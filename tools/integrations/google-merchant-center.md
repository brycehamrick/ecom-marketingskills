# Google Merchant Center

Product feed management for Google Shopping, Performance Max, and free listings. Content API for Shopping.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | Content API for Shopping / Merchant API |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Google API client libraries |

## Authentication

- **Type**: OAuth 2.0 or service account
- **Scope**: `https://www.googleapis.com/auth/content`
- Service accounts must be granted access in Merchant Center under Users.

## Common Agent Operations

```bash
# List products
GET /content/v2.1/{merchantId}/products

# Product status — this is where disapprovals live
GET /content/v2.1/{merchantId}/productstatuses/{productId}

# Batch status (the efficient way to audit)
POST /content/v2.1/{merchantId}/productstatuses/batch

# Account-level issues
GET /content/v2.1/{merchantId}/accountstatuses/{accountId}
```

## Agent Notes

- **`productstatuses` is the first call in any feed audit.** It returns per-item disapprovals with the specific policy cited. The `catalog-and-feeds` skill treats clearing these as the fastest available revenue win.
- **Enable automatic item updates.** They let Google correct price and availability from landing page structured data instead of disapproving the item — this alone eliminates the most common disapproval class.
- **Merchant Center policy is separate from Google Ads policy.** An item can serve in one and be suppressed in the other.
- Account-level suspension causes: misrepresentation (unclear pricing, undisclosed subscription terms), missing site policies (returns, contact, secure checkout), and repeated unaddressed item violations.
- `custom_label_0` through `4` are the campaign segmentation lever. Margin tier is the highest-value use.
- **Related skills**: `catalog-and-feeds`, `google-ads`, `claims-and-compliance`
