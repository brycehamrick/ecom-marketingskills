# Omnisend

Email and SMS marketing platform for ecommerce, positioned below Klaviyo on price and complexity.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST v5 |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: API key
- **Header**: `X-API-KEY: {key}`
- **Base**: `https://api.omnisend.com/v5`

## Common Agent Operations

```bash
# Contacts
GET /contacts?limit=250

# Create or update contact
POST /contacts

# Custom events (for flow triggers)
POST /events
```

## Agent Notes

- Covers the twelve core flows in `lifecycle-flows`, with simpler segmentation than Klaviyo. Adequate for most brands below significant scale.
- Verify **exclusion conditions** on abandonment flows — purchase must exit the flow. Misconfigured exclusions are the most common and most damaging flow error on any platform.
- SMS requires the same express written consent, quiet hours, and STOP handling as any provider. See `claims-and-compliance`.
- **Related skills**: `lifecycle-flows`, `email-sms-campaigns`, `list-growth`
