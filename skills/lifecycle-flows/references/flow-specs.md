# Flow Specifications

Message-by-message specs for the twelve core ecommerce flows. Timings are starting points — adjust to purchase-cycle length, AOV, and how aggressive the brand's tone allows.

Every flow assumes: purchase exits the flow, proper exclusions are set, and SMS only sends to numbers with express written consent.

---

## 1. Checkout Abandon

**Trigger:** started checkout, no purchase. **Exit:** purchase.
Highest intent in the entire program. Email is captured, so recovery rates run well above cart abandon.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | 30–60 min | Email | Assume a technical or interruption problem. "Your order didn't go through — here's your cart." No discount, no selling. Direct link back into checkout |
| 2 | 4–6 hr | Email | Address the likely blocker: shipping cost, delivery time, payment options, returns policy. Add reviews for the item in cart |
| 3 | 24 hr | SMS or Email | Short, urgent. "Still want this? Your cart's saved." SMS is strong here if consent exists |
| 4 | 48–72 hr | Email | Incentive if you use one at all. Free shipping before a percentage discount |

**Copy notes:** show the actual product image, name, and variant. A generic "you left something behind" without the item performs measurably worse.

---

## 2. Cart Abandon

**Trigger:** added to cart, no checkout started. **Exit:** started checkout (hands off to flow 1) or purchase.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | 1–4 hr | Email | Product-forward reminder. Image, name, variant, price, one-click return to cart |
| 2 | 24 hr | Email | Objection handling. Reviews, guarantee, shipping and returns, sizing help |
| 3 | 48 hr | Email | Social proof or scarcity if genuinely true. See `claims-and-compliance` on stock claims |
| 4 | 72 hr | Email or SMS | Optional incentive, final message |

**Split:** high cart value gets a longer, more consultative sequence; low cart value gets a shorter one. Repeat customers skip the brand introduction entirely.

---

## 3. Welcome

**Trigger:** joined the list. **Exit:** purchase moves them to post-purchase.
The highest engagement window a brand ever gets. Do not waste it on a single discount code.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | Immediate | Email | Deliver what was promised at signup (code, guide, quiz result). Set expectations for what comes next. This is the highest-opened email the brand sends |
| 2 | 1 day | Email | The one thing that makes the brand different, shown not claimed. Founder or origin story if it is genuinely load-bearing |
| 3 | 3 days | Email | Best sellers or a category router. Let them self-select what they care about |
| 4 | 5 days | Email | Social proof. Reviews, UGC, results, press |
| 5 | 7 days | Email | Objection handling plus the offer again, with an end date if the incentive expires |

**Split by source.** Someone from a quiz should get results-driven content; someone from an exit popup gets the offer reinforced; someone from a gated guide gets education first. See `list-growth`.

**SMS variant:** two messages only. Welcome plus the code immediately, and one reminder at day 3.

---

## 4. Post-Purchase

**Trigger:** order placed. Runs alongside transactional shipping notifications.
The goal is the second order. Consumption drives repurchase, so drive usage.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | Immediate | Email | Order confirmation with genuine reassurance, not just a receipt. What happens next and when |
| 2 | 1–2 days | Email | How to get the best result. Usage instructions, tips, what to expect and when |
| 3 | On delivery | Email or SMS | "It's here — here's how to start." Highest-attention moment post-purchase |
| 4 | 7–14 days | Email | Check in. Offer help. Route problems to support before they become returns or bad reviews |
| 5 | Cycle-dependent | Email | Complementary product or replenishment setup |

Shipping, tracking, WISMO, and inserts belong to `post-purchase-experience`.

---

## 5. Browse Abandon

**Trigger:** viewed a product, no add to cart. **Exit:** add to cart.
High volume, low intent. Keep it short and low-pressure or it reads as surveillance.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | 4–8 hr | Email | Soft. "Still thinking about this?" with the product and two or three related items |
| 2 | 48 hr | Email | Category-level value — a guide, a comparison, a how-to-choose |

Two messages maximum. Never discount here; intent is too low to justify the margin.

**Suppression:** exclude anyone who viewed only a single page in a single session, and anyone browsing a product they already own.

---

## 6. Back in Stock

**Trigger:** signed up on an out-of-stock product, product restocked.
Tiny volume, exceptional conversion. Among the best revenue-per-recipient flows in the program.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | Immediate | SMS + Email | "It's back." Direct link to the product and variant they wanted |
| 2 | 24 hr | Email | Reminder, only if stock is genuinely limited |

