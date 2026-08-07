# Meta Catalog

Product catalog powering Advantage+ catalog ads, dynamic retargeting, Shops, and Advantage+ Shopping campaigns.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | Marketing API / Graph API |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Official Business SDKs |

## Authentication

- **Type**: OAuth 2.0 access token with `catalog_management` and `business_management`
- **Base**: `https://graph.facebook.com/v21.0`

## Common Agent Operations

```bash
# Catalog products
GET /{catalog_id}/products?limit=100

# Diagnostics — feed errors and warnings
GET /{catalog_id}/diagnostics

# Product sets (the segmentation unit)
GET /{catalog_id}/product_sets

# Batch update
POST /{catalog_id}/batch
```

## Agent Notes

- **Catalog health silently drives Advantage+ performance.** A broken catalog degrades ASC campaigns in a way that presents as a media-buying problem. Check `diagnostics` before restructuring an account.
- **`content_id` in the pixel event must match the catalog `id`.** This mismatch is common, completely invisible without checking, and it breaks catalog retargeting entirely.
- Prefer the platform integration (Shopify, WooCommerce) over a manual file — it syncs price and availability far more reliably.
- Product sets are the segmentation unit; build them from the same logic as Google custom labels.
- **Related skills**: `catalog-and-feeds`, `paid-social`, `measurement-and-analytics`
