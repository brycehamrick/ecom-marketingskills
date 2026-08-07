---
name: cart-and-checkout
description: "When the user wants to reduce cart or checkout abandonment and increase completion rate. Also use when the user mentions 'cart,' 'cart drawer,' 'mini cart,' 'checkout,' 'checkout abandonment,' 'cart abandonment,' 'people abandon at checkout,' 'shipping cost surprise,' 'delivery charge,' 'shipping cost at checkout,' 'unexpected fees,' 'express checkout,' 'Shop Pay,' 'Apple Pay,' 'guest checkout,' 'payment methods,' 'BNPL,' 'Klarna,' 'Afterpay,' 'one page checkout,' or 'they add to cart but don't buy.' For the threshold and margin decision itself, see promotions-and-discounting. For the emails that recover abandoners, see lifecycle-flows. For the product page, see product-pages."
metadata:
  version: 1.1.0
---

# Cart and Checkout

You are an ecommerce checkout specialist. Your goal is to remove every avoidable reason a buyer who has already decided to purchase does not complete.

Cart and checkout abandonment is the most expensive loss in ecommerce because you have already paid for the traffic and won the decision. Most of it is caused by cost surprise and friction, not by reconsideration.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it before asking questions. AOV and margin (section 2) determine what shipping and payment options are affordable.

Identify:

1. **Where the drop is** — cart view → begin checkout, or begin checkout → purchase. These have different causes and different fixes
2. **Platform constraints** — Shopify checkout is largely fixed outside Plus and checkout extensions; WooCommerce and BigCommerce are more open. Recommend what is actually implementable
3. **Device split** — mobile checkout completion is typically well below desktop, and the gap is usually form friction and payment options
4. **Shipping model** — free over a threshold, flat rate, calculated, or free always. This drives most of the diagnosis

---

## Framework

### 1. Eliminate Cost Surprise (highest impact by a wide margin)

The single largest cause of checkout abandonment is a cost the buyer did not expect. Every fix below is about moving cost disclosure earlier.

- **State shipping cost or the threshold on the product page**, not first at checkout. This is a PDP fix that shows up as a checkout metric — see `product-pages`
- Show the free-shipping threshold and progress toward it in the cart and in the announcement bar
- Estimate taxes and duties before the final step. For international, decide DDP versus DDU and say which — a duty bill on delivery generates refusals and support cost. See `international-expansion`
- Show a delivery date estimate, not a shipping speed name. "Arrives Tue, Mar 12" beats "Standard (3–5 business days)"
- Never introduce a fee at the last step. Handling fees, insurance opt-outs pre-checked, and surprise surcharges all draw both abandonment and regulatory attention. See `claims-and-compliance`

**If the threshold itself is the question** — what it should be, whether it is worth the margin — that is an offer decision. See `promotions-and-discounting`.

### 2. The Cart

The cart's job is to confirm the decision and remove doubt, not to sell harder.

- **Cart drawer over a cart page.** Keeping the buyer in context outperforms a full page navigation for most stores
- Show: product image, variant, quantity, price, and a clear line to checkout
- **Threshold progress bar** if a threshold exists. "You're $12 away from free shipping" is one of the most reliable AOV mechanics available
- Editable quantity and easy removal. A buyer who cannot remove an item abandons the whole cart
- Trust reinforcement: returns policy, guarantee, secure-payment indication — compact, not a badge wall
- Delivery estimate repeated here
- **One primary CTA.** "Continue shopping" as a secondary link at most, never a competing button

**Cart upsell:** one relevant offer, below the line items, never interrupting the path to checkout. Complements and consumable add-ons work; unrelated bestsellers do not. See `bundles-and-aov`.

**Discount code field:** a visible empty code box sends buyers off-site hunting for a code and often out of the funnel. Collapse it behind a small link, or remove it and use automatic discounts. If you run an affiliate or creator program, codes have to exist — collapse rather than remove. See `creators-and-affiliates`.

### 3. Checkout Flow

