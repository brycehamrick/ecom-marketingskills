# Gorgias

Ecommerce helpdesk. Ticket data is a primary voice-of-customer source and a pre-purchase conversion surface.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: HTTP Basic
- **Header**: `Authorization: Basic base64(email:api_key)`
- **Base URL**: `https://{subdomain}.gorgias.com/api`
- **Get key**: Settings → REST API

## Common Agent Operations

```bash
# List tickets
GET /api/tickets?limit=100&order_by=created_datetime:desc

# Filter by tag
GET /api/tickets?tags=pre-purchase

# Ticket messages (the actual customer language)
GET /api/tickets/{id}/messages

# Customers
GET /api/customers?limit=100
```

## Agent Notes

- **This is the highest-signal VOC source most brands never mine.** Pre-purchase tickets are objections in raw form; the top 20 by volume become PDP FAQ content.
- Post-purchase tickets reveal expectation gaps — where marketing promised something the product delivered differently.
- **WISMO measurement**: tag or classify "where is my order" tickets and track them per 100 orders. This is the metric the `post-purchase-experience` skill manages against.
- Export ticket bodies in bulk for language-bank analysis rather than reading through the UI.
- **Related skills**: `customer-research`, `post-purchase-experience`, `product-pages`
