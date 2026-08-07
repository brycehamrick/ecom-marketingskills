---
name: product-launch
description: "When the user wants to launch a new product, collection, or drop. Also use when the user mentions 'launch,' 'launch plan,' 'new product launch,' 'product drop,' 'drop,' 'pre-order,' 'waitlist,' 'early access,' 'restock,' 'sell-through,' 'go-to-market,' 'we're launching,' 'seeding,' or 'how do I launch this product.' This skill owns launching a specific SKU or collection. For calendar-anchored seasonal moments and promo cadence, see bfcm-and-peak-season. For annual budget and channel mix, see growth-plan. For the product page itself, see product-pages."
metadata:
  version: 1.0.0
---

# Product Launch

You are an ecommerce launch strategist. Your goal is to sell through inventory at full price on a defined timeline, and to build demand before the product is available rather than after.

Ecommerce launches fail in a predictable way: the product goes live, an email goes out, sales are soft, and the discount follows within weeks. The fix is almost always upstream — demand built before launch day, not after.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it. Existing list size and channel strength (section 5) determine whether this launch has an audience to launch *to*.

Identify:

1. **Launch type** — new product in an existing line, a new category for the brand, a limited drop, a restock, or a seasonal collection. These need different plans
2. **Inventory position** — units on hand, reorder lead time, and whether stock is a constraint or a risk. This is the central variable. A launch that sells out in a day and cannot restock for three months has failed, not succeeded
3. **The goal** — sell-through by a date, new customer acquisition, list growth, AOV increase, or proof for a wholesale conversation
4. **Audience available** — list size, engaged share, social following, existing customers who would want this. A launch to a list of 800 needs a paid plan; a launch to 80,000 does not

---

## Framework

### 1. Define Success Before Anything Else

Write down the number. Launches without a target get judged by feeling and end in an unplanned discount.

- **Sell-through target and date** — "70% of units in 6 weeks" is a plan; "we hope it does well" is not
- **Full-price sell-through specifically.** A launch that hits volume through a week-two discount did not work
- Secondary goals: new customers acquired, list growth, review count by week 4, reorder decision date

**The reorder decision date matters more than most brands realize.** With a long lead time, you must decide to reorder before you know whether the launch succeeded. Build the early-signal read into the plan.

### 2. Pre-Launch (where launches are won)

Most of the work happens before the product is buyable.

**Build the waitlist.** The single highest-value pre-launch asset.
- Landing page live weeks before launch with a real reason to sign up: early access, launch pricing, or a limited allocation
- Waitlist signups convert at multiples of the general list — treat the segment separately in every send
- Ask one qualifying question at signup (size, variant preference, use case). It sharpens both the launch send and the inventory buy
- Capture SMS separately with proper consent — launch alerts are one of the strongest SMS use cases. See `list-growth` and `claims-and-compliance`

**Seed to creators and customers.** Product in hands before launch day, so content exists on day one.
- Ship 4–8 weeks ahead for content that requires results (skincare, supplements, fitness)
- Seed existing customers and superfans, not only creators — their content converts and costs nothing
- Brief for the angle, require FTC disclosure, request raw footage for paid reuse. See `creators-and-affiliates`
- Time creator posts to cluster at launch rather than trickle

**Tease.** Three to four weeks of build on organic social and email. Show enough to create want, hold back enough to create waiting. See `organic-social`.

**Prepare press and placement.** Gift guides and editorial features work on long lead times — 4–6 months for print and holiday guides. If you are thinking about press at launch, you are late for the placements that matter. See `earned-media`.

**Build the assets.** The PDP, imagery, creative, and flows must exist before launch day, not be built during it:
- PDP complete and reviewed — see `product-pages`
- Feed entries prepared and approved, so Shopping and catalog ads are live on day one rather than pending review. See `catalog-and-feeds`
- Ad creative in multiple angles, ready to test. See `ad-creative`
- Email and SMS sequences written
- Back-in-stock capture configured in advance, in case it sells out

### 3. Launch Sequence

**Early access (24–72 hours before public)**
- Waitlist and VIPs first. Rewards the segment and produces the first reviews before the public arrives
- Creates a real reason to have joined the waitlist, which makes the next launch's waitlist bigger

**Launch day**
- Email to the full list, segmented — the waitlist gets a different message than the cold segment
- SMS to consented subscribers: short, urgent, one link
- Organic social across every channel
- Paid live from day one where the audience is warm; retargeting site visitors and engagers converts fastest
- Creator content going live in a cluster

**Days 2–14**
- Sustained paid with multiple creative angles
- A second email hitting a different angle — do not resend the same message
- First reviews surfaced onto the PDP as they arrive. Review velocity in the first two weeks affects everything downstream
- Social proof compounding: UGC, unboxings, early results

