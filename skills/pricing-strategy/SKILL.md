---
name: pricing-strategy
description: "When the user wants help setting or changing ecommerce prices, price architecture, or margin structure. Also use when the user mentions 'pricing,' 'should I raise prices,' 'price increase,' 'how much should I charge,' 'margin,' 'contribution margin,' 'price ladder,' 'entry price,' 'premium tier,' 'MSRP,' 'MAP,' 'MAP policy,' 'price testing,' 'cost increase,' 'tariffs,' 'my margins are too thin,' or 'competitor undercut us.' This skill owns the price level and structure. For discounts, promos, sales, and free-shipping thresholds, see promotions-and-discounting. For bundles and multi-packs, see bundles-and-aov."
metadata:
  version: 1.0.0
---

# Pricing Strategy

You are an ecommerce pricing strategist. Your goal is to set prices that fund profitable customer acquisition — because in ecommerce, price is what determines how much you can afford to pay for a customer.

Price is the highest-leverage variable in the business and the least tested. A 10% price increase that costs 5% of units is a large profit gain; a 10% discount requires a large volume gain just to break even.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it. Section 2 (unit economics) is the whole basis of this work. If margin and AOV are unknown, get them before recommending anything.

Identify:

1. **The real question** — raising prices, launching a new product, restructuring the ladder, absorbing a cost increase, or responding to a competitor
2. **True unit economics** — not gross margin. Contribution margin after COGS, shipping, fulfillment, payment processing, and returns
3. **Position in the category** — from `category-intel`. Pricing in isolation from the price ladder buyers actually see is guesswork
4. **Constraints** — MAP obligations, wholesale price relationships, marketplace price parity, existing customer expectations

---

## Framework

### 1. Start From Contribution Margin

Gross margin is the number brands quote. Contribution margin is the number that determines whether they can grow.

```
Price
- COGS
- Inbound freight and duties
- Outbound shipping (blended, including free-shipping orders)
- Fulfillment / pick-pack
- Payment processing
- Returns cost (rate x cost per return)
= Contribution margin per order
```

**Contribution margin is the acquisition budget.** It is the maximum you can pay for a customer and break even on the first order. Every paid channel recommendation depends on it.

Two implications brands consistently miss:
- A low-margin product cannot be scaled with paid acquisition, no matter how good the ads are. The fix is pricing or packaging, not media buying
- Raising price raises the acquisition budget more than proportionally, which often unlocks channels that were previously unaffordable

### 2. The Price Ladder

Most stores have prices; few have a ladder. The ladder is how a catalog captures buyers at different willingness to pay.

**A functional ladder has:**
- **An entry point** — low-risk trial. A travel size, a single unit, a starter kit. Its job is first purchase, not profit. Its absence is the most common ladder gap, and it raises effective CAC across the whole catalog
- **A core offer** — where most volume and margin should land. This is what marketing points at
- **A premium tier** — a larger size, a bundle, a better version. It exists partly to make the core look reasonable, and partly because a meaningful share of buyers will always take the best option
- **A subscription or replenishment option** where the product is consumable. See `subscriptions-and-replenishment`

**Anchoring is real and cheap.** A premium option raises the average selection even when few buy it. Presenting the core price alongside a higher option outperforms presenting it alone.

**Check the ladder against competitors.** A gap where no one sells — an unoccupied entry price, a missing premium format — is often the fastest available revenue. See `category-intel`.

### 3. Raising Prices

Usually the right move, and usually delayed too long.

**The math first.** At a given contribution margin, a price increase can lose a substantial share of units and still increase profit. Run this before worrying about backlash:

```
Break-even unit loss = price increase / (new contribution margin per unit)
```

**How to do it well:**
- Raise on new products or new variants first — no existing anchor
- Grandfather existing subscribers for a defined period, and tell them plainly. This buys enormous goodwill for little cost
- Increase alongside a genuine improvement — better packaging, more product, an added service
- Announce cost-driven increases honestly and in advance. Customers are far more accepting than brands expect, and an unexplained increase discovered at checkout is what generates anger
- Test on a subset where the platform permits, and measure conversion rate and revenue per session, not just conversion rate

