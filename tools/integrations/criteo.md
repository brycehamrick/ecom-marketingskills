# Criteo

Retail media and commerce advertising network, spanning retailer onsite placements and offsite retargeting.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | Retail Media API and Marketing Solutions API |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | ✓ | Official SDKs |

## Authentication

- **Type**: OAuth 2.0 client credentials

## Agent Notes

- Two distinct products: **retail media** (sponsored placements on retailer sites where you have distribution) and **offsite retargeting**.
- **Treat the retargeting product with the incrementality skepticism it deserves.** Retargeting networks show ads to people already intending to buy and then claim the conversion — this is exactly the spend category the `profitability-and-incrementality` skill flags. Run a holdout before scaling.
- Retail media placements are usually negotiated alongside the retailer relationship rather than bought purely self-serve.
- **Related skills**: `marketplace-ads`, `profitability-and-incrementality`, `wholesale-and-retail`
