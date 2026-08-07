# Northbeam

Multi-touch attribution and media mix modeling for ecommerce. Aimed at brands at meaningful paid spend.

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

## Agent Notes

- Northbeam's models attempt to answer the incrementality question that last-click cannot. **Its output is a model, not measurement** — validate it against a geo holdout before making a large budget reallocation on it.
- Most useful for brands spending enough that channel-level misallocation is expensive. Below that, MER plus periodic holdout tests answer the same questions for free.
- Supports custom attribution windows and first-touch/last-touch comparison — useful for showing a client how much the reported number depends on the model chosen.
- **Related skills**: `profitability-and-incrementality`, `experimentation`, `paid-social`
