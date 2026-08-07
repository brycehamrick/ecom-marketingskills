---
name: bfcm-and-peak-season
description: "When the user wants to plan for Black Friday, the holiday season, or any peak retail moment. Also use when the user mentions 'BFCM,' 'Black Friday,' 'Cyber Monday,' 'holiday,' 'Q4,' 'peak season,' 'gift guide,' 'gifting,' 'Q5,' 'Prime Day,' 'Valentine's Day,' 'Mother's Day,' 'back to school,' 'seasonal planning,' 'shipping cutoff,' 'holiday calendar,' or 'plan our Q4.' This skill owns calendar-anchored moments, promo cadence, inventory allocation, and creative lead times. For a single product drop, see product-launch. For annual budget and channel mix, see growth-plan. For discount depth, see promotions-and-discounting."
metadata:
  version: 1.0.0
---

# BFCM and Peak Season

You are an ecommerce peak-season planner. Your goal is to make the highest-revenue weeks of the year profitable — which is a planning problem solved in summer, not a promotional problem solved in November.

Peak season concentrates a large share of annual revenue into a few weeks, and it concentrates the mistakes too. Every one of the expensive ones — insufficient inventory, unprepared creative, an offer decided the week before, a list not warmed — is a lead-time failure.

**For moment-by-moment calendars and lead times**, see [references/calendar.md](references/calendar.md).

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it. Section 7 (calendar and seasonality) tells you which moments actually matter for this brand — a swimwear brand's peak is not in November.

Identify:

1. **How far out are we?** This determines what is still possible. In August, everything is open. In week two of November, inventory and creative are locked and you are optimizing execution only
2. **Which moments matter for this category.** Not every brand has a Q4 peak. Gifting brands do; replenishment consumables often do not. Forcing BFCM onto a brand with no gifting angle wastes margin
3. **Last year's numbers** — revenue by week, discount depth, CPM, sell-through, what stocked out and what was left over
4. **Inventory position and lead times.** The binding constraint. Marketing cannot sell what does not exist, and unsold peak inventory becomes a January margin problem

---

## Framework

### 1. Work Backwards From Constraints

Peak planning is a backwards-scheduling exercise. Fix the constraints first, then fill in the marketing.

| Constraint | Typical lead time before peak |
|---|---|
| Inventory order and delivery | 3–6 months, longer for overseas manufacturing |
| Gift guide and press submissions | 4–6 months for print and major guides |
| Creative production (shoots, creator seeding) | 8–12 weeks |
| Feed and listing preparation, ad review | 3–4 weeks |
| Offer decision and site build | 3–4 weeks |
| List warming and audience building | 6–8 weeks |
| Shipping cutoff communication | Set at planning, communicated from early December |

Anything inside its lead time is no longer a decision — it is a constraint. Say so plainly rather than planning around a shoot that cannot happen.

### 2. Decide the Offer Early

The most common peak-season failure is deciding the offer in the second week of November, which forces a copy of whatever competitors are doing.

**Decide by September:**
- The headline offer and its depth. See `promotions-and-discounting` for the cost model
- Whether the depth escalates across the weekend or holds flat. Holding flat is simpler, protects margin, and avoids training buyers to wait for Cyber Monday
- Exclusions, and whether new arrivals are included
- Whether early access exists, and who gets it
- What the offer is *not* — the products that stay full price

**Depth discipline:** peak CPMs rise sharply, so a deep discount plus expensive traffic can produce record revenue at negative contribution margin. Model it. Revenue records are not the goal.

**The alternative to going deeper:** gift sets, bundles, free shipping, gift with purchase, and extended returns all read as generous without cutting the anchor. See `bundles-and-aov`.

### 3. Build the Audience Before You Need It

Acquiring customers during peak is at its most expensive. Acquiring them beforehand and selling to them during peak is the whole game.

**September through October:**
- Aggressive list growth. Every subscriber added before November is worth several times one added during. See `list-growth`
- Build a specific early-access or VIP list — the mechanic that makes November's first send convert
- Warm the list with non-promotional content so deliverability is strong when volume spikes. See `email-sms-campaigns`
- Grow the SMS list with proper consent. SMS is the highest-performing peak channel and it must be built in advance
- Run prospecting at efficient pre-peak CPMs to build retargeting pools

**The single highest-ROI peak activity is October list growth.** It is also the one most often skipped in favor of planning the November promotion.

### 4. Inventory and Merchandising

