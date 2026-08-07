# Judge.me

Reviews platform, widely used on Shopify. Lower cost than Yotpo/Okendo with a straightforward API.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: API token + shop domain as query parameters
- **Base URL**: `https://judge.me/api/v1`
- **Params**: `api_token={token}&shop_domain={shop}.myshopify.com`
- **Get token**: Judge.me admin → Settings → API tokens

## Common Agent Operations

```bash
# List reviews
GET /reviews?api_token={t}&shop_domain={d}&per_page=100&page=1

# Reviews for one product
GET /reviews?api_token={t}&shop_domain={d}&product_id={id}

# Review count and average
GET /products/{id}?api_token={t}&shop_domain={d}

# Create a review request
POST /reviews/create_review_request
```

## Agent Notes

- Paginate the full review set for VOC mining. `per_page` maxes at 100.
- `rating`, `body`, `pictures`, and `verified_buyer` are the fields that matter for analysis. Filter to `rating=3` first — highest signal density.
- Judge.me supports review syndication and Google Shopping ratings feed; confirm both are enabled.
- **Related skills**: `reviews-and-reputation`, `customer-research`
