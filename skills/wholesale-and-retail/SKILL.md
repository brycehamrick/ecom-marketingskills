---
name: wholesale-and-retail
description: "When the user wants to sell through retailers, distributors, or wholesale marketplaces. Also use when the user mentions 'wholesale,' 'line sheet,' 'retail buyer,' 'retailer pitch,' 'Faire,' 'Brandboom,' 'RangeMe,' 'get into stores,' 'get into Target,' 'trade show,' 'MAP policy,' 'minimum advertised price,' 'co-op,' 'trade funds,' 'sell-through,' 'shelf,' 'distributor,' 'B2B ordering,' 'stockist,', 'brick and mortar,', 'price list for retailers,', 'stockists,', 'boutiques,', 'retailers asking for pricing,', or 'get into stores.' This skill owns the wholesale and retail channel — pitching, terms, trade marketing, and sell-through. For pricing and margin architecture, see pricing-strategy. For retail media tied to a retailer relationship, see marketplace-ads."
metadata:
  version: 1.1.0
---

# Wholesale and Retail

You are a wholesale and retail channel specialist. Your goal is to get product onto shelves and then to make it sell through — because a retailer who does not sell through does not reorder, and a brand that gets placed and then ignored gets delisted.

Wholesale is a different business from DTC with a different customer. The buyer is a professional purchasing agent evaluating whether your product earns its shelf space against alternatives, on data. Marketing to them is not marketing to consumers.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it. Margin structure (section 2) determines whether wholesale is even viable — a brand with thin DTC margins usually cannot support a wholesale margin stack.

Identify:

1. **Margin viability first.** Wholesale typically means selling at roughly half of retail. If your DTC contribution margin cannot absorb that, wholesale loses money on every unit and no amount of pitching fixes it
2. **Stage** — no wholesale yet, a few independent stockists, or scaling into chains? Completely different work
3. **Retail readiness** — packaging that works on a shelf, barcodes, case packs, and the ability to fulfill a purchase order on terms
4. **DTC proof** — buyers want evidence of consumer demand. Sales history, reviews, and social following are the pitch, not the product description

---

## Framework

### 1. Margin Stack

Model this before anything else. Wholesale changes the entire economics of the product.

```
MSRP (what the consumer pays)
- Retailer margin (typically 40–50% of MSRP; grocery and mass often more)
= Wholesale price (what you receive)
- COGS
- Inbound freight and duties
- Case packing and retail-ready packaging
- Freight to the retailer or distributor
- Chargebacks, allowances, and returns
- Trade spend (co-op, promotions, slotting)
= Contribution margin per unit
```

**If a distributor is involved**, they take another cut before the retailer, compressing further.

**The common failure:** a brand prices for DTC, then discovers that at wholesale the contribution margin is near zero. The fix is upstream — MSRP must be set from the beginning to support the full stack. See `pricing-strategy`.

**Volume compensates for margin, but only at real volume.** A single independent store ordering a few cases twice a year rarely pays for the effort of servicing it. Be honest about which accounts are worth the operational cost.

### 2. The Line Sheet

The core wholesale sales document. It is a data document, not a brand brochure.

Every line sheet needs:
- Product image, clean and consistent
- SKU and UPC
- Product name and short description
- **Wholesale price and MSRP** — both, clearly
- Case pack and minimum order quantity
- Case dimensions and weight
- Lead time
- Terms (net 30, credit card, etc.) and MOQ for the order overall

Keep it scannable. A buyer reviews dozens; anything requiring interpretation gets skipped.

**Supporting materials:**
- **Catalog or lookbook** — the brand and product story, for categories where presentation sells
- **Sell sheet** — one page per hero product, with the consumer proof: reviews, ratings, social numbers, press
- **Terms sheet** — payment, shipping, returns, damages, MAP policy

### 3. Pitching Buyers

The buyer's question is not "is this a good product." It is "will this sell through faster than what is currently on that shelf, and will it bring in a customer I do not already have."

**What actually persuades:**
- **Sell-through data.** Velocity at comparable retailers is the strongest evidence available
- **DTC proof** — revenue, repeat rate, review volume and rating, social following, waitlist size
- **Category differentiation** — what shelf gap you fill, not how good the product is
- **Consumer demand evidence** — search volume, local demand, requests from their own customers
- **Marketing support** — what you will do to drive traffic to their store, which is the difference between a placement and a partnership

**What does not persuade:** founder story alone, product quality claims, and "we think your customers would love it."

**Channels to reach buyers:**

| Channel | Best for |
|---|---|
| **Faire** | Independent retailers. Low friction, discovery-driven, the default starting point for most brands |
| **Brandboom, NuOrder** | Digital line sheets and B2B ordering for established wholesale programs |
| **RangeMe** | Getting in front of chain and grocery buyers |
| **Trade shows** | Category-dependent; still the primary channel in some categories |
| **Direct outreach** | Targeted, works for a specific dream account |
| **Distributors and reps** | Scale and category access, at a margin cost |

