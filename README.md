# Google Campaign Manager (google-campaign-manager)
The Campaign Manager 360 API allows developers to programmatically manage campaigns, creatives, reports, and other advertising operations in Google's Campaign Manager 360 platform.

**URL:** [Visit APIs.json URL](https://developers.google.com/doubleclick-advertisers)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Advertising, Analytics, Campaign Management, Digital Marketing, Reporting

## Timestamps

- **Created:** 2024
- **Modified:** 2026-04-18

## APIs

### Campaign Manager 360 API
Manage your DoubleClick Campaign Manager ad campaigns and reports programmatically. Create, retrieve, update, and delete campaigns, creatives, placements, and generate comprehensive reporting data.

**Human URL:** [https://developers.google.com/doubleclick-advertisers](https://developers.google.com/doubleclick-advertisers)

#### Tags:

 - Advertising, Analytics, Campaign Management, Conversions, Creatives, Digital Marketing, Floodlight, Placements, Reporting, Trafficking

#### Properties

- [Documentation](https://developers.google.com/doubleclick-advertisers/v4)
- [Documentation](https://developers.google.com/doubleclick-advertisers/rest)
- [OpenAPI](openapi/google-campaign-manager-openapi.yml)
- [Authentication](https://developers.google.com/doubleclick-advertisers/guides/authorizing)
- [Pricing](https://marketingplatform.google.com/about/campaign-manager-360/pricing/)
- [Quickstart](https://developers.google.com/doubleclick-advertisers/getting_started)
- [Support](https://support.google.com/campaignmanager)
- [Console](https://console.cloud.google.com/apis/library/dfareporting.googleapis.com)
- [TermsOfService](https://developers.google.com/terms)
- [RateLimits](https://developers.google.com/doubleclick-advertisers/quotas)
- [ReleaseNotes](https://developers.google.com/doubleclick-advertisers/rel_notes)
- [Client Libraries](https://developers.google.com/doubleclick-advertisers/libraries)

### Campaign Manager 360 Data Transfer v2.0
Data Transfer v2.0 provides raw, event-level reporting data from Campaign Manager 360 beyond what is available through standard reporting. Data is delivered to Google Cloud Storage as CSV files for advanced analysis and data warehousing use cases.

**Human URL:** [https://developers.google.com/doubleclick-advertisers/dtv2/overview](https://developers.google.com/doubleclick-advertisers/dtv2/overview)

#### Tags:

 - Analytics, Cloud Storage, CSV, Data Transfer, Raw Data, Reporting

#### Properties

- [Documentation](https://developers.google.com/doubleclick-advertisers/dtv2/overview)
- [Quickstart](https://developers.google.com/doubleclick-advertisers/dtv2/getting-started)
- [FAQ](https://developers.google.com/doubleclick-advertisers/dtv2/reference/faq)
- [ReleaseNotes](https://developers.google.com/doubleclick-advertisers/dtv2/reference/release-notes)
- [Support](https://developers.google.com/doubleclick-advertisers/dtv2/get-support)

## Common Properties

- [Portal](https://developers.google.com/)
- [Authentication](https://developers.google.com/identity/protocols/oauth2)
- [Blog](https://blog.google/products/marketingplatform/)
- [StatusPage](https://status.cloud.google.com/)
- [PrivacyPolicy](https://policies.google.com/privacy)
- [TermsOfService](https://policies.google.com/terms)
- [GitHubRepository](https://github.com/googleads/googleads-dfa-reporting-samples)

## Features

| Name | Description |
|------|-------------|
| Campaign Lifecycle Management | Create, update, and manage advertising campaigns from inception through completion with full programmatic control. |
| Ad Trafficking | Automate the placement and scheduling of ads across publisher sites with targeting and delivery rules. |
| Multi-Format Reporting | Generate standard, reach, path-to-conversion, cross-dimension, floodlight, and cross-media reach reports. |
| Placement Tag Generation | Automatically generate ad tags for publishers to install on their pages. |
| Audience Targeting | Configure geo-targeting, technology targeting, day-part targeting, and audience segment rules. |
| Floodlight Conversion Tracking | Track and attribute conversions using Floodlight tags for cross-channel measurement. |

## Use Cases

| Name | Description |
|------|-------------|
| Programmatic Campaign Setup | Automate the creation and configuration of advertising campaigns, ads, and placements across publisher inventory. |
| Performance Reporting | Generate and schedule reports to analyze campaign performance, reach, and conversion data. |
| Cross-Channel Attribution | Use path-to-conversion and cross-media reach reports to understand multi-channel advertising impact. |
| Ad Operations Automation | Streamline trafficking workflows including placement creation, tag generation, and creative assignment. |

## Integrations

| Name | Description |
|------|-------------|
| Google Analytics | Combine Campaign Manager 360 data with Google Analytics for unified web analytics and attribution. |
| Google Ads | Coordinate campaign management between Campaign Manager 360 and Google Ads platforms. |
| Display & Video 360 | Integrate with DV360 for programmatic buying and campaign execution. |
| Google Cloud Storage | Export raw event-level data via Data Transfer for advanced analysis in BigQuery or other tools. |
| Google Apps Script | Automate Campaign Manager operations using Google Apps Script advanced service. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Google Campaign Manager OpenAPI](openapi/google-campaign-manager-openapi.yml)

### JSON Schema

- [Campaign Schema](json-schema/google-campaign-manager-campaign-schema.json)
- [Ad Schema](json-schema/google-campaign-manager-ad-schema.json)
- [Placement Schema](json-schema/google-campaign-manager-placement-schema.json)
- [Report Schema](json-schema/google-campaign-manager-report-schema.json)

### JSON-LD

- [Google Campaign Manager Context](json-ld/google-campaign-manager-context.jsonld)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Campaign Manager 360 API](capabilities/shared/campaign-manager-360.yaml) — 19 operations for campaign, ad, placement, and report management

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Campaign Management](capabilities/campaign-management.yaml) | Campaign Manager 360 | 19 | Ad Operations Specialist |

## Vocabulary

- [Google Campaign Manager Vocabulary](vocabulary/google-campaign-manager-vocabulary.yaml)

## Rules

- [Google Campaign Manager Spectral Rules](rules/google-campaign-manager-spectral-rules.yml)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
