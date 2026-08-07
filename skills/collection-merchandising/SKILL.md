---
name: collection-merchandising
description: "When the user wants to decide what products appear on a collection page and in what order. Also use when the user mentions 'collection page,' 'category page,' 'PLP,' 'product listing page,' 'sort order,' 'merchandising,' 'filters,' 'faceted navigation,' 'product badges,' 'new arrivals,' 'best sellers,' 'curation,' 'what should we feature,' 'out of stock products showing,' or 'people browse but don't click into products.' This skill owns what appears and in what order. For ranking collection pages in organic search — indexation, category copy, internal links, schema — see ecommerce-seo. For the product page itself, see product-pages. For claims and disclosures, see claims-and-compliance."
metadata:
  version: 1.0.0
---

# Collection Merchandising

You are an ecommerce merchandiser. Your goal is to get browsers into the right product page quickly by controlling what appears on collection pages and in what order.

Collection pages are the second-most-trafficked page type on most stores and the least deliberately managed. Nearly every store runs default sort order set once at launch and never revisited, which quietly buries the products that actually sell.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it before asking questions. Catalog size and shape (section 1) determine whether this is a curation problem or a filtering problem.

Identify:

1. **Catalog size** — under 30 SKUs is a curation problem; over 200 is a findability and filtering problem. The tactics barely overlap
2. **Collection type** — category, use case, audience, seasonal, sale, or new arrivals. Each has a different job
3. **Traffic source** — organic search collection pages need copy and internal links; paid and email traffic needs immediate relevance and no preamble
4. **Current behavior** — collection page click-through to PDP, bounce rate, whether visitors use filters, and where they enter the catalog

---

## Merchandising Framework

### 1. Sort Order (highest impact, lowest effort)

Default sort determines what most visitors ever see. The first row on mobile is roughly two products.

**Sort logic that works, in rough priority:**

- **Revenue per view**, not units sold. A high-margin, high-converting SKU beats a cheap volume seller
- **Demote out-of-stock to the end** — never hide them entirely (they carry links and back-in-stock demand), but never let them occupy the first row
- **Boost new arrivals on collections where newness matters** (apparel, seasonal); ignore newness where it does not (staples, consumables)
- **Boost seasonal relevance** — actively, on a calendar. See `bfcm-and-peak-season`
- **Never sort by "featured" if nobody maintains it.** An unmaintained manual order is worse than an automated one

**Rules to set explicitly:**
- What happens to a SKU that goes out of stock
- What happens to a SKU on deep discount — surfacing it raises conversion and lowers margin; decide deliberately
- Whether the hero SKU is pinned first or has to earn it

**Sort options offered to the user** should be short: Featured, Best Selling, Price low→high, Price high→low, Newest. More options than that go unused.

### 2. Filters and Faceted Navigation

Filters matter above roughly 40 SKUs and become critical above 150.

**Filter on what buyers decide with**, not on how the catalog is organized internally. Skin type, hair type, size, fit, occasion, dietary attribute, room, and compatibility are decision filters. "Product line" and "collection" usually are not.

- Filters must be visible on mobile — a hidden filter is an unused filter. Show the count of active filters
- Show result counts per filter value; suppress values that return zero
- Never let a filter combination return an empty page. Return nearest matches with an explanation
- Multi-select within a facet, AND across facets

**The SEO trap:** filter combinations generate URLs. Left uncontrolled they produce thousands of thin, near-duplicate indexed pages that dilute crawl budget and cannibalize the collection page itself. Decide which facet combinations are worth an indexable page and block the rest. This is a coordination point — see `ecommerce-seo` for the indexation rules.

### 3. Product Cards

The card is the entire pitch. Buyers decide from it in under a second.

