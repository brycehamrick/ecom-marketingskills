# Faire

Wholesale marketplace connecting brands to independent retailers. The default starting point for most brands entering wholesale.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST, for brands |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: API token
- **Header**: `X-FAIRE-ACCESS-TOKEN: {token}`
- **Base**: `https://www.faire.com/external-api/v2`
- **Get token**: Faire brand portal → Integrations

## Common Agent Operations

```bash
# Products
GET /products?limit=50

# Orders
GET /orders?limit=50&updated_at_min=2026-01-01

# Accept an order
PUT /orders/{order_id}/processing

# Inventory
PATCH /products/{product_id}/options/{option_id}
```

## Agent Notes

- **Optimize the Faire storefront like a marketplace listing** — imagery, complete product data, correct category placement, competitive minimums. Discovery on Faire is search- and browse-driven.
- **Commission differs by retailer source.** Retailers Faire brings you cost more than retailers you bring onto the platform. Bringing your own accounts onto Faire is materially cheaper — factor this into the margin model.
- Order data here is your wholesale sell-in. Sell-**through** requires the retailer to report it, and Faire does not provide it — that gap is why the `wholesale-and-retail` skill emphasizes measuring sell-through separately.
- Insider program and free-shipping terms affect discoverability; check what is enabled.
- **Related skills**: `wholesale-and-retail`, `pricing-strategy`
