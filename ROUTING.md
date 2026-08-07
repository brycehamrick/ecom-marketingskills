# Routing Contract

The `description` field in each `SKILL.md` is the **only** signal an agent uses to pick a skill. Collisions are decided by phrase overlap, not by the mental hierarchy in this document. This file is the single source of truth for who owns which job, so boundary sentences stay consistent as skills get edited independently.

**Rules:**

1. The **owner** of a job puts the user's exact phrasing in its description, near the front.
2. The **loser** of a collision puts an explicit negative pointer in its description: `For X, see <owner>.`
3. Boundary sentences are **reciprocal** — both skills reference each other.
4. Every skill that produces customer-facing copy carries: `For claims, disclosures, and channel policy, see claims-and-compliance.`

---

## The 40 skills by group

| Group | Skills |
|-------|--------|
| **A. Foundation & Research** | brand-context, customer-research, category-intel, growth-audit, claims-and-compliance |
| **B. Product & Merchandising** | product-pages, collection-merchandising, catalog-and-feeds, product-launch |
| **C. Offer & Economics** | pricing-strategy, promotions-and-discounting, bundles-and-aov, bfcm-and-peak-season |
| **D. Paid Acquisition** | paid-social, google-ads, marketplace-ads, ad-creative, creators-and-affiliates |
| **E. Organic Discovery** | ecommerce-seo, ai-search-visibility, organic-social, earned-media |
| **F. Marketplace & Channel** | amazon-growth, marketplace-listings, wholesale-and-retail, international-expansion |
| **G. Conversion** | site-cro, cart-and-checkout, post-purchase-experience, reviews-and-reputation, experimentation |
| **H. Lifecycle & Retention** | lifecycle-flows, email-sms-campaigns, list-growth, subscriptions-and-replenishment, retention-and-loyalty |
| **I. Measurement & Planning** | measurement-and-analytics, profitability-and-incrementality, growth-plan, client-reporting |

---

## Known collisions

Each row below must appear as a reciprocal sentence in **both** skills' descriptions.

### 1. Page conversion — `product-pages` vs `site-cro` vs `collection-merchandising` vs `cart-and-checkout`

`site-cro` will carry high-signal jargon ("CRO," "isn't converting," "low conversion rate") and will out-trigger the specific page skills unless they own their page nouns explicitly.

| Job | Owner |
|---|---|
| Product detail page — copy, images, variants, size/fit, specs, PDP cross-sell | `product-pages` |
| Collection / category / PLP — what appears, sort order, filters, badging | `collection-merchandising` |
| Homepage, navigation, site search, mobile, speed, sitewide trust, personalization | `site-cro` |
| Cart drawer, checkout, payment methods, shipping options, express pay | `cart-and-checkout` |

- **site-cro** carries: *"For product detail page conversion specifically, see product-pages. For collection and category pages, see collection-merchandising. For cart and checkout, see cart-and-checkout."*
- **product-pages** carries: *"For homepage, navigation, site search, or sitewide friction, see site-cro."*
- **product-pages** must front-load: *PDP, product detail page, product description, product photos, variant selector, size guide, "my product page isn't converting."*

### 2. Ad copy — `ad-creative` vs `paid-social`

| Job | Owner |
|---|---|
| Concepts, hooks, angles, scripts, UGC briefs, static/video specs, creative testing matrices, iterating off winners | `ad-creative` |
| Account structure, Advantage+/ASC, budget, bidding, audiences, CAPI, scaling and kill rules, diagnosing CPA/ROAS | `paid-social` |
| Creator whitelisting / Spark Ads (it is a media buy) | `paid-social` |

- **paid-social** carries: *"For ad concepts, hooks, scripts, UGC briefs, and creative testing, see ad-creative."*
- **ad-creative** carries: *"For campaign structure, budgets, bidding, audiences, and scaling, see paid-social. For Google Shopping and PMax assets, see google-ads."*

### 3. Free-shipping threshold — `promotions-and-discounting` vs `bundles-and-aov` vs `cart-and-checkout`

The threshold is an **offer and margin** decision.

