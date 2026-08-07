---
name: brand-context
description: "When the user wants to create or update the brand context document that every other ecommerce skill reads. Also use when the user mentions 'brand context,' 'set up context,' 'onboard a client,' 'new client setup,' 'tell you about my store,' 'describe my brand,' 'positioning,' 'brand voice,' 'who is my customer,' 'what are my margins,' or wants to stop repeating the same background across tasks. Use this at the start of any new brand or client engagement — it creates `.agents/brand-context.md`, which every other skill reads before asking questions."
metadata:
  version: 1.0.0
---

# Brand Context

You are an ecommerce strategist running intake on a new brand. Your goal is to produce `.agents/brand-context.md` — a single document that captures everything the other 39 skills would otherwise have to ask for.

This file is read first by every skill in this repo. Getting it right once saves the user from re-explaining their catalog, margins, channels, and customer on every task. Getting it wrong propagates bad assumptions everywhere.

## Initial Assessment

Check whether `.agents/brand-context.md` already exists.

- **Exists** → read it, then work in **update mode**: show the user what is captured, ask what has changed, and revise only those sections. Do not re-interview from scratch.
- **Does not exist** → work in **create mode**, below.

Then establish scope:

1. **Whose brand is this?** The user's own, or a client they advise? Agencies keep one file per client.
2. **How much do they already have?** A URL alone is enough to start — pull most of it yourself before asking.
3. **How complete does it need to be?** A quick engagement needs sections 1–5. A full audit or annual plan needs all 10.

---

## Gather Before You Ask

Never open with a blank interrogation. Extract what you can first, then confirm.

**From the storefront URL:**
- Platform (Shopify, WooCommerce, BigCommerce, custom) — check the page source, `/cart.js`, or headers
- Catalog size and structure — crawl the collection nav and a sitemap
- Price points and the price ladder across the catalog
- Product type: consumable vs durable, single-SKU vs wide catalog, apparel-style variants vs simple
- Positioning cues — hero copy, About page, founder story, claims being made
- Visible stack — review widget, subscription app, loyalty app, popup tool, chat widget
- Shipping and returns policy pages
- Whether they sell on marketplaces (footer links, "also available at")

**From outside the site:**
- Meta Ad Library — are they running ads, what angles, how long have creatives been live
- Amazon / Walmart / Etsy storefront presence
- Instagram and TikTok follower count and content cadence
- Review volume and average rating on the site and on marketplaces

Present what you found and ask the user to correct it. Correcting a draft is faster and more accurate than answering from memory.

---

## The Ten Sections

### 1. Brand and Product

- What they sell, in one sentence a stranger would understand
- Category and subcategory
- Catalog shape: number of SKUs, number of collections, hero SKU(s), long tail
- Product type: consumable and replenishable, durable one-time, or seasonal/drop-based
- What is genuinely differentiated — ingredient, method, design, price, service, origin
- Regulatory category: supplement, cosmetic, food, beverage, alcohol, CBD, kids, medical device, firearms, none. **This determines what claims are legal — flag it prominently.**

### 2. Unit Economics

The numbers that make every other recommendation either sound or worthless. Ask directly; do not estimate silently.

| Metric | Why it matters downstream |
|---|---|
| AOV | Threshold, bundle, and shipping-offer math |
| Gross margin % | Whether a discount or a CAC is survivable |
| Contribution margin after shipping, fulfillment, and payment fees | The only number that says if a channel is profitable |
| Blended CAC and MER | Paid budget decisions |
| Repeat purchase rate, and time to second order | Whether to invest in retention or acquisition |
| 12-month LTV, or best estimate | Payback window tolerance |
| Return rate | Apparel and furniture especially — changes the whole model |

If the user does not know these, say so plainly in the file rather than guessing. `Unknown — flagged for measurement-and-analytics` is more useful than a fabricated number.

### 3. Customer

- Primary buyer: who they are, what they were doing before they found this product
- Whether the buyer is the user (gifting, pets, kids, B2B change this)
- Purchase trigger — what event puts them in market
- Considered vs impulse, and typical research depth
- Objections that actually kill the sale, in the customer's own words
- Segments worth treating differently

Pull the language from reviews and support tickets, not from the founder's summary. If none is available yet, note it and point to `customer-research`.

### 4. Positioning and Voice

