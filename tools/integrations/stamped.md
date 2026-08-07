# Stamped

Reviews, ratings, UGC, and loyalty platform for ecommerce.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: API key + store hash, HTTP Basic
- **Base**: `https://stamped.io/api`

## Agent Notes

- Combines reviews and loyalty, which simplifies awarding points for reviews — one of the better non-purchase earning actions in a loyalty program.
- Supports custom review fields for structured attributes; configure them per category rather than accepting defaults.
- Google Shopping ratings and rich snippet output are supported — coordinate with `catalog-and-feeds` and `ecommerce-seo`.
- Bulk-export reviews for VOC mining rather than reading the widget. See `customer-research`.
- **Related skills**: `reviews-and-reputation`, `retention-and-loyalty`, `customer-research`
