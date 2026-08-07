# Rebuy

Personalization and merchandising engine for Shopify — cross-sell, upsell, post-purchase offers, and smart cart.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | JS widget + HTTP API |

## Authentication

- **Type**: API key
- **Base**: `https://rebuyengine.com/api/v1`

## Agent Notes

- **Post-purchase one-click upsell is the highest-ROI mechanic Rebuy provides.** It runs after payment, so it cannot cost the original conversion — the point made in `bundles-and-aov` and `cart-and-checkout`.
- Smart cart supports free-shipping threshold progress with a **specific gap-closing product suggestion**, which outperforms a bare "you're $12 away" message.
- Recommendation sources matter: bought-together data beats algorithmic similarity. Configure rules rather than accepting defaults — "similar to what you're buying" recommends a competitor to yourself.
- Never place a cross-sell above the primary add-to-cart. Rebuy makes this easy to do and it costs conversions.
- **Related skills**: `bundles-and-aov`, `cart-and-checkout`, `product-pages`