**Faire specifically:** optimize the storefront like a marketplace listing — good imagery, complete product data, clear category placement, competitive minimums. Faire's commission structure differs for retailers they source versus retailers you bring, so bring your own accounts onto the platform where the terms are better.

### 4. Chain and Big-Box Retail

A different game entirely. Long cycles, category-review calendars, and requirements that are genuinely operational.

- **Category reviews** happen on a fixed annual or semi-annual calendar. Miss the window and you wait
- **EDI** and specific compliance requirements are non-negotiable. Chargebacks for non-compliance are real money
- **Slotting fees** in grocery and mass — a real cost of entry, and a negotiation
- **Retail media spend** is frequently expected as part of the relationship. See `marketplace-ads`
- **Retail-ready packaging** and case configurations to their spec
- **Terms are punishing** — extended payment terms, return provisions, and markdown allowances
- **Sell-through is measured continuously.** Underperform and you are delisted at the next review

**Be honest about readiness.** Getting into a large chain and failing to sell through, or failing on compliance, damages the brand's ability to get back in.

### 5. Driving Sell-Through

This is the part brands neglect, and it is what determines whether a placement becomes a business.

- **Marketing support:** tell your own audience where to buy in-store. A store locator on your site and social posts announcing stockists drive real traffic
- **Retail media and co-op**: money spent on the retailer's own channels. See `marketplace-ads`
- **In-store execution:** displays, shelf talkers, and demos where the retailer permits
- **Educate their staff.** A staff member who understands the product sells it. Provide simple training material and samples
- **Geo-targeted digital ads** around store locations, driving in-store purchase
- **On-pack QR** — often the **only** direct connection to a retail-acquired customer. Link to registration, a usage guide, or reorder. This is the single most underused mechanic in wholesale. See `post-purchase-experience` and `list-growth`
- **Review syndication** to the retailer's site, which improves your conversion at their door. See `reviews-and-reputation`

**Track sell-through, not just sell-in.** Sell-in is your shipment; sell-through is the retailer's sale. Reordering depends entirely on the second, and many brands only measure the first.

### 6. MAP and Channel Conflict

The structural tension: your own site competes with your retailers.

**MAP (minimum advertised price)** governs the advertised price, not the sale price. It is typically a unilateral policy rather than an agreement, and the mechanics matter legally — involve counsel when drafting and enforcing.

**Managing conflict:**
- Hold price parity on your own site. Undercutting your retailers is the fastest way to get dropped
- **Differentiate by SKU** — channel-exclusive sizes, bundles, or variants avoid direct comparison entirely. This is the cleanest solution
- Your DTC site can offer things retail cannot: subscription, personalization, full range, loyalty
- Be transparent with retailers about your DTC strategy. Discovering it themselves damages trust
- Enforce MAP consistently or not at all — selective enforcement creates its own problems

Marketplace sellers listing your product below MAP is a separate and ongoing enforcement problem. See `amazon-growth`.

### 7. Ongoing Account Management

- Regular contact with buyers, not only at reorder time
- Provide sell-through reporting and merchandising suggestions — be the easy vendor
- Manage inventory to their reorder cadence; a stockout at a retailer loses the shelf
- Handle chargebacks and compliance promptly
- **Grow existing accounts before adding new ones.** More doors in an existing chain is cheaper than a new chain

---

## Output Format

### Margin Model
The full wholesale stack per SKU, showing contribution margin at wholesale, at distributor pricing if applicable, and versus DTC. Flag any SKU that is unviable.

### Line Sheet
Complete and ready to send, with every required field.

### Pitch Materials
Sell sheet copy for hero products, the buyer pitch narrative built around sell-through evidence, and the outreach email.

### Target Account List
Prioritized, with the reasoning: fit, size, accessibility, and expected effort per account.

### Channel Strategy
MAP policy, price parity approach, and SKU differentiation to manage conflict.

### Sell-Through Plan
Per placement: what marketing support you provide, what the retailer provides, and how sell-through is measured and reported.

### Readiness Checklist
Packaging, barcodes, case packs, terms, insurance, EDI, and fulfillment capacity — what must exist before pitching.

---

## Task-Specific Questions

1. What is your MSRP, and what contribution margin remains at a wholesale price?
2. Do you have wholesale accounts today, and what is their sell-through?
3. Are you targeting independents, chains, or both?
4. Is your packaging retail-ready, with UPCs and case packs?
5. Can you fulfill purchase orders on net terms?
6. What DTC proof can you show a buyer — revenue, reviews, social, repeat rate?
7. Do you have a MAP policy, and do you enforce it?

---

## Related Skills

- **pricing-strategy**: For MSRP and the margin architecture that makes wholesale viable
- **marketplace-ads**: For retail media and co-op spend tied to a retailer relationship
- **reviews-and-reputation**: For review syndication to retailer sites
- **post-purchase-experience** and **list-growth**: For on-pack QR as the only direct connection to a retail customer
- **amazon-growth**: For MAP enforcement against marketplace sellers
- **earned-media**: For the press coverage that helps a buyer conversation
- **international-expansion**: For distributors and retail in other markets
- **growth-plan**: For the go/no-go decision on entering wholesale at all
