# Skio

Subscription platform for Shopify, built for headless and passwordless subscriber management.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | GraphQL |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | GraphQL client |

## Authentication

- **Type**: API key
- **Header**: `Authorization: {api_key}`

## Agent Notes

- GraphQL-first, which makes it easier to pull subscription state and cancellation reasons in one query than Recharge's REST pagination.
- **Cancellation reasons and save-offer acceptance are exposed.** These are the inputs to the cancel-flow optimization in `subscriptions-and-replenishment` — every reason should map to an alternative offer.
- Passwordless subscriber portal reduces friction on skip/pause/swap. Flexibility is retention: an easy skip prevents a cancel.
- Dunning configuration and account-updater status must be checked in the admin. Involuntary churn is the cheapest churn to fix.
- **Related skills**: `subscriptions-and-replenishment`, `retention-and-loyalty`
