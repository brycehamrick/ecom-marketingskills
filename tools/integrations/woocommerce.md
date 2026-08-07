# WooCommerce

Open-source ecommerce plugin for WordPress. Self-hosted, with a full REST API.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST v3 |
| MCP | - | Not available |
| CLI | ✓ | WP-CLI with the `wc` command namespace |
| SDK | ✓ | Official libraries for PHP, Node, Python, Ruby |

## Authentication

- **Type**: Consumer key + secret (HTTP Basic over HTTPS, or OAuth 1.0a over HTTP)
- **Base**: `https://{site}/wp-json/wc/v3`
- **Get keys**: WooCommerce → Settings → Advanced → REST API

## Common Agent Operations

```bash
# Products
GET /wp-json/wc/v3/products?per_page=100

# Orders
GET /wp-json/wc/v3/orders?after=2026-01-01T00:00:00

# Sales report
GET /wp-json/wc/v3/reports/sales?period=month

# Top sellers
GET /wp-json/wc/v3/reports/top_sellers
```

## Agent Notes

- **Self-hosted means performance is the store's own problem.** Speed audits matter more here than on hosted platforms — plugin bloat is the usual cause, analogous to app bloat on Shopify. See `site-cro`.
- Checkout is fully customizable, which makes the `cart-and-checkout` recommendations more implementable than on Shopify's locked checkout.
- Feed generation typically requires a plugin; verify what is producing the Merchant Center and Meta feeds before diagnosing feed problems. See `catalog-and-feeds`.
- Order data is the source of truth for revenue reconciliation against analytics.
- **Related skills**: `site-cro`, `cart-and-checkout`, `measurement-and-analytics`
