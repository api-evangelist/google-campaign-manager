---
name: google-campaign-manager-launch-campaign
description: Create a Campaign Manager 360 campaign under an advertiser, then verify it, using the Campaign Manager 360 API.
api: Google Campaign Manager Campaigns API
generated: '2026-08-13'
method: generated
source: openapi/google-campaign-manager-campaigns-api-openapi.yml, discovery/google-campaign-manager-dfareporting-v5-discovery.json
operations:
  - listCampaigns
  - insertCampaign
  - getCampaign
---

# Launch a Campaign Manager 360 campaign

Creates a campaign under an existing advertiser and confirms it landed.

## Before you start

- Base URL: `https://dfareporting.googleapis.com/dfareporting/v5`. The OpenAPI in this repo describes **v4, which is retired** — the operationIds are unchanged but the version segment in the path is not. Requests to `/dfareporting/v4/...` return HTTP 404.
- OAuth 2.0 access token with scope `https://www.googleapis.com/auth/dfatrafficking`. There is no API-key path.
- You need a **user profile ID**, not an account ID. Resolve it once with `GET /userprofiles` and cache it — every path below is `/userprofiles/{profileId}/...`.
- You need an `advertiserId`. Campaigns cannot be created without one.

## Steps

### 1. Check whether the campaign already exists

`listCampaigns` — `GET /userprofiles/{profileId}/campaigns`

Filter with `advertiserIds` and `searchString` (the `*` wildcard is supported on the name). Do this first: **`insertCampaign` is a POST with no idempotency key**, so a retry after a network timeout will create a duplicate campaign. Listing before inserting is the only safe-retry pattern this API offers.

Page with `maxResults` + `pageToken`; stop when `nextPageToken` is absent.

### 2. Create the campaign

`insertCampaign` — `POST /userprofiles/{profileId}/campaigns`

Required in the body: `advertiserId`, `name`, `startDate`, `endDate`, `defaultLandingPageId`. Dates are `YYYY-MM-DD`.

Optional but usually wanted: `creativeOptimizationConfiguration`, `clickThroughUrlSuffixProperties`, `defaultClickThroughEventTagProperties`, `adBlockingConfiguration`.

The response is the created `Campaign` with a server-assigned `id` and an `idDimensionValue`. **Keep the `idDimensionValue`** — it is what the reporting side of the API accepts as a filter, and you cannot construct it yourself.

### 3. Verify

`getCampaign` — `GET /userprofiles/{profileId}/campaigns/{campaignId}`

Use `fields=id,name,startDate,endDate,archived` to keep the response small; the full Campaign object is 28 properties deep.

## Error handling

Branch on `error.errors[0].reason`, not on the HTTP status — this API reports throttling as **403, never 429**.

| status | reason | do this |
|---|---|---|
| 400 | `required` / `invalidParameter` | Fix the body. Check enum values against the v5 Discovery Document. |
| 401 | `required` | Refresh the access token. Retry once. |
| 403 | `insufficientPermissions` | Token is missing `dfatrafficking`. Re-consent. |
| 403 | `userRateLimitExceeded` | Exponential backoff. There is no `Retry-After` header — you own the schedule. |
| 403 | `dailyLimitExceeded` | 50,000/project/day is spent. Resets midnight PST. Retrying will not help. |
| 404 | `notFound` | Wrong `profileId`, wrong `campaignId` — or you are still calling `/v4/`. |

## Rate discipline

1 QPS per project by default, 10 QPS maximum. Google explicitly advises against concurrent write requests. Serialise campaign creation.
