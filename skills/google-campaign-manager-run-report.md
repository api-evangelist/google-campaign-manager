---
name: google-campaign-manager-run-report
description: Define, run and collect a Campaign Manager 360 report — the asynchronous reporting flow from report definition to downloadable file.
api: Google Campaign Manager Reports API
generated: '2026-08-13'
method: generated
source: openapi/google-campaign-manager-reports-api-openapi.yml, discovery/google-campaign-manager-dfareporting-v5-discovery.json, https://developers.google.com/doubleclick-advertisers/guides/run_reports
operations:
  - listReports
  - insertReport
  - getReport
  - updateReport
  - runReport
  - deleteReport
---

# Run a Campaign Manager 360 report

Reporting here is **asynchronous by design**. You create a durable report *definition*, run it to produce a *File*, poll until the file is ready, then download it. There is no webhook and no callback.

## Before you start

- Base URL `https://dfareporting.googleapis.com/dfareporting/v5`, scope `https://www.googleapis.com/auth/dfareporting`, a resolved `profileId`.
- Reports are owned by a profile (`ownerProfileId`), not by an account.

## Steps

### 1. Create the report definition

`insertReport` — `POST /userprofiles/{profileId}/reports`

Set `type` and then exactly one matching criteria block:

| `type` | criteria field |
|---|---|
| `STANDARD` | `criteria` |
| `REACH` | `reachCriteria` |
| `PATH_TO_CONVERSION` | `pathToConversionCriteria` |
| `FLOODLIGHT` | `floodlightCriteria` |
| `CROSS_MEDIA_REACH` | `crossMediaReachCriteria` |

Each criteria block carries `dateRange` (either `relativeDateRange` such as `LAST_30_DAYS`, or explicit `startDate`/`endDate`), `dimensions[]`, `metricNames[]` and optional `dimensionFilters[]`.

**Dimension filters take `DimensionValue` objects, not raw IDs.** If you have a campaign ID from the trafficking side, you cannot drop it straight into a filter — fetch its `idDimensionValue` from the campaign, or resolve it with `dimensionValues.query`. This is the seam between the trafficking and reporting halves of the API and it catches almost everyone.

Optional: `schedule` (recurring runs) and `delivery` (email recipients).

Two removals landed in v5 — `crossDimensionReachCriteria` and `enableAllDimensionCombinations` no longer exist on Report.

### 2. Run it

`runReport` — `POST /userprofiles/{profileId}/reports/{reportId}/run`

Pass `synchronous=false` (the default) for anything non-trivial. The response is a `File` with a `status` of `PROCESSING`.

### 3. Poll for the file

`GET /userprofiles/{profileId}/reports/{reportId}/files/{fileId}`

`status` moves `PROCESSING` → `REPORT_AVAILABLE`, or to `FAILED` / `CANCELLED`. Poll with backoff — **a poll costs the same quota as any other call**, and you have 1 QPS by default against a 50,000/day project budget. A tight polling loop on several reports will exhaust the day.

### 4. Download

Take `urls.apiUrl` from the ready `File` and GET it with the same OAuth token, following redirects. Large files support HTTP `Range` requests.

### 5. Maintain the definition

- `getReport` / `listReports` — retrieve. `listReports` accepts `scope`, `sortField`, `sortOrder`, `maxResults`, `pageToken`.
- `updateReport` — `PUT`. **Full replacement**; GET first, mutate, PUT the whole object.
- `deleteReport` — `DELETE`. Removes the definition and its generated files.

### patchReport no longer exists

The OpenAPI in this repository (v4) carries `patchReport`. **The v5 release notes removed the `patch` method from the Reports resource.** Use `updateReport` instead. This is the one operation in this repo's specs with no v5 successor.

## Error handling

| status | reason | do this |
|---|---|---|
| 400 | `invalidParameter` | A dimension or metric name is not valid for this report type. Check with `reports.compatibleFields.query`. |
| 403 | `quotaExceeded` | Scheduled-report or account object limit hit — delete unused report definitions. |
| 403 | `userRateLimitExceeded` | Slow the polling loop. Exponential backoff; no `Retry-After` is returned. |
| 403 | `dailyLimitExceeded` | The project's 50,000 daily requests are gone until midnight PST. |
| 404 | `notFound` | Report deleted, or the file expired. |