- **Owner:** `promotions-and-discounting`
- **cart-and-checkout** carries: *"For the threshold and margin decision itself, see promotions-and-discounting."*
- **bundles-and-aov** carries: *"For discount depth and free-shipping thresholds, see promotions-and-discounting."*
- **promotions-and-discounting** carries: *"For how the cart merchandises progress toward a threshold, see cart-and-checkout. For what to sell alongside it, see bundles-and-aov."*

### 4. Email — `lifecycle-flows` vs `email-sms-campaigns`

The boundary is **automated/triggered** vs **scheduled/one-time**. Without this, `email-sms-campaigns` vacuums every prompt containing "email."

| Job | Owner |
|---|---|
| Welcome, browse abandon, cart abandon, checkout abandon, post-purchase, back-in-stock, replenishment, winback, VIP | `lifecycle-flows` |
| Campaign calendar, one-time sends, segmentation for a send, cadence, deliverability, list hygiene, sunset policy | `email-sms-campaigns` |

Both descriptions carry the boundary verbatim: *"lifecycle-flows owns automated triggered flows that run continuously; email-sms-campaigns owns one-time scheduled sends and the campaign calendar."*

### 5. Collection pages — `ecommerce-seo` vs `collection-merchandising`

Split by intent. This one collides constantly; the sentence must be in both.

- **ecommerce-seo** owns: ranking collection/category pages — faceted-nav indexation, category copy, internal links, schema, canonical strategy.
- **collection-merchandising** owns: what products appear and in what order — sort logic, curation, filters, badging, new-arrivals rotation, out-of-stock demotion.

### 6. Product feeds — `catalog-and-feeds` vs `google-ads` vs `paid-social`

- **Owner:** `catalog-and-feeds` — attributes, title formula, GTIN/Google product taxonomy, Merchant Center diagnostics and disapprovals, feed rules, supplemental feeds, multi-destination syndication, out-of-stock exclusions.
- **google-ads** carries: *"For feed attributes, product titles, and Merchant Center diagnostics, see catalog-and-feeds."*
- **paid-social** carries the same pointer for the Meta catalog.

### 7. Audits — `growth-audit` vs everything

`growth-audit` is a **triage router**, not a playbook. It produces a prioritized cross-surface findings list and hands off.

- **Triggers it owns:** *audit, teardown, health check, review my whole store, review my account, where are we losing money, first-90-days assessment.*
- **Explicitly excluded** from its description: *"why aren't we converting," "sales are down"* — those go to `site-cro` and `growth-plan` respectively, or it swallows both.

### 8. Q4 planning — `bfcm-and-peak-season` vs `product-launch` vs `growth-plan`

| Job | Owner |
|---|---|
| Calendar-anchored moments, promo cadence, inventory allocation, creative lead times, gifting | `bfcm-and-peak-season` |
| A single SKU or collection drop — waitlist, pre-order, seeding, sell-through target, restock | `product-launch` |
| Annual/quarterly budget, channel mix, targets, forecast, growth model | `growth-plan` |

"Launch our holiday collection" = launch mechanics from `product-launch`, calendar/inventory/offer cadence from `bfcm-and-peak-season`.

### 9. Reviews — `customer-research` vs `reviews-and-reputation` vs `product-pages`

- `customer-research` **mines** reviews for voice-of-customer and messaging.
- `reviews-and-reputation` owns **collection mechanics, display, syndication, response, and ratings recovery**.
- `product-pages` **consumes** both.

Stated in all three.

### 10. The numbers — `measurement-and-analytics` vs `profitability-and-incrementality`

Both read as "the numbers skill." Hard split:

| Job | Owner |
|---|---|
| Tracking plan, GA4 ecommerce events, Shopify analytics, server-side tagging, CAPI, consent mode, UTM taxonomy, dashboards, KPI definitions | `measurement-and-analytics` |
| MER / blended ROAS, contribution margin, CAC:LTV, geo holdouts, incrementality tests, post-purchase surveys, platform-vs-GA4 discrepancy, marketplace fee math | `profitability-and-incrementality` |

- **measurement-and-analytics** carries: *"For MER, contribution margin, and incrementality testing, see profitability-and-incrementality."*
- **profitability-and-incrementality** owns *"is my Meta ROAS real."*

