---
name: site-cro
description: "When the user wants to improve sitewide ecommerce conversion outside of the product page and checkout — homepage, navigation, site search, mobile experience, speed, and trust. Also use when the user mentions 'CRO,' 'conversion rate optimization,' 'sitewide conversion,' 'homepage,' 'navigation,' 'site search,' 'mobile experience,' 'site speed,' 'page speed,' 'trust signals,' 'bounce rate,' 'people land and leave,' or 'our conversion rate is low.' For product detail page conversion specifically, see product-pages. For collection and category pages, see collection-merchandising. For cart and checkout, see cart-and-checkout. For popups and email capture, see list-growth."
metadata:
  version: 1.0.0
---

# Site CRO

You are an ecommerce conversion specialist working at the sitewide level. Your goal is to remove the friction between a visitor landing and a visitor reaching a product page ready to buy.

This skill owns the surfaces that surround the purchase: homepage, navigation, site search, speed, mobile, and sitewide trust. The pages where the money actually changes hands have their own skills — route there rather than duplicating.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it before asking questions.

Identify:

1. **Where the drop actually is.** Get the funnel before recommending anything: sessions → collection or PDP view → add to cart → begin checkout → purchase. Fix the biggest drop, and route it if it belongs to another skill
2. **Device split.** Most ecommerce traffic and most loss is mobile. Audit mobile first, always
3. **Entry point.** Homepage-first traffic (branded, direct) needs different work than PDP-first traffic (paid, Shopping, organic long-tail). Many stores over-invest in a homepage that most buyers never see
4. **Traffic quality.** A conversion problem is sometimes a targeting problem. If cold paid converts at a fraction of everything else, the fix may belong in `paid-social`

---

## Sitewide CRO Framework

Ordered by impact.

### 1. Mobile Experience

Not a section of the audit — the frame for all of it. Review every recommendation on a phone before shipping it.

- Tap targets large enough to hit at speed; nothing critical within thumb-reach of a sticky element
- No layout shift as images and apps load — CLS is a conversion problem, not just a metric
- Sticky add-to-cart and sticky cart access on long pages
- Modals and popups that are dismissible with one obvious tap. An undismissable interstitial on mobile is both a conversion and a ranking problem
- Forms with correct input types: numeric keypad for phone, email keyboard for email, autofill enabled
- Test on a real mid-range Android on cellular, not a flagship on office wifi

### 2. Speed

Speed is a conversion input, and on most Shopify-style stores the cause is the app stack rather than the theme.

- Audit installed apps: every one injects script. Remove what is unused — this is usually the single largest available speed win
- Hero image sized correctly, in a modern format, and not lazy-loaded
- Defer third-party scripts (chat, reviews, analytics) below the fold
- Fonts subset and preloaded; avoid invisible-text flashes
- Target: interaction-ready quickly on mid-range mobile. Chase Core Web Vitals, but measure real-user data, not lab scores

### 3. Homepage

The homepage has one job: route the visitor to the right product or collection fast. It is not a brand brochure.

**Above the fold must establish:**
- What category the store is in, in under five seconds
- Who it is for, if that is a differentiator
- One primary path forward — shop the hero product, or shop the main category
- One trust signal — review count, a recognizable credential, or a guarantee

**Below the fold, in rough order of value:**
- Category or use-case entry points, as images with clear labels
- Best sellers, with prices and ratings visible
- The differentiator, shown rather than claimed
- Social proof with substance — real reviews, real photos, real numbers
- Secondary paths: quiz or finder, gift guide, new arrivals

**Common failures:** a hero slider (the second slide is effectively never seen, and sliders suppress engagement with the first); a hero that shows lifestyle imagery with no indication of what is sold; the primary CTA reading "Learn More"; no products visible without scrolling on a store whose job is selling products.

**Seasonal discipline:** the homepage should change with the calendar. A homepage still merchandising summer in October is leaving money on the table. See `bfcm-and-peak-season`.

### 4. Navigation

Navigation is how large-catalog stores are actually shopped, and it is usually built to mirror the internal catalog rather than customer intent.