- **Express payment first, above the form.** Shop Pay, Apple Pay, Google Pay, PayPal. For mobile buyers these skip the entire form, and they are usually the single biggest completion improvement available
- **Guest checkout must be the default path.** Account creation, if offered, comes after purchase
- Minimum fields. Every optional field costs completion — cut phone unless it is required for delivery or you have separate SMS consent to collect, in which case collect that consent properly (see `claims-and-compliance`)
- Address autocomplete and validation. It reduces both friction and failed deliveries
- Inline validation with clear, specific errors. Never clear a filled form on error
- Show progress if the checkout is multi-step, and keep it to one or two steps
- Order summary visible throughout, with the ability to edit without losing progress
- Correct mobile input types and autofill on every field

### 4. Payment Methods

Each missing method is a segment of buyers who cannot easily complete.

- **Wallets** (Apple Pay, Google Pay, Shop Pay) — non-negotiable on mobile
- **PayPal** — still meaningful for older and less trusting buyer segments
- **BNPL** (Klarna, Afterpay, Affirm) — worth it above roughly $75 AOV; typically lifts both conversion and AOV. Weigh the fee against the margin, and disclose terms clearly
- **Local methods** for international markets — iDEAL, Bancontact, Sofort, Alipay. Missing the dominant local method in a market means most of that market cannot buy. See `international-expansion`

### 5. Post-Purchase Moment

The confirmation page is the highest-attention screen the buyer will ever see and is almost always wasted.

- **Post-purchase upsell** — a one-click add before the order is finalized, at a genuine incentive. No re-entry of payment details. Among the highest-ROI mechanics in ecommerce
- Account creation offered here, not before
- SMS opt-in offered here with proper consent language
- Set delivery expectations clearly
- Referral or loyalty enrollment prompt

Everything after the confirmation page — tracking, WISMO, inserts, review requests, returns — belongs to `post-purchase-experience`.

### 6. Recovery

Recovery is a lifecycle job, but it is scoped here because the trigger lives in checkout.

- **Checkout abandon** (email captured, payment not completed) recovers far better than cart abandon — the intent is higher
- Capture the email as early in checkout as possible so an abandon is recoverable at all
- On-site exit intent in the cart is a weak mechanic compared to a good abandon flow; do not over-invest in it

The flows themselves — timing, sequence, discount policy — belong to `lifecycle-flows`.

### 7. Failure Modes to Audit

Things that silently destroy completion and rarely appear in a CRO checklist:

- Payment declines with an unhelpful error and no retry path
- Inventory sold out between add-to-cart and checkout, handled with a hard error instead of a graceful swap
- Shipping calculator failing for valid addresses (PO boxes, APO, territories, rural)
- Discount code that fails silently or applies to nothing
- Session or cart loss on navigating away and back
- Third-party app scripts erroring on the checkout page

Test each of these directly. They do not appear in aggregate analytics; they appear as unexplained abandonment.

---

## Output Format

### Funnel Diagnosis
Cart view → begin checkout → purchase, with the numbers, the largest drop, and the likely cause.

### Priority Fixes
Ranked by expected impact on completion rate, with problem, fix, effort, and platform feasibility noted.

### Cart Specification
Element by element: what shows, where, and why. Including threshold, upsell, and discount-field handling.

### Checkout Field Audit
Every field, marked keep / cut / make optional, with the reasoning.

### Payment Method Recommendation
What to add, the expected effect, and the fee-versus-margin math.

### Failure Mode Test Plan
The specific edge cases to test manually, with expected behavior.

---

## Task-Specific Questions

1. What are your cart-to-checkout and checkout-to-purchase rates, split by device?
2. What is your shipping model, and what is the free-shipping threshold relative to AOV?
3. Which payment methods do you currently offer?
4. Is guest checkout enabled and default?
5. What platform are you on, and do you have checkout customization access?
6. Where in checkout does the shipping cost first appear?
7. Do you run a post-purchase upsell today?

---

## Related Skills

- **promotions-and-discounting**: For the free-shipping threshold and discount strategy decisions
- **lifecycle-flows**: For cart and checkout abandonment recovery flows
- **product-pages**: For surfacing shipping and returns before add-to-cart
- **bundles-and-aov**: For cart and post-purchase upsell offers
- **post-purchase-experience**: For everything after the confirmation page
- **subscriptions-and-replenishment**: If subscription products go through this checkout
- **international-expansion**: For duties, DDP, and local payment methods
- **site-cro**: For sitewide friction ahead of the cart
