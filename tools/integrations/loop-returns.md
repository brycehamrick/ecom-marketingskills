# Loop Returns

Returns and exchange platform for Shopify. Its core value is converting refunds into exchanges and store credit.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: API key
- **Header**: `X-Authorization: {api_key}`
- **Base URL**: `https://api.loopreturns.com/api/v1`

## Common Agent Operations

```bash
# List returns
GET /warehouse/return/list?filter[created_at][gte]=2026-01-01

# Return detail with line items and reasons
GET /warehouse/return/{id}
```

## Agent Notes

- **Return reason codes are the point.** Pull them, group them, and route each to the upstream cause — sizing to `product-pages`, "not as described" to imagery and copy, "changed mind" often to delivery speed. This is the analysis the `post-purchase-experience` skill runs.
- Track the **exchange-to-refund ratio**. It is the direct measure of whether the returns flow is retaining revenue.
- Loop's bonus-credit mechanic ("$50 refund or $60 credit") is configured in the admin; verify it is on before recommending it.
- **Related skills**: `post-purchase-experience`, `product-pages`, `retention-and-loyalty`
