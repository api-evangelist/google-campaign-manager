---
name: google-campaign-manager-traffic-ad
description: Traffic an ad in Campaign Manager 360 — create it against a campaign, assign creatives and placements, then adjust it in place.
api: Google Campaign Manager Ads API
generated: '2026-08-13'
method: generated
source: openapi/google-campaign-manager-ads-api-openapi.yml, discovery/google-campaign-manager-dfareporting-v5-discovery.json
operations:
  - listAds
  - insertAd
  - getAd
  - updateAd
  - patchAd
---

# Traffic an ad in Campaign Manager 360

## Before you start

- Base URL `https://dfareporting.googleapis.com/dfareporting/v5`, scope `https://www.googleapis.com/auth/dfatrafficking`, a resolved `profileId`.
- An ad needs a `campaignId` that already exists, plus the creatives and placements it will bind.

## Steps

### 1. Create the ad

`insertAd` — `POST /userprofiles/{profileId}/ads`

The body carries the whole delivery configuration inline. The two fields that do the real work:

- `creativeRotation.creativeAssignments[]` — each entry names a `creativeId`, a `clickThroughUrl`, and optional `startTime`/`endTime`. `creativeRotation.type` and `weightCalculationStrategy` decide how they rotate.
- `placementAssignments[]` — each entry names a `placementId` and an `active` flag. **This is the many-to-many join between ads and inventory, and it lives on the Ad**, not on the Placement and not as its own resource. There is no separate assignment endpoint.

Targeting is also inline and optional: `geoTargeting`, `technologyTargeting`, `dayPartTargeting`, `languageTargeting`, `remarketingListExpression`, `deliverySchedule.frequencyCap`.

An alternative is `targetingTemplateId`, which pulls a saved targeting bundle instead of restating it.

### 2. Read it back

`getAd` — `GET /userprofiles/{profileId}/ads/{adId}`

Use `fields` to select only what you need; the Ad object has 40 top-level properties.

### 3. Change it

Two verbs, and the difference matters:

- `updateAd` — `PUT /userprofiles/{profileId}/ads/{adId}`. **Full replacement.** Any field you omit is cleared. Always GET, mutate, then PUT the whole object. PUT is idempotent, so it is the safe verb to retry.
- `patchAd` — `PATCH /userprofiles/{profileId}/ads/{adId}?id={adId}`. Partial update; send only the fields you are changing. Note the `id` query parameter is required in addition to the path segment.

Prefer `patchAd` for a single-field change such as flipping `active`, and `updateAd` when you are rewriting the assignment lists.

### 4. Find ads later

`listAds` — `GET /userprofiles/{profileId}/ads`

Filter with `campaignIds`, `advertiserId`, `creativeIds`, `placementIds`, `active`, `archived`, `type`, `searchString`. Page with `maxResults` + `pageToken` until `nextPageToken` is gone.

## Gotchas

- Ad IDs are int64 serialised as **strings**. Parsing them as JavaScript numbers loses precision.
- Every write is a `POST`/`PUT`/`PATCH` with no idempotency key. On a timeout, `listAds` filtered by `campaignIds` before you retry an insert.
- Errors follow the Google envelope; branch on `error.errors[0].reason`. Throttling arrives as **403 `userRateLimitExceeded`**, not 429, with no `Retry-After`.
