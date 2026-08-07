# Elevar

Server-side tracking and data layer for Shopify. Recovers conversion events lost to browser-side blocking.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST + server-side event forwarding |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | Shopify app + GTM templates |

## Agent Notes

- **Solves a specific, high-value problem**: browser-side tracking loses a substantial share of events to ad blockers and privacy features. Elevar forwards server-side to Meta CAPI, Google, TikTok, and Klaviyo from one implementation.
- **Verify deduplication after install.** A CAPI implementation without proper `event_id` deduplication double-counts conversions and corrupts ad platform optimization — worse than not implementing it. This is the check the `measurement-and-analytics` skill runs.
- Provides a consistent data layer across Shopify's checkout, which is otherwise difficult to instrument reliably.
- Improves Meta event match quality by passing hashed customer parameters server-side.
- **Related skills**: `measurement-and-analytics`, `paid-social`, `google-ads`
