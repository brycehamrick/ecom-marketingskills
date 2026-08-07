# Amazon Ads API

Sponsored Products, Sponsored Brands, and Sponsored Display campaign management and reporting.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST, versioned per ad product |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Community SDKs; official OpenAPI specs |

## Authentication

- **Type**: LWA OAuth 2.0 (same identity system as SP-API, separate app registration)
- **Headers**: `Authorization: Bearer {token}`, `Amazon-Advertising-API-ClientId`, `Amazon-Advertising-API-Scope: {profileId}`
- **Profiles**: one per marketplace/account. Every request is scoped to a profile ID.

## Common Agent Operations

```bash
# List profiles (do this first — you need the profile ID)
GET /v2/profiles

# Sponsored Products campaigns
GET /sp/campaigns

# Request a report (async: request, poll, download)
POST /reporting/reports
{ "reportTypeId": "spSearchTerm", "timeUnit": "DAILY", ... }
```

## Agent Notes

- **The search term report is the recurring work.** It drives the promote/negate cycle that the `marketplace-ads` skill describes as where accounts are won.
- Reporting is asynchronous everywhere: request → poll status → download. Budget for the round trip.
- **TACoS is not an API metric.** Compute it: ad spend from Ads API divided by total sales from SP-API. This cross-API join is what tells you whether ads are buying rank or renting sales.
- Sponsored Brands and Sponsored Display use different endpoint versions than Sponsored Products. Do not assume parity.
- **Related skills**: `marketplace-ads`, `amazon-growth`, `profitability-and-incrementality`
