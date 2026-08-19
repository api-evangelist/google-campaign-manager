---
name: google-campaign-manager-generate-placement-tags
description: Create placements against a campaign and generate the ad tags a publisher needs to serve them.
api: Google Campaign Manager Placements API
generated: '2026-08-13'
method: generated
source: openapi/google-campaign-manager-placements-api-openapi.yml, discovery/google-campaign-manager-dfareporting-v5-discovery.json
operations:
  - listPlacements
  - insertPlacement
  - getPlacement
  - updatePlacement
  - patchPlacement
  - generatePlacementTags
---

# Create placements and pull their ad tags

The end of the trafficking chain: a placement is the unit of inventory, and its **ad tag** is the artifact you actually hand to a publisher.

## Before you start

- Base URL `https://dfareporting.googleapis.com/dfareporting/v5`, scope `https://www.googleapis.com/auth/dfatrafficking`, a resolved `profileId`.
- You need a `campaignId` and either a `siteId` or a `directorySiteId`. A placement must sit on inventory.

## Steps

### 1. Create the placement

`insertPlacement` — `POST /userprofiles/{profileId}/placements`

Required: `name`, `campaignId`, one of `siteId` / `directorySiteId`, `compatibility` (`DISPLAY`, `DISPLAY_INTERSTITIAL`, `APP`, `APP_INTERSTITIAL`, `IN_STREAM_VIDEO`, `IN_STREAM_AUDIO`), `size` (for display), `paymentSource`, and a `pricingSchedule` with `startDate`, `endDate` and `pricingType`.

Monetary values in `pricingSchedule` are **micros** — millionths of the account currency unit. A $2.50 CPM is `2500000`.

Also on the object: `tagSetting`, `videoSettings`, `conversionDomainOverride`, `placementGroupId`, `placementStrategyId`, `contentCategoryId`.

### 2. Generate the ad tags

`generatePlacementTags` — `POST /userprofiles/{profileId}/placements/generatetags`

Query parameters: `campaignId`, repeated `placementIds`, and repeated `tagFormats` (for example `PLACEMENT_TAG_STANDARD`, `PLACEMENT_TAG_IFRAME_JAVASCRIPT`, `PLACEMENT_TAG_JAVASCRIPT`, `PLACEMENT_TAG_INTERNAL_REDIRECT`, `PLACEMENT_TAG_TRACKING`).

The response carries `placementTags[]`, each with the `placementId` and `tagDatas[]` — the tag string per requested format. This is a POST that reads rather than writes; it creates nothing and is safe to repeat.

### 3. Read and adjust

- `getPlacement` — `GET /userprofiles/{profileId}/placements/{placementId}`. Use `fields`; the object has 48 top-level properties.
- `listPlacements` — filter by `campaignIds`, `siteIds`, `advertiserIds`, `placementStrategyIds`, `compatibilities`, `archived`, `searchString`. Page with `maxResults` + `pageToken`.
- `updatePlacement` — `PUT`, full replacement. GET, mutate, PUT.
- `patchPlacement` — `PATCH` with the `id` query parameter, partial update. Use this to archive one placement without restating the pricing schedule.

## Ordering

Placements must exist before an ad can reference them in `placementAssignments[]`. The dependency chain is: Advertiser → Campaign → Placement → Ad. Creating out of order returns 400 `required`.

## Error handling

Same envelope as the rest of the API — branch on `error.errors[0].reason`. Throttling is **403 `userRateLimitExceeded`**, not 429, with no `Retry-After` header. Google advises against concurrent writes, so create placements serially.
