# Okendo

Reviews and UGC platform focused on structured attribute capture and photo/video reviews.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: API key
- **Header**: `Authorization: {api_key}`
- **Get key**: Okendo admin → Settings → API

## Agent Notes

- **Okendo's differentiator is structured attribute capture** — fit, skin type, hair type, age range, and custom category attributes on every review. This is what produces "87% said true to size" aggregations.
- Those attributes are the highest-value output for the `product-pages` skill: they reduce returns and raise conversion simultaneously. Pull them, do not just pull star ratings.
- Media (photo/video) reviews are a separate field; surface them first in display recommendations.
- Supports Google Seller Ratings and product ratings feed for Shopping ads — coordinate with `catalog-and-feeds`.
- **Related skills**: `reviews-and-reputation`, `product-pages`, `customer-research`
