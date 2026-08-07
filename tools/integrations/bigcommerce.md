# BigCommerce

Hosted ecommerce platform with a more open API and checkout than Shopify.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST v3 + GraphQL Storefront API |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Official Node and PHP SDKs |

## Authentication

- **Type**: OAuth API account token
- **Header**: `X-Auth-Token: {token}`
- **Base**: `https://api.bigcommerce.com/stores/{store_hash}/v3`

## Common Agent Operations

```bash
# Catalog products
GET /v3/catalog/products?limit=250

# Product variants
GET /v3/catalog/products/{id}/variants

# Orders (note: orders remain on v2)
GET /v2/orders?min_date_created=2026-01-01

# Customers
GET /v3/customers
```

## Agent Notes

- **Checkout is more customizable than Shopify's**, so `cart-and-checkout` recommendations that are blocked on Shopify (outside Plus) are often implementable here.
- Multi-storefront support makes it a reasonable choice for `international-expansion` with genuinely distinct catalogs per market.
- Note the v2/v3 split — orders and some legacy resources are still v2. This trips up integrations.
- Native B2B/wholesale features (customer groups, price lists) are stronger than Shopify's without apps. Relevant to `wholesale-and-retail`.
- **Related skills**: `cart-and-checkout`, `international-expansion`, `wholesale-and-retail`