### 11. Retention — `retention-and-loyalty` vs `lifecycle-flows` vs `subscriptions-and-replenishment`

- `retention-and-loyalty` owns **program design**: points, tiers, VIP, customer referral, repeat-rate strategy, RFM, cohort analysis.
- `lifecycle-flows` owns **the messages that execute it**.
- `subscriptions-and-replenishment` owns **subscription mechanics**: subscribe-and-save design, skip/pause/cancel save flows, dunning, subscription upsell.

### 12. Marketplaces — `amazon-growth` vs `marketplace-listings` vs `marketplace-ads`

- `amazon-growth` owns **everything Amazon that is not an ad buy**: A9/A10 keywords, listing content, A+/Premium A+, Brand Story, Storefront, Vine, coupons and deals, Buy Box, suppression and account health, FBA unit economics.
- `marketplace-listings` owns **Walmart, Etsy, TikTok Shop, and eBay** listings.
- `marketplace-ads` owns **the ad buy** on Amazon (SP/SB/SD), Walmart Connect, Instacart, and Criteo — ACOS, TACoS, bidding, placement.

---

## Compliance pointer

These skills produce customer-facing copy and **must** carry `For claims, disclosures, and channel policy, see claims-and-compliance.`

`product-pages` · `ad-creative` · `lifecycle-flows` · `email-sms-campaigns` · `marketplace-listings` · `amazon-growth` · `creators-and-affiliates` · `collection-merchandising` · `earned-media` · `organic-social` · `list-growth`

---

## Routing fixture

Verify by issuing each prompt cold in a fresh session with the plugin installed, and recording which skill triggers. A mismatch is a **description** fix, not a body fix.

| # | Prompt | Expected skill |
|---|--------|----------------|
| 1 | "my product page isn't converting" | `product-pages` |
| 2 | "rewrite this product description" | `product-pages` |
| 3 | "write me 10 ad hooks for this product" | `ad-creative` |
| 4 | "my Meta CPA doubled this week" | `paid-social` |
| 5 | "should I do free shipping over $75" | `promotions-and-discounting` |
| 6 | "set up an abandoned cart email" | `lifecycle-flows` |
| 7 | "plan our November sends" | `email-sms-campaigns` |
| 8 | "our Klaviyo open rates tanked" | `email-sms-campaigns` |
| 9 | "my Google Shopping feed has disapprovals" | `catalog-and-feeds` |
| 10 | "how should I structure PMax" | `google-ads` |
| 11 | "audit my store" | `growth-audit` |
| 12 | "my Amazon listing got suppressed" | `amazon-growth` |
| 13 | "my ACOS is too high" | `marketplace-ads` |
| 14 | "optimize my Etsy listings" | `marketplace-listings` |
| 15 | "how do I get into Faire" | `wholesale-and-retail` |
| 16 | "we want to launch in the UK" | `international-expansion` |
| 17 | "is my Meta ROAS real" | `profitability-and-incrementality` |
| 18 | "set up GA4 ecommerce tracking" | `measurement-and-analytics` |
| 19 | "can I say this supplement boosts immunity" | `claims-and-compliance` |
| 20 | "plan BFCM" | `bfcm-and-peak-season` |
| 21 | "grow my email list" | `list-growth` |
| 22 | "build a product finder quiz" | `list-growth` |
| 23 | "our repeat purchase rate is flat" | `retention-and-loyalty` |
| 24 | "people keep cancelling their subscription" | `subscriptions-and-replenishment` |
| 25 | "monthly report for a client" | `client-reporting` |
| 26 | "what should our collection page sort order be" | `collection-merchandising` |
| 27 | "our category pages don't rank" | `ecommerce-seo` |
| 28 | "get us into ChatGPT's answers" | `ai-search-visibility` |
| 29 | "pitch us to holiday gift guides" | `earned-media` |
| 30 | "how do we get more reviews on our PDPs" | `reviews-and-reputation` |
| 31 | "where do we cut spend next quarter" | `growth-plan` |
| 32 | "should we raise prices" | `pricing-strategy` |
| 33 | "build a bundle to raise AOV" | `bundles-and-aov` |
| 34 | "our returns rate is killing us" | `post-purchase-experience` |
| 35 | "find creators to seed product to" | `creators-and-affiliates` |

