# Google Campaign Manager

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Campaign Manager 360 is Google's ad-serving, trafficking and measurement platform for advertisers and agencies. Its API — service name dfareporting — lets developers programmatically manage advertisers, campaigns, ads, creatives, placements, floodlight conversion tags and remarketing lists, generate publisher ad tags, and define, run and download standard, reach, path-to-conversion, floodlight and cross-media reach reports. Access is OAuth 2.0 only and every path is scoped to a Campaign Manager 360 user profile. The current version is v5; v4 has been fully sunset. Google publishes a Discovery Document rather than an OpenAPI, plus Data Transfer v2.0 for bulk event-level delivery to Cloud Storage.

**Areas:** Advertising · Analytics · Campaign Management · Digital Marketing · Reporting · Ad Serving · Ad Trafficking · Attribution · Conversion Tracking · Marketing · Media Buying · Google Marketing Platform

## Google Campaign Manager on APIs.io

Everything profiled for Google Campaign Manager is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/google-campaign-manager/](https://apis.io/providers/google-campaign-manager/)** — or go straight to one of the APIs or properties below.

### APIs (5)

- [Campaign Manager 360 Data Transfer v2.0](https://apis.io/apis/google-campaign-manager/campaign-manager-360-data-transfer-v20/) — Data Transfer v2.0 provides raw, event-level reporting data from Campaign Manager 360 beyond what is available through standard reporting. Data is delivered…
- [Google Campaign Manager Ads API](https://apis.io/apis/google-campaign-manager/google-campaign-manager-ads-api/) — Manage ad configurations within campaigns. Ads define the creative content, delivery schedules, targeting rules, and placement assignments that determine…
- [Google Campaign Manager Campaigns API](https://apis.io/apis/google-campaign-manager/google-campaign-manager-campaigns-api/) — Manage advertising campaigns. Campaigns serve as top-level organizational containers that group ads, placements, and creatives under a single advertiser…
- [Google Campaign Manager Placements API](https://apis.io/apis/google-campaign-manager/google-campaign-manager-placements-api/) — Manage placements representing ad inventory on publisher sites. Placements define the size, format, pricing, and site location where ads can be served, and…
- [Google Campaign Manager Reports API](https://apis.io/apis/google-campaign-manager/google-campaign-manager-reports-api/) — Create, configure, and run reports to analyze campaign performance. Reports support multiple types including standard, reach, path to conversion,…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [google-campaign-manager-mcp.yml](https://apis.io/servers/google-campaign-manager/google-campaign-manager-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Google Campaign Manager Agentic Access](https://apis.io/agentic-access/google-campaign-manager/google-campaign-manager-agentic-access/)

#### JSON Schema (64)

The data models the API reads and writes.

- [Activities](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-activities/)
- [Ad](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-ad/)
- [AdBlockingConfiguration](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-ad-blocking-configuration/)
- [AdsListResponse](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-ads-list-response/)
- [AudienceSegment](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-audience-segment/)
- [AudienceSegmentGroup](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-audience-segment-group/)
- [Browser](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-browser/)
- [Campaign](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-campaign/)
- [CampaignsListResponse](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-campaigns-list-response/)
- [City](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-city/)
- [ClickThroughUrl](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-click-through-url/)
- [ClickThroughUrlSuffixProperties](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-click-through-url-suffix-properties/)
- [ConnectionType](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-connection-type/)
- [ConversionDomainOverride](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-conversion-domain-override/)
- [Country](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-country/)
- [CreativeAssignment](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-creative-assignment/)
- [CreativeOptimizationConfiguration](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-creative-optimization-configuration/)
- [CreativeRotation](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-creative-rotation/)
- [CustomRichMediaEvents](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-custom-rich-media-events/)
- [DateRange](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-date-range/)
- [DayPartTargeting](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-day-part-targeting/)
- [DefaultClickThroughEventTagProperties](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-default-click-through-event-tag-properties/)
- [DeliverySchedule](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-delivery-schedule/)
- [DimensionValue](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-dimension-value/)
- [Error](https://apis.io/schemas/google-campaign-manager/google-campaign-manager-error/)
- …and 39 more published on APIs.io

#### JSON Structure (64)

Data models expressed in JSON Structure.

- [Google Campaign Manager Activities Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-activities-structure/)
- [Google Campaign Manager Ad Blocking Configuration Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-ad-blocking-configuration-structure/)
- [Google Campaign Manager Ad Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-ad-structure/)
- [Google Campaign Manager Ads List Response Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-ads-list-response-structure/)
- [Google Campaign Manager Audience Segment Group Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-audience-segment-group-structure/)
- [Google Campaign Manager Audience Segment Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-audience-segment-structure/)
- [Google Campaign Manager Browser Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-browser-structure/)
- [Google Campaign Manager Campaign Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-campaign-structure/)
- [Google Campaign Manager Campaigns List Response Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-campaigns-list-response-structure/)
- [Google Campaign Manager City Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-city-structure/)
- [Google Campaign Manager Click Through Url Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-click-through-url-structure/)
- [Google Campaign Manager Click Through Url Suffix Properties Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-click-through-url-suffix-properties-structure/)
- [Google Campaign Manager Connection Type Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-connection-type-structure/)
- [Google Campaign Manager Conversion Domain Override Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-conversion-domain-override-structure/)
- [Google Campaign Manager Country Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-country-structure/)
- [Google Campaign Manager Creative Assignment Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-creative-assignment-structure/)
- [Google Campaign Manager Creative Optimization Configuration Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-creative-optimization-configuration-structure/)
- [Google Campaign Manager Creative Rotation Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-creative-rotation-structure/)
- [Google Campaign Manager Custom Rich Media Events Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-custom-rich-media-events-structure/)
- [Google Campaign Manager Date Range Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-date-range-structure/)
- [Google Campaign Manager Day Part Targeting Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-day-part-targeting-structure/)
- [Google Campaign Manager Default Click Through Event Tag Properties Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-default-click-through-event-tag-properties-structure/)
- [Google Campaign Manager Delivery Schedule Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-delivery-schedule-structure/)
- [Google Campaign Manager Dimension Value Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-dimension-value-structure/)
- [Google Campaign Manager Error Structure](https://apis.io/json-structure/google-campaign-manager/google-campaign-manager-error-structure/)
- …and 39 more published on APIs.io

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Google Campaign Manager Context](https://apis.io/jsonld/google-campaign-manager/google-campaign-manager-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [google-campaign-manager API Vocabulary](https://apis.io/vocabularies/google-campaign-manager/google-campaign-manager-vocabulary/)

#### Examples (64)

Example requests and responses.

- [Google Campaign Manager Activities Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-activities-example/)
- [Google Campaign Manager Ad Blocking Configuration Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-ad-blocking-configuration-example/)
- [Google Campaign Manager Ad Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-ad-example/)
- [Google Campaign Manager Ads List Response Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-ads-list-response-example/)
- [Google Campaign Manager Audience Segment Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-audience-segment-example/)
- [Google Campaign Manager Audience Segment Group Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-audience-segment-group-example/)
- [Google Campaign Manager Browser Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-browser-example/)
- [Google Campaign Manager Campaign Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-campaign-example/)
- [Google Campaign Manager Campaigns List Response Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-campaigns-list-response-example/)
- [Google Campaign Manager City Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-city-example/)
- [Google Campaign Manager Click Through Url Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-click-through-url-example/)
- [Google Campaign Manager Click Through Url Suffix Properties Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-click-through-url-suffix-properties-example/)
- [Google Campaign Manager Connection Type Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-connection-type-example/)
- [Google Campaign Manager Conversion Domain Override Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-conversion-domain-override-example/)
- [Google Campaign Manager Country Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-country-example/)
- [Google Campaign Manager Creative Assignment Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-creative-assignment-example/)
- [Google Campaign Manager Creative Optimization Configuration Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-creative-optimization-configuration-example/)
- [Google Campaign Manager Creative Rotation Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-creative-rotation-example/)
- [Google Campaign Manager Custom Rich Media Events Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-custom-rich-media-events-example/)
- [Google Campaign Manager Date Range Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-date-range-example/)
- [Google Campaign Manager Day Part Targeting Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-day-part-targeting-example/)
- [Google Campaign Manager Default Click Through Event Tag Properties Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-default-click-through-event-tag-properties-example/)
- [Google Campaign Manager Delivery Schedule Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-delivery-schedule-example/)
- [Google Campaign Manager Dimension Value Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-dimension-value-example/)
- [Google Campaign Manager Error Example](https://apis.io/examples/google-campaign-manager/google-campaign-manager-error-example/)
- …and 39 more published on APIs.io

#### Collections (5)

Postman and Open Collection request collections.

- [Google Campaign Manager Campaign Manager 360 API](https://apis.io/collections/google-campaign-manager/open-google-campaign-manager/)
- [Google Campaign Manager Campaign Manager 360 Ads API](https://apis.io/collections/google-campaign-manager/open-google-campaign-manager-ads-api/)
- [Google Campaign Manager Campaign Manager 360 Ads Campaigns API](https://apis.io/collections/google-campaign-manager/open-google-campaign-manager-campaigns-api/)
- [Google Campaign Manager Campaign Manager 360 Ads Placements API](https://apis.io/collections/google-campaign-manager/open-google-campaign-manager-placements-api/)
- [Google Campaign Manager Campaign Manager 360 Ads Reports API](https://apis.io/collections/google-campaign-manager/open-google-campaign-manager-reports-api/)

#### Overlays (8)

OpenAPI overlays, including conversational phrasing for each operation.

- [Google Campaign Manager Ads Api Overlay](https://apis.io/overlays/google-campaign-manager/google-campaign-manager-ads-api-overlay/)
- [Google Campaign Manager Ads Api Phrasing Overlay](https://apis.io/overlays/google-campaign-manager/google-campaign-manager-ads-api-phrasing-overlay/)
- [Google Campaign Manager Campaigns Api Overlay](https://apis.io/overlays/google-campaign-manager/google-campaign-manager-campaigns-api-overlay/)
- [Google Campaign Manager Campaigns Api Phrasing Overlay](https://apis.io/overlays/google-campaign-manager/google-campaign-manager-campaigns-api-phrasing-overlay/)
- [Google Campaign Manager Placements Api Overlay](https://apis.io/overlays/google-campaign-manager/google-campaign-manager-placements-api-overlay/)
- [Google Campaign Manager Placements Api Phrasing Overlay](https://apis.io/overlays/google-campaign-manager/google-campaign-manager-placements-api-phrasing-overlay/)
- [Google Campaign Manager Reports Api Overlay](https://apis.io/overlays/google-campaign-manager/google-campaign-manager-reports-api-overlay/)
- [Google Campaign Manager Reports Api Phrasing Overlay](https://apis.io/overlays/google-campaign-manager/google-campaign-manager-reports-api-phrasing-overlay/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Google Campaign Manager — jsonschema rules](https://apis.io/rules/google-campaign-manager/google-campaign-manager-jsonschema-spectral-rules/)
- [Google Campaign Manager API Rules](https://apis.io/rules/google-campaign-manager/google-campaign-manager-spectral-rules/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Google Campaign Manager Authentication](https://apis.io/security/google-campaign-manager/google-campaign-manager-authentication/)
- [Google Campaign Manager Domain Security](https://apis.io/security/google-campaign-manager/google-campaign-manager-domain-security/)
- [Google Campaign Manager Vulnerability Disclosure](https://apis.io/security/google-campaign-manager/google-campaign-manager-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Google Campaign Manager Scopes](https://apis.io/scopes/google-campaign-manager/google-campaign-manager-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Google Campaign Manager Plans Pricing](https://apis.io/plans/google-campaign-manager/google-campaign-manager-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Google Campaign Manager Rate Limits](https://apis.io/rate-limits/google-campaign-manager/google-campaign-manager-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Google Campaign Manager Finops](https://apis.io/finops/google-campaign-manager/google-campaign-manager-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.google.com/)
- [Documentation](https://developers.google.com/doubleclick-advertisers)
- [Getting started](https://developers.google.com/doubleclick-advertisers/getting_started)
- [API reference](https://developers.google.com/doubleclick-advertisers/rest)
- [Pricing](https://marketingplatform.google.com/about/campaign-manager-360/)
- [Sign up](https://marketingplatform.google.com/about/campaign-manager-360/)
- [Support](https://developers.google.com/doubleclick-advertisers/get-support)
- [Blog](https://blog.google/products/marketingplatform/)
- [Terms of service](https://policies.google.com/terms)
- [Privacy policy](https://policies.google.com/privacy)
- [GitHub](https://github.com/googleads)
- [Status](https://status.cloud.google.com/)

## API Evangelist rating

**Kin Score 65.9** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 64.3 |
| Contract quality | 63.2 |
| Contract governance | 31.8 |
| Operational transparency | 84.2 |
| Developer ergonomics | 70.8 |
| Access clarity | 44.7 |

**Agent readiness 32.8** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | documented (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | distinct |

**Regulatory alignment 40.2** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/google-campaign-manager/](https://apis.io/providers/google-campaign-manager/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Google Campaign Manager: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/google-campaign-manager/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
