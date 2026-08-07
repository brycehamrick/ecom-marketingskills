# Amazon SP-API (Selling Partner API)

Amazon's API for listings, orders, inventory, reports, and fees. The data source behind everything in the `amazon-growth` skill.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST, region-scoped endpoints |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Official SDKs in Java, PHP, Python, Node, C#, TypeScript |

## Authentication

- **Type**: LWA (Login with Amazon) OAuth 2.0
- **Flow**: refresh token → access token, exchanged per request cycle
- **Setup**: register a developer profile in Seller Central, create an app, obtain the LWA client ID/secret and a refresh token
- **Endpoints are regional**: `sellingpartnerapi-na.amazon.com`, `-eu`, `-fe`
- Roles are granular; request only the ones needed. PII roles require additional approval.

## Key APIs

| API | Use |
|-----|-----|
| Catalog Items | ASIN data, attributes, browse nodes |
| Listings Items | Create and update listings, read issue/suppression status |
| Reports | Bulk data — the primary route for search terms, inventory, and returns |
| Orders | Order-level detail |
| FBA Inventory | Stock by fulfillment center |
| Product Fees | **Referral and FBA fee estimates per ASIN** |
| Finances | Settlement-level actuals |

## Agent Notes

- **Reports API is where the useful data is.** Most analysis (search terms, inventory health, returns, fee preview) comes from requesting a report, polling for completion, and downloading the document — not from a live endpoint.
- **Product Fees API is essential for unit economics.** The `amazon-growth` skill's contribution margin model needs referral fee, FBA fee, and size-tier data per ASIN — this is the authoritative source.
- **Listings Items issues array** exposes suppression reasons programmatically. Check it before diagnosing a sales drop as a marketing problem.
- Rate limits are per-operation and strictly enforced with a token bucket. Build in backoff.
- **Related skills**: `amazon-growth`, `marketplace-ads`, `profitability-and-incrementality`
