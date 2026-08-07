---
name: catalog-and-feeds
description: "When the user wants to fix product data, titles, attributes, or shopping feeds. Also use when the user mentions 'product feed,' 'shopping feed,' 'Merchant Center,' 'Google Merchant Center,' 'feed errors,' 'disapproved products,' 'my Google Shopping feed has disapprovals,' 'GTIN,' 'product titles,' 'product attributes,' 'catalog,' 'Meta catalog,' 'feed rules,' 'supplemental feed,' 'product taxonomy,' 'variants not showing,' or 'products not showing in Shopping.' This skill owns product data quality and feed syndication to every destination. For campaign structure and bidding, see google-ads and paid-social. For what appears on collection pages, see collection-merchandising."
metadata:
  version: 1.0.0
---

# Catalog and Feeds

You are an ecommerce product data specialist. Your goal is to make the product catalog machine-readable, so every downstream surface — Shopping, catalog ads, marketplaces, on-site search, and AI shopping assistants — can find and correctly represent the products.

Product data is infrastructure. When it is wrong, every channel underperforms simultaneously and the cause is invisible from inside any single channel. A brand debugging Shopping performance is frequently debugging a title problem.

**For destination-specific requirements**, see [references/destinations.md](references/destinations.md).

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it. Catalog size and complexity (section 1) determine whether this is a manual cleanup or a rules-and-automation problem.

Identify:

1. **Active destinations** — Google Merchant Center, Meta catalog, Pinterest, TikTok, marketplaces. Each has different requirements
2. **Current error state** — pull the diagnostics from every destination first. Disapprovals are the fastest available win and are frequently unnoticed
3. **Source of truth** — the platform product data, a PIM, a feed management tool, or spreadsheets. Fix the source, not the feed, or the fix regresses on the next sync
4. **Catalog complexity** — variant depth, number of attributes, how many SKUs change price or availability frequently

---

## Framework

### 1. Clear Disapprovals First

Free revenue, sitting idle. Every destination has a diagnostics view — start there.

**The recurring causes:**

| Error | Cause | Fix |
|---|---|---|
| Price mismatch | Feed price differs from the landing page | Enable automatic item updates; check currency and tax display |
| Availability mismatch | Feed says in stock, page says sold out | Sync frequency; automatic updates |
| Missing GTIN | No barcode supplied | Supply the real GTIN, or set the identifier-exists flag correctly for genuinely unbranded goods |
| Image issues | Placeholder, watermark, promotional text on image | Clean product image, no overlays |
| Policy violation | Restricted category or claim language | See `claims-and-compliance` |
| Landing page mismatch | URL 404s, redirects, or shows a different product | Fix the URL, including variant-level URLs |
| Missing required attribute | Category-specific requirement unmet | Apparel needs size, color, gender, age group |

**Promotional text on images is the most common self-inflicted disapproval.** Feed images must be clean product images. Sale badges belong in the ad, not on the asset.

### 2. Titles

The single highest-leverage element in the entire feed. Titles determine which queries a product matches in Shopping and marketplace search, and they usually outperform any bid adjustment available.

**Formula, front-loading what buyers search:**

```
Brand + Product Type + Key Attribute + Size/Count + Variant
```

- `Acme Vitamin C Serum 20% Brightening 30ml`
- `Nord Merino Wool Crew Socks Charcoal Size 9-11 3-Pack`

**Rules:**
- Front-load. Titles truncate, and the first several words carry most of the matching weight
- Use the words buyers use, not internal product names. "Renew" means nothing; "Vitamin C Serum" is searched
- Include the attributes buyers filter and search by: size, color, count, material, compatibility
- No promotional language. "Best," "Sale," and "Free Shipping" in a title cause disapproval
- Stay within destination limits, and make sure the meaningful content is in the visible portion

**The site title and the feed title can and often should differ.** The PDP title is written for humans; the feed title is written for a matching algorithm. Use feed rules to build the feed title from attributes rather than hand-editing.

### 3. Attributes

Every attribute you supply is a matching opportunity and a filter the platform can use.

**Supply everything applicable, not just the required minimum:**
- Identifiers: GTIN, MPN, brand — these are what merge your product with the platform's own product knowledge
- Category: use the destination's own taxonomy, mapped as specifically as possible. A vague category assignment costs matching precision
- Physical: color, size, material, pattern, dimensions, weight
- Merchandising: sale price with effective dates, shipping, and item group ID
- Category-specific: apparel needs age group, gender, and size system; food needs ingredients and nutrition where required

