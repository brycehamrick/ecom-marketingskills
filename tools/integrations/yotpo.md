# Yotpo

Reviews, UGC, loyalty, and SMS platform. Reviews product is the most commonly used piece.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST; separate APIs per product (Reviews, Loyalty, SMS) |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: App key + secret exchanged for a bearer token
- **Reviews base**: `https://api.yotpo.com`
- **Loyalty base**: `https://loyalty.yotpo.com/api/v2` (separate GUID + API key)
- Products authenticate independently — a Reviews token does not work against Loyalty.

## Common Agent Operations

```bash
# Get reviews for a product
GET /v1/widget/{app_key}/products/{product_id}/reviews.json

# All reviews for the account (bulk export for mining)
GET /v1/apps/{app_key}/reviews?utoken={token}&count=100&page=1

# Create a review request
POST /apps/{app_key}/purchases
```

## Agent Notes

- **Bulk-export reviews for analysis**, not the widget endpoint. The `customer-research` skill needs the full corpus including 3-star reviews, which is where the highest-density signal is.
- Custom review questions map to structured attributes (fit, skin type). Those power the aggregated feedback that reduces returns — see `product-pages`.
- Yotpo syndicates reviews to retailer sites and to Google Seller Ratings. Check what is enabled before recommending syndication work.
- Loyalty API exposes point balances and tier state for RFM segmentation.
- **Related skills**: `reviews-and-reputation`, `customer-research`, `retention-and-loyalty`
