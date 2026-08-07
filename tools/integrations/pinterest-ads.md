# Pinterest Ads

Advertising API for Pinterest — Shopping ads, catalog, and standard campaigns.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST v5 |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Official SDKs |

## Authentication

- **Type**: OAuth 2.0
- **Base**: `https://api.pinterest.com/v5`

## Common Agent Operations

```bash
# Ad accounts
GET /v5/ad_accounts

# Campaigns
GET /v5/ad_accounts/{id}/campaigns

# Catalogs
GET /v5/catalogs

# Analytics
GET /v5/ad_accounts/{id}/analytics?start_date=...&end_date=...
```

## Agent Notes

- **Judge Pinterest on a 30-day window minimum.** Intent is planning-stage and conversion lags materially — a 7-day attribution window systematically understates it.
- **Keyword targeting carries real signal here**, unlike Meta. Pinterest functions partly as a visual search engine.
- Vertical static images compete with video, which is unusual among social platforms.
- Organic and paid compound — pins persist and accumulate reach rather than expiring in 48 hours.
- Strong fit for home, decor, apparel, wedding, food, DIY, and beauty; poor fit for most utility products.
- **Related skills**: `paid-social`, `catalog-and-feeds`, `organic-social`