Send SMS here even for brands that otherwise use SMS sparingly — it is the highest-value message in the program. Requires back-in-stock capture on out-of-stock PDPs; see `collection-merchandising` and `product-pages`.

---

## 7. Review Request

**Trigger:** delivered, plus enough delay for real use.
Compounds — reviews raise conversion on every downstream surface.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | Product-dependent | Email | Ask once, simply. Star selector embedded in the email. Delay must match time-to-value: 7 days for apparel, 21–30 for skincare, longer for supplements |
| 2 | +7 days | Email | One reminder only |

**Split on sentiment where the platform allows** — route low ratings to support rather than to the public review form. Never suppress or gate negative reviews from being posted; the split is about resolving problems, not hiding them. See `claims-and-compliance` and `reviews-and-reputation`.

---

## 8. Replenishment

**Trigger:** purchase plus the consumption cycle. Consumables only.
The highest-value retention flow for consumable brands, and one of the most commonly missing.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | 75% of cycle | Email | "Running low?" One-click reorder with the exact previous variant |
| 2 | 100% of cycle | Email or SMS | "Time to restock." Offer the subscription as the easier option |
| 3 | 120% of cycle | Email | Final reminder, possibly with an incentive |

**Set the cycle per product**, from actual consumption, not a guess. If time-to-second-order in the data is much longer than the product's stated supply duration, this flow is missing or mistimed. See `subscriptions-and-replenishment`.

---

## 9. Winback

**Trigger:** no purchase in N days, where N is roughly 1.5–2x the normal repurchase interval.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | Day 0 | Email | "We miss you" plus what is new since they last bought — new products, improvements |
| 2 | +7 days | Email | Best sellers and social proof. Reset the brand in mind |
| 3 | +14 days | Email | Real incentive. This is where a discount is justified — reactivation is cheaper than acquisition |
| 4 | +21 days | Email | Last call, then route to sunset |

**Split by past value.** A former high-value customer deserves a better offer and a more personal message than a single low-value order.

---

## 10. VIP / Second Purchase

**Trigger:** purchase count or lifetime spend threshold.
The second purchase is the biggest single step change in customer value. Treat it as its own campaign.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | On threshold | Email | Recognition. Early access, a perk, or genuine thanks — not a discount |
| 2 | +30 days | Email | Exclusive access to something not publicly available |

Program design — tiers, points, benefits — belongs to `retention-and-loyalty`. This flow only executes it.

---

## 11. Sunset

**Trigger:** no open or click in 90–180 days.
Protects deliverability. Skipping it degrades inbox placement for the entire program.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | Day 0 | Email | "Still want to hear from us?" One clear button to stay |
| 2 | +7 days | Email | Last chance, plainly stated |
| 3 | +14 days | — | Suppress from campaigns. Keep in flows that are purchase-triggered |

Suppress rather than delete, so purchase history and attribution survive.

---

## 12. Birthday / Anniversary

**Trigger:** date on file.
Low effort, reliably positive, modest ceiling. Only build it if the date is already being collected — do not add a birthday field to a signup form to enable it.

| # | Delay | Channel | Job |
|---|---|---|---|
| 1 | 7 days before | Email | Gift or offer, with a clear expiry |
| 2 | On date | SMS or Email | Short reminder |

---

## Timing Reference

| Product cycle | Replenishment trigger | Winback trigger | Review request delay |
|---|---|---|---|
| Weekly consumable | 5 days | 30 days | 10 days |
| Monthly consumable | 22 days | 60 days | 21 days |
| Quarterly consumable | 70 days | 180 days | 30 days |
| Apparel | n/a | 120 days | 7 days |
| Durable goods | n/a | 365 days | 14 days |

---

## Common Configuration Errors

- Cart abandon and checkout abandon both firing for the same person
- No purchase exclusion — emailing someone about an item they bought an hour ago
- Browse abandon triggering on the same product repeatedly for a habitual browser
- Review request firing on order date instead of delivery date
- Replenishment timed to the order date rather than the consumption cycle
- Back-in-stock sending to people who already bought the item elsewhere on the site
- Sunset flow suppressing people who are still buying but never opening — exclude recent purchasers from sunset
- SMS sending outside quiet hours in the recipient's timezone
