# LoyaltyLion

Loyalty and referral platform, aimed at mid-market ecommerce with deeper tier and integration support.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: HTTP Basic with site token and secret
- **Base**: `https://api.loyaltylion.com/v2`

## Agent Notes

- Deeper tier support than lighter loyalty apps, and it integrates point state into Klaviyo for segmentation — that integration is what makes loyalty data usable in `lifecycle-flows`.
- Same liability caution as any points program: pull outstanding balance and redemption rate before enriching rewards.
- Non-discount rewards (early access, exclusive products, free shipping) are configurable and preferable to point-to-discount conversion, which is just a deferred discount program.
- **Related skills**: `retention-and-loyalty`, `lifecycle-flows`
