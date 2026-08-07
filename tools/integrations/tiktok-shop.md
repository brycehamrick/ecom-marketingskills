# TikTok Shop

In-app commerce with creator affiliate distribution and live selling. Distinct from the TikTok Ads catalog.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | Partner API, requires app approval |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Official SDKs in several languages |

## Authentication

- **Type**: OAuth 2.0 with signed requests
- Requests require an HMAC signature over sorted parameters plus the app secret
- Shop-scoped: every call carries a `shop_cipher` identifying the shop

## Key Resources

| Area | Use |
|------|-----|
| Product | Listing create/update, category attributes |
| Order | Order lifecycle and fulfillment |
| Fulfillment | Shipping labels, tracking |
| Finance | Settlements, fees |
| Affiliate | Creator campaigns, commission rates, creator performance |

## Agent Notes

- **The affiliate program is the engine.** Most TikTok Shop revenue for most brands comes from creator affiliate videos, not brand-owned content. Commission rate competitiveness and sample availability drive it more than listing quality.
- **This is separate from the TikTok Ads catalog.** Selling through TikTok Shop routes product data, fulfillment, and fees through TikTok's marketplace, not your store.
- **Inventory sync must be reliable.** TikTok traffic converts fast; a stale stock count produces cancellations that damage account metrics.
- Live selling is a substantial channel but requires sustained commitment — scheduled, hosted, repeated. Occasional lives do not work.
- **Related skills**: `marketplace-listings`, `creators-and-affiliates`, `paid-social`
