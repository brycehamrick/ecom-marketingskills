# AfterShip

Shipment tracking, branded tracking pages, and delivery notifications across carriers.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST v4 |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Official SDKs in several languages |

## Authentication

- **Type**: API key
- **Header**: `as-api-key: {key}`
- **Base**: `https://api.aftership.com/v4`

## Common Agent Operations

```bash
# Create a tracking
POST /trackings
{ "tracking": { "tracking_number": "...", "slug": "usps" } }

# Get tracking status
GET /trackings/{slug}/{tracking_number}

# List trackings with exceptions
GET /trackings?tag=Exception
```

## Agent Notes

- **The branded tracking page is the point.** Customers check tracking multiple times per order; sending them to the carrier gives that attention away. This is one of the cheapest wins in the `post-purchase-experience` skill and one of the least implemented.
- **Filter on `Exception` and `AttemptFail` tags for proactive outreach.** Contacting a customer about a stalled package before they notice converts a complaint into loyalty — and it is the main mechanism for reducing WISMO volume.
- Delivery notification webhooks are the correct trigger for review requests. Triggering on order date instead of delivery is the most common review-flow configuration error.
- Estimated delivery data supports showing a delivery date rather than a shipping speed at checkout.
- **Related skills**: `post-purchase-experience`, `lifecycle-flows`, `reviews-and-reputation`