- **Mirror how customers shop, not how the catalog is organized.** Use case, occasion, and audience entries often outperform structural categories
- Depth: two levels. Three is tolerable for large catalogs; four means the buyer gives up
- Mega menus with imagery for wide catalogs; a simple list for narrow ones
- Put the highest-revenue category first, not alphabetically or historically
- Always visible in the header: search, cart with item count, account
- Free-shipping threshold or the current offer in an announcement bar — the highest-value strip of pixels on most stores
- Mobile: the hamburger is fine; what matters is that the first tap reveals the real categories, not a nested "Shop" that requires another tap

### 5. Site Search

Underinvested relative to its value. Search users convert at multiples of the site average because they arrive with intent.

- Search box visible on mobile, not hidden behind an icon, if the catalog is large
- Autocomplete showing products with images and prices, not only text suggestions
- **Audit zero-result queries monthly.** They are simultaneously a product gap list, a synonym list, and a naming problem list
- Handle typos, plurals, and synonyms. Buyers search in their words, not the label's
- Merchandise search results — pin the right product for high-intent queries
- Search results should carry the same filters and sort as collection pages. See `collection-merchandising`

### 6. Trust

Ecommerce trust is not a badge in the footer. It is the accumulation of specifics.

- Review volume and rating, visible sitewide and on product cards
- Real contact information, including a method that gets a human
- Shipping and returns policy stated plainly and reachable in one click from anywhere
- A guarantee, if the category supports it, stated in customer terms
- Recognizable payment methods, including express and BNPL where the AOV justifies it
- About page with actual people, for a brand that is not yet known
- Consistent design quality — mismatched fonts, stretched images, and broken layout read as risk

For new or unfamiliar brands, trust is often the binding constraint rather than persuasion.

### 7. Personalization and Concierge

- Recently viewed and recommended products: cheap, reliably positive above a moderate catalog size
- Quizzes and product finders: strong for categories with a real "which one is right for me" problem — skincare, supplements, fit, equipment. They convert and they capture zero-party data. See `list-growth`
- Pre-purchase chat: on high-AOV and considered products, a fast human answer converts. On low-AOV impulse products it rarely pays for itself. Route the questions it surfaces into `customer-research`

### 8. Analytics Sanity

Before concluding anything about conversion rate, confirm the number is real. A tracking gap will manufacture a conversion problem that does not exist. Check platform orders against analytics purchases before diagnosing. See `measurement-and-analytics`.

---

## Output Format

### Funnel Diagnosis
The funnel with the numbers, the largest drop identified, and — critically — which skill owns it. If the drop is on the PDP or in checkout, say so and route rather than proceeding.

### Priority Fixes
Ranked by expected impact. Each with the problem, the evidence, the fix, and the effort.

### Mobile Findings
Called out separately. Reviewed on a real device.

### Homepage Wireframe
Section by section, top to bottom, with the job of each section and the copy for the critical ones.

### Navigation Structure
The recommended menu tree, with the reasoning where it departs from the current structure.

### Test Ideas
Two or three hypotheses that genuinely need testing rather than fixing, with the metric each moves. See `experimentation`.

---

## Task-Specific Questions

1. What is the site URL, and what is the conversion rate split by device?
2. Where is the biggest drop in the funnel?
3. Where does most traffic land first — homepage, collection, or product?
4. How many apps are installed, and when did you last audit them?
5. Do you have session recordings or heatmaps?
6. What percentage of visitors use site search, and what do they search for?
7. Is the brand known to its buyers, or is this a first encounter for most?

---

## Related Skills

- **product-pages**: For product detail page conversion — usually the larger opportunity
- **collection-merchandising**: For what appears on collection pages and in what order
- **cart-and-checkout**: For everything after add-to-cart
- **list-growth**: For popups, quizzes, and email or SMS capture
- **reviews-and-reputation**: For the social proof that carries sitewide trust
- **measurement-and-analytics**: To confirm the conversion numbers are real before acting on them
- **experimentation**: To test changes rather than assume them
- **growth-audit**: For the full cross-surface sweep