**Variant handling** is the most common structural error. Group variants with a shared item group ID so the platform understands they are one product in different forms — otherwise variants compete against each other in the same auction and the reporting is unusable.

### 4. Images

- Clean product on a plain background as the primary image, no overlays or watermarks
- Supply additional images — most destinations use them, and richer imagery improves performance
- Correct image per variant. A red variant showing the blue product is a conversion and returns problem
- Meet the resolution minimums; higher resolution generally performs better
- Keep the feed's primary image consistent with the PDP's primary image. A mismatch between the ad and the landing page hurts conversion and can trigger review. See `product-pages`

### 5. Feed Rules and Supplemental Feeds

Do not hand-edit the feed. Hand edits regress on every sync.

- **Feed rules** transform data at the destination: build titles from attributes, map categories, set defaults, exclude products
- **Supplemental feeds** layer data onto the primary feed without touching the source — the right tool for custom labels, promotional IDs, and manual overrides
- **Custom labels** are the main segmentation lever for campaign structure. Populate them with what you actually want to bid differently on: margin tier, seasonality, bestseller status, stock level, price band. See `google-ads`

**Custom labels by margin tier** is the highest-value use of this feature, because it lets bidding reflect profitability rather than revenue.

### 6. Inventory-Aware Feed Management

The feed should reflect inventory reality automatically, not through someone remembering.

- **Exclude out-of-stock products** from ads. Paying for clicks on unbuyable products is pure loss
- **Exclude low-stock products** before they sell out, especially if the ad platform's pacing will burn through the remaining units in hours
- **Exclude zero-margin or clearance items** from campaigns where they will absorb budget
- Update availability at high frequency for fast-moving catalogs — daily sync is not enough during a promotion or a peak period
- Reinstate automatically on restock, and pair with back-in-stock capture on the PDP. See `lifecycle-flows`

### 7. Feed Quality as AI Search Infrastructure

Structured product data increasingly feeds AI shopping assistants and agentic commerce surfaces, not just ad platforms. The same discipline serves both.

- Complete, accurate attributes make products legible to systems that summarize and compare
- Valid `Product` schema on the PDP, consistent with the feed. See `ecommerce-seo`
- Clear availability, price, and shipping data
- Structured, factual product descriptions rather than pure marketing prose

See `ai-search-visibility`.

### 8. Monitoring

Feed problems are silent. Build the routine:

- **Weekly:** disapproval count by destination, and any new error types
- **Weekly:** count of active products versus expected — a sudden drop is the highest-priority alert in this entire skill
- **Monthly:** title quality audit on top-revenue SKUs; attribute completeness rate
- **On every catalog change:** verify the feed picked it up
- Alert on active-product-count drops, not just on error counts

---

## Output Format

### Error Report
Every disapproval and warning by destination, grouped by cause, with the fix and the revenue at stake. Ranked — this section is usually the largest immediate win.

### Title Audit and Rewrites
Current title, recommended title, and the reasoning, for top-revenue SKUs. Plus the formula and the feed rule to apply it catalog-wide.

### Attribute Gap Analysis
Which attributes are missing, on how many products, and the impact of each gap.

### Feed Rule Specification
The rules to create, written so they can be built directly in the destination: title construction, category mapping, exclusions, custom labels.

### Custom Label Scheme
What each label slot holds and how campaigns should use it. Coordinate with `google-ads`.

### Monitoring Plan
What to check, how often, and the alert thresholds.

---

## Task-Specific Questions

1. Which destinations do you feed — Merchant Center, Meta, Pinterest, TikTok, marketplaces?
2. How many products are disapproved right now, and for what reasons?
3. Where does product data live — platform, PIM, feed tool, or spreadsheets?
4. How are your product titles constructed today?
5. Do you have GTINs for all products?
6. How do you handle out-of-stock products in ad campaigns?
7. How frequently does the feed sync, and does it handle price and stock changes fast enough?

---

## Related Skills

- **google-ads**: For Shopping and PMax campaign structure that consumes this feed
- **paid-social**: For Meta catalog and Advantage+ campaigns
- **product-pages**: For PDP consistency with feed titles and images
- **collection-merchandising**: For the on-site use of the same product data
- **marketplace-listings** and **amazon-growth**: For marketplace-specific product data
- **ecommerce-seo**: For Product schema consistency with the feed
- **ai-search-visibility**: For structured data as AI shopping infrastructure
- **claims-and-compliance**: For Merchant Center policy and restricted-category disapprovals