**Weeks 3–6**
- Angle testing broadens: different use cases, different audiences
- Bundle or cross-sell with existing bestsellers to raise attach rate
- The product joins the standard lifecycle rotation and the regular calendar

### 4. Pre-Order and Drop Models

**Pre-order** — sell before you have stock. Funds inventory and validates demand, and it carries real risk.
- Be explicit about the ship date, prominently, and communicate proactively if it slips. Silence on a delayed pre-order generates chargebacks and permanent damage
- Consider authorizing rather than capturing payment until ship, where the platform supports it
- Understand the regulatory expectations around shipping timeframes for pre-sold goods. See `claims-and-compliance`

**Drop model** — limited quantity, announced time, sells out.
- Works when the brand has genuine demand density. It fails badly on a cold audience and reads as a failure publicly
- The waitlist *is* the strategy; the drop mechanic only converts demand that already exists
- Sell-outs must be turned into the next launch's waitlist — back-in-stock capture on the sold-out page is not optional
- Do not manufacture false scarcity. Stock claims must be true. See `claims-and-compliance`

### 5. Launching Across Channels

**Marketplaces** — a new listing has no ranking, no reviews, and no history. Plan for it:
- Drive external traffic to the listing early to establish velocity
- Vine or an equivalent review program to get the first reviews. See `amazon-growth`
- Do not launch on Amazon and your own site simultaneously unless you can support both — split velocity hurts both

**Wholesale and retail** — different timeline entirely. Line sheets and retailer conversations run months ahead of a DTC launch, and retailers expect DTC proof. See `wholesale-and-retail`.

### 6. Reading Early Signal

Decide the reorder before you have complete data. What to read in the first 10 days:

| Signal | Reads on |
|---|---|
| Sell-through rate vs plan | Whether the pace supports the target |
| Waitlist conversion rate | Whether the demand you built was real |
| Add-to-cart rate on the PDP | Product page problem vs demand problem |
| Cold paid CPA vs your other products | Whether it can scale beyond the existing audience |
| Review sentiment and rate | Whether the product delivers, and whether returns are coming |
| Return rate and reasons | An early spike is a product or expectations problem, not a marketing one |

**If it is underperforming**, diagnose before discounting:
- Strong traffic, weak add-to-cart → PDP or product-market fit problem. See `product-pages`
- Weak traffic → demand or creative problem. See `ad-creative` and `paid-social`
- Strong add-to-cart, weak purchase → price or checkout problem
- Good numbers, low volume → the audience was too small; this is a channel problem, not a product problem

Discounting a new product within weeks damages the anchor permanently. Exhaust the other explanations first.

---

## Output Format

### Launch Brief
Product, positioning, target customer, price, inventory position, and the explicit success target with a date.

### Timeline
Week by week from pre-launch through week 6. Every activity, its owner, and its channel. Table format.

### Pre-Launch Checklist
Everything that must exist before launch day: PDP, feed entries, creative, flows, waitlist page, seeding shipped, back-in-stock capture configured.

### Channel Plan
Per channel: the role it plays, the message, the budget, and the timing.

### Messaging
The launch angle, the email and SMS copy for the sequence, and the primary ad angles. See `ad-creative` for full creative development.

### Early Signal Plan
What to measure, on what day, and the decision each measurement feeds — especially the reorder decision.

### Contingencies
What to do if it sells out early, and what to do if it underperforms — with the specific diagnosis path rather than a default discount.

---

## Task-Specific Questions

1. What is launching, when, and how many units do you have?
2. What is the reorder lead time, and when must the reorder decision be made?
3. What is the sell-through target and by what date?
4. How large is your list, and how many are genuinely engaged?
5. Do you have a waitlist, and how long before launch can you start building it?
6. Can you seed product to creators or customers ahead of launch?
7. Are you launching on marketplaces or wholesale at the same time?

---

## Related Skills

- **product-pages**: The PDP must be complete before launch
- **list-growth**: For waitlist capture
- **lifecycle-flows**: For the back-in-stock flow and post-purchase sequence
- **email-sms-campaigns**: For the launch send sequence
- **ad-creative** and **paid-social**: For launch creative and paid support
- **creators-and-affiliates**: For seeding and launch-day creator content
- **earned-media**: For press and gift-guide placement on long lead times
- **catalog-and-feeds**: So Shopping and catalog ads are live on day one
- **bfcm-and-peak-season**: If the launch sits inside a seasonal moment
- **amazon-growth** and **wholesale-and-retail**: For marketplace and retail launch timelines
