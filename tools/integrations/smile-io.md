# Smile.io

Loyalty, rewards, and referral program platform for Shopify and BigCommerce.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: API key
- **Header**: `Authorization: Bearer {api_key}`
- **Base**: `https://api.smile.io/v1`

## Common Agent Operations

```bash
# Customers with point balances and tier state
GET /customers?limit=100

# Points transactions
GET /points_transactions?customer_id={id}

# Referrals
GET /referrals
```

## Agent Notes

- **Point balances and tier state are useful RFM inputs.** Join them to purchase data for the segmentation the `retention-and-loyalty` skill builds.
- **Model the liability.** Points are an accrued cost. Pull outstanding balances and redemption rate before recommending a richer program.
- The key diagnostic: does the program change behavior, or reward behavior that was already happening? Compare repeat rate of enrolled versus non-enrolled customers, controlling for the fact that engaged customers self-select into enrollment.
- Referral module is customer-to-friend, which is distinct from affiliate — see `creators-and-affiliates` for the difference.
- **Related skills**: `retention-and-loyalty`, `lifecycle-flows`