- **Image**: consistent aspect ratio and crop treatment across the collection. Inconsistency reads as unprofessional and breaks scanning
- **Secondary image on hover or swipe** — an in-use or alternate angle. One of the cheapest CTR improvements available
- **Rating and review count** — high-value, frequently omitted
- **Price**, with the compare-at price only when the discount is real. See `claims-and-compliance` for reference-price rules
- **Variant swatches on the card** when color is the primary decision. Do not make people click in to discover the color exists
- **One badge maximum.** Badge inflation destroys badge meaning
- **Quick add** for simple products; send varianted products to the PDP rather than forcing a variant choice in a cramped modal

### 4. Badges

Badges work because they carry information, and stop working the moment they are everywhere.

Useful: Best Seller, New, Low Stock (only if true — see `claims-and-compliance`), Back in Stock, Bundle and Save, a genuine award or certification.

Rules: at most one badge per card, at most ~20% of a collection badged, and every badge earned by a rule rather than assigned by hand.

### 5. Curation and Collection Design

**The collection set itself is a merchandising decision.** Most stores have collections that mirror their internal catalog structure rather than how customers shop.

Build collections around how buyers actually search and shop:
- By use case ("for sensitive skin," "for small spaces")
- By audience ("for beginners," "gifts for him")
- By occasion or season
- By problem ("frizz control," "back pain")

These outperform structural collections both for conversion and for organic search, because they match query intent.

**Collection page top content:** two to three lines above the grid that confirm the visitor is in the right place, plus filters. Long SEO copy belongs **below** the grid — pushing products down to make room for text costs more than the ranking is worth. See `ecommerce-seo`.

**Empty and thin collections** are worse than no collection. Under roughly six products, merge it or turn it into a landing page.

### 6. Out-of-Stock and Inventory-Aware Merchandising

Inventory reality should drive merchandising automatically, not through someone remembering:

- Out-of-stock SKUs sort last, keep their page, and offer back-in-stock capture → `lifecycle-flows`
- Low-stock SKUs get demoted in paid campaigns and excluded from feeds before they sell out → `catalog-and-feeds`
- Overstocked SKUs get boosted in sort and considered for a bundle → `bundles-and-aov`
- Discontinued SKUs redirect to the closest alternative, never to a 404 or the homepage

### 7. Personalization and Site Search

- Recently viewed on collection pages is cheap and reliably positive
- Recommended-for-you is worth it above roughly 100 SKUs; below that, curation beats an algorithm
- **Site search deserves merchandising attention**: searchers convert at multiple times the site average. Audit zero-result queries — they are a catalog gap list and a synonym list. Pin results for high-intent queries. Make sure search covers synonyms and the words customers use rather than the words on the label

---

## Output Format

### Sort Order Rules
The explicit rule set per collection type, including out-of-stock, discount, and new-arrival handling. Written so someone can implement it in the platform or a merchandising app.

### Filter Specification
Which facets to expose per collection, in what order, with values — plus which combinations should be indexable and which blocked.

### Product Card Spec
Every element, its rule, and its data source. Badge rules and thresholds.

### Collection Architecture
Recommended collections to add, merge, or retire, with the shopping behavior each serves and the query intent it matches.

### Quick Wins
Ranked changes implementable this week without development work.

---

## Task-Specific Questions

1. How many SKUs, and how many collections?
2. What is the current default sort order, and when was it last changed?
3. What is the click-through rate from collection pages to product pages?
4. Do visitors use your filters? What percentage?
5. How do you handle out-of-stock products today?
6. What are your top site-search queries, and which return nothing?
7. Are collection pages an organic search entry point, or mostly internal navigation?

---

## Related Skills

- **ecommerce-seo**: For ranking collection pages, faceted-nav indexation, category copy, and schema
- **product-pages**: For the page this one sends traffic to
- **catalog-and-feeds**: For product data quality, which merchandising depends on
- **bundles-and-aov**: For merchandising bundles and multi-packs
- **bfcm-and-peak-season**: For seasonal merchandising calendars
- **site-cro**: For navigation and site search structure
- **lifecycle-flows**: For back-in-stock capture on out-of-stock products
