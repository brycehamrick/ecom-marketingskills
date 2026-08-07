# Benchmarks and Scoring Rubric

Reference ranges for grading an ecommerce brand. **Use these as conversation starters, not verdicts.** Benchmarks vary enormously by category, price point, traffic mix, and season. A brand below a range is not automatically broken; a brand above it is not automatically healthy.

Always prefer the brand's own trend over any external benchmark. "Down 30% from your own Q1" is a stronger finding than "below a published average."

---

## Conversion

| Metric | Weak | Typical | Strong | Notes |
|---|---|---|---|---|
| Sitewide CVR | under 1% | 1.5–3% | over 3.5% | Heavily mix-dependent. Branded and email traffic inflates it; cold paid deflates it |
| Mobile CVR | under 0.8% | 1–2% | over 2.5% | Usually 30–50% below desktop. A gap wider than that is a mobile UX finding |
| Desktop CVR | under 1.5% | 2.5–4% | over 5% | |
| PDP add-to-cart rate | under 5% | 8–12% | over 15% | The cleanest read on product page quality |
| Cart to checkout | under 40% | 50–65% | over 70% | Low here means cart friction or a shipping-cost surprise |
| Checkout completion | under 45% | 55–70% | over 75% | Express payment options move this most |
| Site search usage | — | 5–15% of sessions | — | Searchers convert 2–3x site average; zero-result searches are a catalog finding |

**High-AOV, considered categories** (furniture, jewelry, equipment) run far lower CVR and should be judged on assisted conversion and lead capture instead.

---

## Paid Acquisition

| Metric | Notes |
|---|---|
| MER (blended revenue / total ad spend) | The number that matters. Healthy varies with margin: a 70%-margin brand survives a 3x MER; a 35%-margin brand does not |
| Meta CPM | Rises 30–80% from October through December. Never compare Q4 to Q2 |
| Prospecting share of spend | Below 50% often means the account is harvesting existing demand and calling it growth |
| Creative refresh rate | Fatigue shows as rising frequency with falling CTR. Most scaling accounts need new concepts weekly, not new variations |
| Longest-running creative | If nothing has run over 30 days, either testing is unfocused or nothing is working |
| Brand-term search spend | Defensible if competitors bid on you; otherwise test a holdout before assuming it is incremental |
| Amazon ACOS / TACoS | ACOS is ad efficiency; TACoS (ad spend / total sales) is the one that shows whether ads are building organic rank |

---

## Lifecycle

| Metric | Weak | Typical | Strong |
|---|---|---|---|
| Email + SMS share of total revenue | under 15% | 20–30% | over 35% |
| Flow share of email revenue | under 20% | 30–45% | over 50% |
| Welcome flow revenue per recipient | — | varies widely | — |
| List growth rate (monthly, net) | under 1% | 2–5% | over 6% |
| Email capture rate on site | under 1% | 2–4% | over 5% |
| Campaign unsubscribe rate | over 0.5% | 0.1–0.3% | under 0.1% |
| Spam complaint rate | over 0.1% | under 0.05% | — | Above 0.3% risks bulk-sender enforcement |

**Flow coverage** is scored by presence, not performance, on the first pass. Count how many of these exist and are live:

welcome · browse abandon · cart abandon · checkout abandon · post-purchase · shipping and delivery · review request · back-in-stock · replenishment · winback · VIP · sunset

Under six of twelve is a major finding regardless of how good the existing ones are.

---

## Retention

| Metric | Weak | Typical | Strong | Notes |
|---|---|---|---|---|
| Repeat purchase rate (12mo) | under 15% | 20–35% | over 40% | Consumables should be far higher than durables |
| Time to second order | — | category-dependent | — | Compare to the product's natural consumption cycle. A 90-day supply with a 200-day repurchase gap is a replenishment-flow finding |
| Subscription penetration | under 5% | 10–25% | over 30% | Consumables only |
| Subscription churn (monthly) | over 12% | 6–10% | under 5% | |
| Dunning recovery | under 30% | 40–60% | over 65% | Involuntary churn is the cheapest churn to fix |
| Return rate | — | 5–10% general, 20–40% apparel | — | Judge against category, never in the abstract |

---

## Organic and Marketplace

| Signal | What good looks like |
|---|---|
| Indexed pages vs real pages | Close. Large excess usually means faceted-nav bloat |
| Collection pages ranking for category terms | The main organic revenue driver for most stores; PDPs rank for long-tail |
| Product schema | Valid, with price, availability, and aggregate rating present |
| Mobile Core Web Vitals | Passing. Ecommerce themes with heavy app stacks routinely fail LCP |
| Review count vs category leader | Within an order of magnitude. On Amazon this is the ranking moat |
| Amazon organic rank, top 10 keywords | Page one for at least the primary term |
| A+ content | Present on every parent ASIN; Premium A+ if brand-registered and eligible |

---

## Scoring Rubric

| Score | Meaning |
|---|---|
| **0** | Absent entirely. No cart abandon flow, no reviews, no tracking |
| **1** | Exists but broken — misconfigured, not firing, or actively harming |
| **2** | Minimal. Default app settings, never revisited |
| **3** | Functional. Does the job, no meaningful optimization |
| **4** | Good. Deliberately built, measured, and iterated |
| **5** | Best-in-category. A competitive advantage |

**Score the surface, rank by money.** A 3/5 on checkout for a brand doing 60% of revenue through it outranks a 0/5 loyalty program every time.

---

## Impact Estimation

Always show the arithmetic so the user can correct an input rather than dispute a conclusion.

**Missing or weak flow:**
```
triggering events/mo x recovery rate x AOV
```
Recovery-rate starting points: cart abandon 5–10%, checkout abandon 10–20%, browse abandon 1–3%, back-in-stock 15–30%.

**Conversion improvement:**
```
sessions/mo x CVR delta x AOV
```
Be conservative on the delta. Claiming a full point of CVR from a copy change is not credible.

**AOV improvement:**
```
orders/mo x AOV delta x contribution margin %
```
Use contribution margin, not revenue — a bundle that raises AOV by discounting can lower profit.

**Paid efficiency:**
```
spend/mo x (current CPA - projected CPA) / current CPA
```

When an input is unknown, write the formula with the blank and name what would fill it. `[sessions/mo] x 0.5% x $68 — need GA4 access` is more useful than a guess presented as a finding.
