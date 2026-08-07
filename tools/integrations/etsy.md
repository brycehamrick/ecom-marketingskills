# Etsy

Open API v3 for listings, shop management, and orders on Etsy.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST v3 |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: OAuth 2.0 with PKCE
- **Headers**: `Authorization: Bearer {token}`, `x-api-key: {keystring}`
- **Base**: `https://openapi.etsy.com/v3/application`
- Scopes are granular (`listings_r`, `listings_w`, `shops_r`, `transactions_r`).

## Common Agent Operations

```bash
# Shop listings
GET /shops/{shop_id}/listings/active?limit=100

# Listing detail
GET /listings/{listing_id}

# Update listing (title, tags, attributes)
PATCH /shops/{shop_id}/listings/{listing_id}

# Listing images
GET /shops/{shop_id}/listings/{listing_id}/images
```

## Agent Notes

- **Tags are the primary ranking lever.** Thirteen slots — use all thirteen, all as multi-word phrases. Single-word tags waste a slot.
- Etsy is a search-and-discovery platform with its own model. **Do not port Amazon listing logic**; keyword stuffing is penalized here and natural-reading titles perform better.
- Attributes feed filters and search. Completeness matters more than on most marketplaces.
- **Photos carry more weight than anywhere else.** Ten slots, all used, first photo determines click-through from search.
- Off-site Ads commission is mandatory above a revenue threshold — model it into contribution margin.
- Policy restricts what may be sold (handmade, vintage, craft supplies). Mass-manufactured goods violate policy and the audience rejects them.
- **Related skills**: `marketplace-listings`, `pricing-strategy`
