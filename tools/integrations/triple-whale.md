# Triple Whale

Ecommerce analytics and attribution platform. Consolidates ad spend, revenue, and margin into blended reporting.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: API key
- **Header**: `x-api-key: {key}`
- **Get key**: Triple Whale settings → API keys

## Agent Notes

- **Its main value is MER and blended reporting in one place** — the metric the `profitability-and-incrementality` skill manages against, because it cannot be gamed by attribution settings.
- **Treat its attribution model as one opinion, not truth.** Pixel-based post-purchase attribution is better than platform-reported ROAS and still not incrementality. Use it for directional allocation; use geo holdouts for the actual incrementality question.
- Supports COGS and shipping cost inputs — populate them. Without them the "profit" figures are gross revenue with a different label.
- The post-purchase survey feature is a genuinely useful attribution cross-check and feeds `customer-research`.
- **Related skills**: `profitability-and-incrementality`, `measurement-and-analytics`, `client-reporting`