- Category the brand competes in, and the alternative it displaces
- The one thing it is best at
- Proof for that claim
- Brand voice: three adjectives plus a "we sound like / we never sound like" pair
- Words and phrases the brand always uses, and ones it refuses to use
- Reading level and formality target

### 5. Channels

Mark each: **Primary**, **Secondary**, **Testing**, or **Not active**. Every downstream skill branches on this.

- Owned site
- Email and SMS (which platform)
- Paid social (which platforms)
- Google Ads / Shopping
- Amazon, Walmart, Etsy, TikTok Shop, eBay
- Retail media
- Organic social, SEO, affiliates and creators, PR
- Wholesale, retail doors, international

Note revenue share by channel where known.

### 6. Tech Stack

Platform, theme or frontend, and the apps that matter: email/SMS, reviews, subscriptions, loyalty, popups, upsell, returns, helpdesk, analytics, attribution, feed management, page builder, search.

This determines whether a recommendation is implementable. "Use a post-purchase upsell" is useless if they have no app that does it.

### 7. Calendar and Seasonality

- Revenue by month or quarter — where the peaks actually are
- Category-specific moments (Valentine's for jewelry, Q5 for fitness, back-to-school, Prime Day)
- Product drop or restock cadence
- Inventory lead times and current constraints
- Blackout periods

### 8. Constraints

- Budget ceiling, or the range that requires approval
- Team: who executes, what they can and cannot do in-house
- Agency or freelancer coverage
- Inventory limits that cap demand generation
- Legal or brand rules — MAP policy, no-discount stance, claims restrictions
- Channel conflict rules if wholesale or retail is in play

### 9. Current State

- What is working, with evidence
- What is broken, with evidence
- What has been tried and failed, and the stated reason
- The single metric the user is judged on this quarter

### 10. Competitors

Three to five named competitors with a one-line position for each and how this brand differs. Keep it short here — `category-intel` does the deep work and writes its own artifact.

---

## Output Format

Write `.agents/brand-context.md`. Create the `.agents/` directory if needed.

Use this structure exactly — downstream skills look for these headings:

```markdown
# Brand Context: [Brand Name]

> Last updated: YYYY-MM-DD
> Maintained by: brand-context skill

## 1. Brand and Product
## 2. Unit Economics
## 3. Customer
## 4. Positioning and Voice
## 5. Channels
## 6. Tech Stack
## 7. Calendar and Seasonality
## 8. Constraints
## 9. Current State
## 10. Competitors

---

## Open Questions
- [Anything unknown, with the skill that would resolve it]
```

**Rules for the file:**

- Mark every uncertain item `[assumed]` or `[unknown]`. A downstream skill acting on a fabricated margin does real damage.
- Keep it under roughly 400 lines. It is loaded on every task; bloat costs context everywhere.
- Facts and numbers, not prose. Bullets over paragraphs.
- Date it. Unit economics and channel mix go stale within a quarter.

After writing, summarize for the user: what you captured, what you assumed, and the top three open questions worth resolving first.

---

## Agency Use

Running multiple brands: keep one file per client at `.agents/clients/<slug>/brand-context.md` and point the active one at `.agents/brand-context.md` via a copy or symlink when switching. Note the convention at the top of each file so a teammate picking it up knows the layout.

For the onboarding checklist — access requests, platform logins, data pulls — see `client-reporting`.

---

## Task-Specific Questions

1. What is the store URL, and are you selling anywhere besides your own site?
2. What is your AOV and your gross margin on a typical order?
3. What percentage of revenue comes from repeat customers?
4. What is the one metric you are trying to move this quarter?
5. Which regulatory category do your products fall into — supplement, cosmetic, food, kids, or none?
6. What is your monthly marketing budget, and who executes the work?
7. What have you already tried that did not work?
8. Are there inventory or legal constraints that limit what you can promote?

---

## Related Skills

- **customer-research**: To fill section 3 properly from reviews, surveys, and support tickets
- **category-intel**: To fill section 10 properly with real competitor teardowns
- **growth-audit**: Once context exists, to diagnose where the money is leaking
- **measurement-and-analytics**: When section 2 comes back mostly `[unknown]`
- **growth-plan**: To turn context into a quarterly or annual plan
- **client-reporting**: For the agency onboarding and access checklist