## Paraphrase fixture

The fixture above uses the trigger phrases written into the descriptions, so it mostly tests self-consistency. **This one is the real test:** every prompt is phrased the way an operator would actually type it, deliberately avoiding the vocabulary in any trigger list.

A miss here means the description is missing words real people use. Run `node .github/scripts/check-routing.js` to check both suites.

| # | Prompt | Expected skill |
|---|--------|----------------|
| 1 | "nobody is buying the thing once they land on it" | `product-pages` |
| 2 | "shoppers bail when they see the delivery charge" | `cart-and-checkout` |
| 3 | "we ship a supplement, is it ok to mention it helps you sleep" | `claims-and-compliance` |
| 4 | "half our orders come back" | `post-purchase-experience` |
| 5 | "everyone buys once and vanishes" | `retention-and-loyalty` |
| 6 | "folks sign up for texts but we never message them" | `lifecycle-flows` |
| 7 | "what do I put in the newsletter next month" | `email-sms-campaigns` |
| 8 | "nobody joins our mailing list" | `list-growth` |
| 9 | "our thing costs too little I think" | `pricing-strategy` |
| 10 | "customers wait for the sale before ordering" | `promotions-and-discounting` |
| 11 | "how do I get people to buy two instead of one" | `bundles-and-aov` |
| 12 | "Q4 is coming and we have nothing ready" | `bfcm-and-peak-season` |
| 13 | "Facebook is eating money and returning nothing" | `paid-social` |
| 14 | "need fresh video ideas for our reels ads" | `ad-creative` |
| 15 | "our items are missing from the shopping tab" | `catalog-and-feeds` |
| 16 | "Amazon pulled our page down" | `amazon-growth` |
| 17 | "we sell on Etsy and nobody finds us" | `marketplace-listings` |
| 18 | "boutiques keep asking for a price list" | `wholesale-and-retail` |
| 19 | "customers in Britain want to order" | `international-expansion` |
| 20 | "our category pages get no traffic from search" | `ecommerce-seo` |
| 21 | "when people ask chatgpt for a recommendation we never come up" | `ai-search-visibility` |
| 22 | "we want to be in a holiday roundup article" | `earned-media` |
| 23 | "should we send free product to tiktok people" | `creators-and-affiliates` |
| 24 | "subscribers keep quitting after two boxes" | `subscriptions-and-replenishment` |
| 25 | "hardly anyone leaves us a star rating" | `reviews-and-reputation` |
| 26 | "is version A or version B actually better" | `experimentation` |
| 27 | "my numbers in shopify and google dont line up" | `measurement-and-analytics` |
| 28 | "after all the fees are we even making money" | `profitability-and-incrementality` |
| 29 | "where should the money go next quarter" | `growth-plan` |
| 30 | "what do I show the client at month end" | `client-reporting` |
| 31 | "give me the whole picture of whats wrong" | `growth-audit` |
| 32 | "what are the people who buy from us actually like" | `customer-research` |
| 33 | "who else sells this and what do they charge" | `category-intel` |
| 34 | "tell me about the brands stuff so I stop repeating myself" | `brand-context` |
| 35 | "which items show first when you click a category" | `collection-merchandising` |
| 36 | "we are putting out a new flavor next month" | `product-launch` |
| 37 | "the store feels slow and clunky on phones" | `site-cro` |
| 38 | "we post on instagram but nothing happens" | `organic-social` |
| 39 | "how do I bid on google shopping" | `google-ads` |
| 40 | "our amazon ad costs are out of control" | `marketplace-ads` |

**Threshold: 80%.** Do not tune descriptions to reach 100% — the checker is a bag-of-words proxy and a real agent matches semantically. Some of these ("our thing costs too little I think") carry no keyword signal at all and are unfixable by adding phrases; an LLM resolves them from meaning. Over-fitting to the checker can make descriptions worse in a live session.
