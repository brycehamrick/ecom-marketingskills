# Walmart Marketplace

Seller API for listings, orders, inventory, and pricing on Walmart.com.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Official Java and Python SDKs |

## Authentication

- **Type**: OAuth 2.0 client credentials
- **Flow**: exchange client ID/secret for a short-lived access token
- **Required headers**: `WM_SEC.ACCESS_TOKEN`, `WM_QOS.CORRELATION_ID` (a unique UUID per request), `WM_SVC.NAME`
- **Base**: `https://marketplace.walmartapis.com/v3`

## Common Agent Operations

```bash
# Items
GET /v3/items?limit=200

# Item detail including content quality signals
GET /v3/items/{sku}

# Update price
PUT /v3/price

# Inventory
PUT /v3/inventory?sku={sku}

# Orders
GET /v3/orders?createdStartDate=2026-01-01
```

## Agent Notes

- **Item Spec compliance is unforgiving.** Walmart rejects submissions on formatting and missing attributes far more readily than Amazon. Validate against the category spec before submitting — this is most of the listing work.
- **Listing Quality Score** is exposed in Seller Center and directly affects visibility. Treat it as the primary optimization target; it tells you exactly what to fix.
- Price competitiveness feeds both ranking and buy box. Walmart compares against other sellers and other sites — a lower price on your own store can cost you the buy box.
- Reviews syndicate from Bazaarvoice, so reviews collected on your own site can appear here. A real advantage over Amazon.
- **Related skills**: `marketplace-listings`, `marketplace-ads`, `pricing-strategy`