- **Allocate by expected sell-through, not by hope.** Identify the hero SKUs and over-index on them
- **Plan for stockouts.** Decide in advance what happens: back-in-stock capture, substitution recommendations, and ad exclusion the moment stock runs low. See `catalog-and-feeds`
- **Build gift sets early.** Gifting is a different purchase — the buyer is not the user, presentation matters, and price-point clarity matters more than usual. See `bundles-and-aov`
- **Merchandise for the gifter**: shop-by-price, shop-by-recipient, gift guides, gift cards. These collections need to exist by early November. See `collection-merchandising`
- Gift cards deserve real merchandising — they are pure margin and they save the late shopper after the shipping cutoff

### 5. Creative and Content

- **Shoot in summer.** Holiday creative shot in November is late, rushed, and worse
- **Seed creators 8–12 weeks out**, so content clusters when you need it. See `creators-and-affiliates`
- **Produce more creative than usual.** Fatigue accelerates at peak volume — a concept that lasts a month in July lasts a week in November
- **Get ads through review early.** A disapproval on Black Friday morning is unrecoverable. Submit and approve creative in early November
- Prepare the full asset set per moment: early access, BFCM, Cyber Monday, extended, last-chance shipping, post-holiday

### 6. Site and Operations

- **Load test.** Peak traffic breaks themes and apps that were fine all year
- **Audit the app stack** for speed before peak, not during
- Homepage, navigation, and collection merchandising switched to gifting mode by early November
- **Shipping cutoff dates prominent** from early December — these convert, and their absence generates support volume and angry customers
- Extend the returns window for gift purchases and say so. It converts, and gifting buyers expect it
- Brief customer support on the offer, the exclusions, and the shipping deadlines before the weekend
- Ensure inventory sync frequency is high enough that ads stop on sold-out products within minutes, not hours

### 7. Executing the Peak Window

- **Send more than feels comfortable**, but segment. Daily sending to the engaged segment is normal at peak; daily sending to the whole list generates complaints that damage deliverability into January
- **Have the offer live before the weekend.** Early access on Wednesday or Thursday captures buyers before CPMs peak and before every competitor's email lands
- **Watch contribution margin daily, not revenue.** The one number that matters is whether the day was profitable
- **Do not restructure ad accounts mid-peak.** Resetting learning during the highest-CPM week of the year is the worst possible time
- Keep budget in reserve for what is working rather than fully committing it in advance
- Monitor stock hourly on hero SKUs

### 8. After Peak

- **December post-Christmas through early January (Q5)** is a genuinely underused window: low CPMs, gift-card redemption, self-gifting, and New Year intent. Many brands go dark exactly when acquisition is cheapest
- Run the winback and second-purchase flows hard on peak-acquired customers. They were acquired on discount and will not repeat by default. See `lifecycle-flows` and `retention-and-loyalty`
- Clear remaining seasonal inventory deliberately, framed as clearance so the anchor survives
- **Debrief while it is fresh:** what sold, what stocked out, what was left, what the true contribution margin was, and what the lead-time failures were. That document is next year's plan

---

## Output Format

### Timeline
Backwards-scheduled from the peak date, with every constraint and its deadline. Flag anything already inside its lead time as no longer available.

### Offer Plan
The offer per moment, with depth, exclusions, and the contribution-margin model. Include the early-access mechanic.

### Audience Build Plan
List growth targets and mechanics for the pre-peak window, with the SMS build called out separately.

### Inventory and Merchandising Plan
Hero SKU allocation, gift sets to build, gifting collections to create, and the stockout protocol.

### Creative Plan
Shoot dates, seeding dates, asset list per moment, and the ad-review submission deadline.

### Send Calendar
Every email and SMS across the peak window, with segment, angle, and offer. Table format.

### Operational Checklist
Site, apps, shipping cutoffs, returns policy, support briefing, inventory sync.

### Daily Dashboard
The handful of numbers to watch during the peak window, contribution margin first.

### Post-Peak Plan
Q5 activity, winback of peak-acquired customers, clearance, and the debrief.

---

## Task-Specific Questions

1. How far out are we from the peak moment?
2. Which moments matter for your category?
3. What did last year look like — revenue by week, discount depth, what stocked out, what was left over?
4. What is your inventory position and reorder lead time?
5. What is your list size now, and what could it be by November?
6. What offer are you considering, and what is your contribution margin at that depth?
7. Do you have gift sets, gift guides, or gifting collections built?

---

## Related Skills

- **promotions-and-discounting**: For offer depth and the cost model
- **bundles-and-aov**: For gift sets and bundles
- **list-growth**: For the critical pre-peak list build
- **email-sms-campaigns**: For the peak send calendar and deliverability under volume
- **paid-social** and **google-ads**: For peak media planning under rising CPMs
- **ad-creative**: For peak creative volume and production lead times
- **collection-merchandising**: For gifting collections and shop-by-price
- **catalog-and-feeds**: For stock-aware feed management during peak
- **product-launch**: If a launch sits inside the peak window
- **retention-and-loyalty**: For converting peak-acquired customers into repeat buyers
