# Feed Destinations

Requirements and quirks per destination. Specs change — verify against current documentation before implementation. The patterns and failure modes below are stable even when exact limits move.

---

## Google Merchant Center

The most demanding destination and the one whose rules are worth building to, because meeting Google's requirements generally satisfies everyone else.

**Required for all items:** `id`, `title`, `description`, `link`, `image_link`, `availability`, `price`, `brand`, and a product identifier (`gtin` or `mpn`). Apparel additionally requires `age_group`, `gender`, `color`, and `size`.

**Key behaviors:**

- **Automatic item updates** — enable them. They let Google correct price and availability from the landing page's structured data rather than disapproving the item. This alone eliminates the most common disapproval class
- **`google_product_category`** — use Google's own taxonomy and go as deep as the taxonomy allows. A shallow assignment costs matching precision
- **`item_group_id`** — groups variants. Without it, variants compete against each other and reporting is meaningless
- **`identifier_exists: false`** — only for genuinely unbranded or custom goods. Misusing it to dodge a missing-GTIN error suppresses matching and hurts performance
- **`custom_label_0` through `custom_label_4`** — the segmentation lever for campaign structure. Margin tier is the highest-value use
- **`sale_price` with `sale_price_effective_date`** — use these rather than editing `price`, so the strikethrough displays and the promotion is legible
- **Shipping and tax** — configure at the account level; supply item-level overrides only where a product genuinely differs

**Merchant Center policy is separate from Google Ads policy.** An item can serve in one and be suppressed in the other. Site-level requirements also apply: a visible returns policy, contact information, secure checkout, and clear pricing. Missing site policies suspend the whole account, not one item. See `claims-and-compliance`.

**The account-suspension causes worth knowing:** misrepresentation (unclear pricing, undisclosed subscription terms), missing site policies, and repeated unaddressed item-level violations.

---

## Meta Catalog

Powers Advantage+ catalog ads, dynamic retargeting, Shops, and Advantage+ Shopping campaigns.

**Requirements are lighter than Google's**, but performance still tracks data quality closely.

- Core fields: `id`, `title`, `description`, `availability`, `condition`, `price`, `link`, `image_link`, `brand`
- **Connect via the platform integration** (Shopify, WooCommerce) rather than a manual file where possible — it syncs availability and price far more reliably
- **Catalog health drives Advantage+ performance directly.** A broken catalog degrades ASC campaigns silently, presenting as a media problem
- Product sets are the segmentation unit. Build them from the same logic as Google custom labels
- Supply multiple images; Meta uses them in carousel and collection formats
- Meta pulls its own signal from the pixel — `content_id` in the pixel event **must** match the feed `id`, or catalog retargeting cannot function. This mismatch is common and completely invisible without checking

---

## Pinterest

- Catalog powers Shopping ads and organic product Pins, both of which persist and accumulate over time
- Requires `id`, `title`, `description`, `link`, `image_link`, `price`, `availability`
- Vertical imagery performs better here than square, unlike other destinations
- Pinterest indexes descriptions for search more than other feed destinations — descriptive, keyword-relevant copy earns more here than elsewhere
- Longer conversion windows; judge accordingly. See `paid-social` references

---

## TikTok

- Catalog powers Video Shopping Ads and Product Sales campaigns
- Standard fields; requirements close to Meta's
- **TikTok Shop is a separate system** from the TikTok Ads catalog. Selling in-app through TikTok Shop means product data, fulfillment, and fees run through TikTok's marketplace, not your store. See `marketplace-listings`
- Availability sync accuracy matters more than usual because TikTok traffic converts fast — a stale out-of-stock burns budget quickly

---

## Amazon

Not a feed in the same sense — a listing system with its own rules, its own taxonomy, and its own suppression logic.

- Product data flows via flat files, the Seller Central UI, or SP-API
- Category-specific browse-node requirements and required attributes vary widely by category
- **Backend search terms** are a separate field from the title and are one of the main keyword levers
- Restricted claim language causes suppression independent of any regulator
- Parent-child variation relationships are the equivalent of `item_group_id` and are handled differently

See `amazon-growth`.

---

## Walmart, Etsy, eBay, TikTok Shop

Each has its own item spec, taxonomy, and quirks. Walmart's Item Spec is notably strict and rejects on formatting. Etsy is tag- and attribute-driven with a different search model entirely.

See `marketplace-listings`.

---

## Cross-Destination Strategy

**One source of truth, many transformations.** Maintain complete, accurate product data in the platform or a PIM, then transform per destination with rules. Never maintain separate hand-edited feeds — they diverge within weeks and the divergence is invisible until something breaks.

**Sync frequency by volatility:**

| Catalog behavior | Minimum sync |
|---|---|
| Stable pricing, deep stock | Daily |
| Frequent price changes | Multiple times daily |
| Fast-moving or limited stock | Hourly, or real-time via API |
| During a promotion or peak season | Real-time. Stale prices during a sale cause disapprovals and angry customers |

**Attribute completeness is the single best predictor of feed performance across every destination.** Before optimizing bids, optimizing structure, or blaming the algorithm, measure what percentage of products have every applicable attribute populated. It is usually lower than anyone expects.