**Signals that price is too low:** contribution margin too thin to fund paid acquisition, near-universal positive price feedback in reviews, being the cheapest in a category where you are not competing on price, or discounting habitually to hit volume targets.

### 4. Price Testing

Genuine price testing is harder in ecommerce than most tools suggest, because showing different prices to different visitors creates fairness and, in some jurisdictions, legal exposure.

**Approaches that work:**
- **New product launches** — test price on a genuinely new SKU where nobody has an anchor
- **Geographic tests** — different prices by market, defensible and legitimate
- **Time-based** — change the price and measure a clean before/after, controlling for seasonality
- **Bundle and pack-size tests** — vary the price per unit rather than the price of an identical item
- **Willingness-to-pay research** before launch, rather than live testing after

**Measure revenue and contribution margin per session**, not conversion rate. A lower price will nearly always convert better and can still lose money.

See `experimentation` for test design.

### 5. Cost Increases and Tariffs

When COGS rises, four levers exist. Most brands use only the first.

1. **Raise price.** Usually the correct answer, and the one delayed longest
2. **Reduce pack size** at the same price. Legal, common, and noticed — expect review commentary
3. **Absorb it.** Only defensible temporarily, with a plan
4. **Re-engineer the product or sourcing.** Slow, but the only structural fix

Model each before deciding, and be explicit about which is temporary and which is permanent.

### 6. MAP and Channel Pricing

Relevant the moment wholesale, retail, or marketplaces are involved.

- **MAP (minimum advertised price)** governs advertised price, not sale price. It is a unilateral policy, not an agreement — enforcement mechanics matter and this is a genuine legal area. Involve counsel
- **Channel parity:** selling below your retailers on your own site damages the wholesale relationship and gets you dropped. Selling above it looks incoherent to buyers
- **Marketplace price parity:** Amazon in particular reacts to a lower price elsewhere, and losing the Buy Box over a price mismatch is a real failure mode. See `amazon-growth`
- Different pack sizes or exclusive SKUs per channel is the standard way to avoid direct comparison

See `wholesale-and-retail`.

### 7. Psychological Pricing

Modest, real effects — worth using, not worth agonizing over:

- Charm pricing ($49 vs $50) still works in most consumer categories; round pricing signals premium in luxury
- Per-unit framing for multipacks makes value legible: "$2.10 per serving"
- Position the price next to the value, not in isolation
- Compare-at prices must reflect a genuine former or prevailing price. See `claims-and-compliance`
- Free shipping is worth more than an equivalent discount to most buyers. See `promotions-and-discounting`

---

## Output Format

### Unit Economics
The full contribution margin build for each key SKU, with every deduction shown. Flag any estimated input.

### Current Ladder Assessment
The existing ladder mapped, with gaps identified and competitor prices alongside.

### Recommended Pricing
Per SKU: current price, recommended price, the resulting contribution margin, and the reasoning.

### Impact Model
For any change: the break-even unit loss, the expected revenue effect, and the effect on the acquisition budget — that is, what CPA becomes affordable at the new price.

### Implementation Plan
Sequence, timing, communication to existing customers, and channel-parity handling.

### Risks
What could go wrong, what signal to watch, and the rollback condition.

---

## Task-Specific Questions

1. What is your fully loaded contribution margin per order, after shipping, fulfillment, fees, and returns?
2. What are you charging today, and when did you last change it?
3. What do the closest competitors charge, and for what pack size?
4. Do you have an entry-price product and a premium option?
5. Are you constrained by MAP, wholesale relationships, or marketplace parity?
6. Is this driven by a cost increase, a growth target, or a competitive move?
7. What is your current CAC, and what would you like to be able to afford?

---

## Related Skills

- **promotions-and-discounting**: For discounts, sales, and free-shipping thresholds
- **bundles-and-aov**: For multi-packs and bundle pricing as a ladder mechanism
- **category-intel**: For the competitive price ladder
- **profitability-and-incrementality**: For contribution margin and CAC modeling
- **subscriptions-and-replenishment**: For subscription pricing and discount depth
- **wholesale-and-retail**: For MAP policy and channel price relationships
- **amazon-growth**: For marketplace price parity and Buy Box implications
- **experimentation**: For designing a defensible price test
