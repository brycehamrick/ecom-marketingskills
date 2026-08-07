# Recharge

Subscription and recurring billing platform for Shopify and BigCommerce. Powers subscribe-and-save, skip/pause/swap, and dunning.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST, versioned via `X-Recharge-Version` header |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Community libraries; official Node and Python helpers |

## Authentication

- **Type**: API token
- **Header**: `X-Recharge-Access-Token: {token}`
- **Version header**: `X-Recharge-Version: 2021-11` (pin it; behavior differs across versions)
- **Get token**: Recharge admin → Apps → API tokens. Scope tokens to the minimum resources needed.

## Core Resources

| Resource | Use |
|----------|-----|
| `customers` | Subscriber identity, linked to the platform customer |
| `subscriptions` | The recurring line item — product, quantity, frequency, next charge date |
| `charges` | Upcoming and historical charges; where dunning state lives |
| `orders` | Orders generated from charges |
| `addresses` | Shipping address, and the grouping unit for charges |
| `discounts` | Subscription-specific discounts |
| `bundle_selections` | For build-a-box style subscriptions |

## Common Agent Operations

```bash
# List active subscriptions
GET https://api.rechargeapps.com/subscriptions?status=active&limit=250

# Subscriptions for one customer
GET https://api.rechargeapps.com/subscriptions?customer_id={id}

# Skip an upcoming charge
POST https://api.rechargeapps.com/onetimes/{charge_id}/skip

# Change frequency
PUT https://api.rechargeapps.com/subscriptions/{id}
{ "order_interval_frequency": "60", "order_interval_unit": "day" }

# Upcoming charges (dunning + forecasting)
GET https://api.rechargeapps.com/charges?status=queued
```

## Agent Notes

- **Churn analysis**: pull `subscriptions` with `cancelled_at` and `cancellation_reason`. Recharge captures the reason from the cancel flow — this is the roadmap referenced in the `subscriptions-and-replenishment` skill.
- **Involuntary churn**: `charges` with status `error` and the `error_type` field distinguish failed payments from active cancellations. Report these separately; they need dunning, not a save offer.
- **Dunning config** lives in the admin, not the API. Verify retry schedule and the account updater are enabled.
- Rate limits are per-store and tight. Batch and paginate with `limit=250`.
- **Related skills**: `subscriptions-and-replenishment`, `retention-and-loyalty`, `lifecycle-flows`
