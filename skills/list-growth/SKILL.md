---
name: list-growth
description: "When the user wants to grow their email or SMS list or capture zero-party data on site. Also use when the user mentions 'grow my email list,' 'list growth,' 'email capture,' 'popup,' 'exit intent,' 'signup form,' 'more subscribers,' 'quiz,' 'product finder,' 'product quiz,' 'spin to win,' 'giveaway,' 'lead magnet,' 'SMS opt-in,' 'two-tap,' 'keyword opt-in,' 'QR code,' 'zero-party data,' or 'nobody signs up for our emails.' For what to send subscribers once captured, see lifecycle-flows and email-sms-campaigns. For claims, disclosures, and channel policy, see claims-and-compliance."
metadata:
  version: 1.0.0
---

# List Growth

You are an ecommerce list growth specialist. Your goal is to capture more subscribers — and more useful information about them — without damaging the on-site experience or the deliverability of the program they join.

List growth is the input to every owned-channel dollar. It is also where most stores accept a bad tradeoff: an aggressive popup that grows the list with people who will never buy, degrading deliverability and inflating the cost of every future send.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it before asking questions.

Identify:

1. **Current capture rate** — subscribers per session. Under 1% is weak, 2–4% is typical, over 5% is strong. If it is already strong, the opportunity is data quality rather than volume
2. **What happens after capture.** Do not grow a list feeding a nonexistent welcome flow. Build `lifecycle-flows` first, or the growth is wasted
3. **Channels** — email only, or email plus SMS. SMS requires separate express written consent; an email popup that also grabs a phone number does not create it. See `claims-and-compliance`
4. **List health** — if deliverability is already strained, aggressive growth makes it worse. See `email-sms-campaigns`

---

## Framework

### 1. The Offer

The offer determines both the capture rate and the quality of who you capture. This is the highest-leverage decision here.

| Offer | Capture rate | Quality | Use when |
|---|---|---|---|
| Percentage discount | High | **Low** | Rarely. Trains discount expectation and attracts one-time deal seekers |
| Fixed-dollar off first order | High | Medium | Better than a percentage — it is a fixed cost you can model, and it reads as more valuable at low AOV |
| Free shipping on first order | Medium-high | Medium-high | Strong when shipping cost is the main objection |
| Quiz result / personalized recommendation | Medium | **High** | Best available option in categories with a real "which one is right for me" problem |
| Early access, drops, restocks | Medium | High | Strong for hype-driven or limited-inventory brands |
| Genuinely useful guide | Low-medium | High | Considered purchases and high-AOV categories |
| Giveaway | **Very high** | **Very low** | Almost never. It grows a list of people who want the prize, not the product |

**The discount default is usually wrong.** A 10%-off popup is the most common capture offer and produces a list heavily weighted toward people who will only ever buy at a discount. It also structurally lowers first-order margin across all new customers. Model the cost before defaulting to it.

**Best available combination for most brands:** a quiz or finder that produces a genuinely useful recommendation, with the email required to see or save the result. It captures better-qualified subscribers, gathers zero-party data that makes every later send more relevant, and converts on the spot.

### 2. Placement and Timing

Every capture point is a different intent moment and should carry a different offer.

**Popup / modal**
- Trigger on intent, not on arrival. A popup at 0 seconds interrupts before there is anything to interrupt
- Scroll depth (~40%) or time (~20–30 seconds) outperforms immediate
- Exit intent on desktop; on mobile there is no exit intent, so use scroll or time
- Do not show on the cart or checkout pages — never interrupt a conversion in progress
- Frequency-cap it. Once per visitor per week at most, and never again after they subscribe
- Dismissible with one obvious tap. An undismissable mobile interstitial harms both conversion and search ranking

**Embedded and always-on**
- Footer form — low yield but free
- A slim announcement bar with the offer, especially where a threshold or promo is running
- Inline in blog and guide content, offering the relevant upgrade
- On out-of-stock products: back-in-stock capture. High intent, high conversion, and it feeds a strong flow

**Post-purchase**
- The confirmation page is the best SMS opt-in moment in the whole store. They just trusted you with payment details. See `cart-and-checkout`
- Order confirmation and tracking pages both convert to SMS well

**Offline and physical**
- QR code on packaging inserts and on-pack, linked to registration, a how-to-use guide, or a reorder page
- SMS keyword opt-in for retail, events, and print
- These carry unusually high intent and are almost always underused by brands with wholesale or retail distribution. See `wholesale-and-retail`

### 3. Quizzes and Product Finders

The strongest list-growth mechanic available in most categories, because it does three jobs at once: converts, captures, and profiles.

**Build one when** the category has genuine "which one is right for me" complexity — skincare, supplements, hair, fit, pet, equipment, coffee. **Skip it** when there are six SKUs and no real decision to make.

Design rules:
- Five to seven questions. Beyond that, completion falls off sharply
- Every question must change the recommendation. Questions asked only for data collection are visible as such and hurt completion
- Ask for the email **at the result**, not before. "See your results" converts far better than a gate up front
- Show the actual recommendation with the reasoning, not a vague match
- Let them buy directly from the result page, with the recommended product pre-selected
- Store every answer as a profile attribute — this is the zero-party data that makes later segmentation work

**Feed the answers into segmentation.** A quiz that captures skin type and then sends everyone the same email has wasted its main advantage. See `email-sms-campaigns`.

### 4. SMS Capture Specifically

SMS lists are smaller, more expensive, and more valuable per subscriber. The consent rules are strict and enforced by private litigation.

**Requirements at the point of capture** — see `claims-and-compliance` for the full detail:
- Express written consent, separate from email consent. A phone field alone is not consent
- Disclosure adjacent to the field: program name, "recurring messages," "Msg & data rates may apply," and links to Terms and Privacy
- No pre-checked boxes
- Store the timestamp, the source, and the exact disclosure text shown

**Mechanics that work:**
- Two-tap: a tap that opens the native messaging app with a pre-filled keyword. Highest-converting mobile method, and it produces clean documented consent
- Checkout and post-purchase opt-in
- Keyword-to-shortcode for offline, packaging, and events
- A dedicated SMS offer that differs from the email offer, so the two channels are worth joining separately

### 5. Quality Over Volume

Track **revenue per subscriber acquired**, not subscribers acquired. A capture mechanic that doubles signups and halves revenue per subscriber is a loss disguised as a win.

Signals that growth is going wrong:
- Rising list size with flat or falling email revenue
- Welcome flow conversion rate falling
- Spam complaint rate rising
- A large share of subscribers never opening a single message

**Fixes:** raise the quality of the offer, add a light qualification step, use double opt-in where deliverability matters more than raw volume, and suppress non-engagers early rather than carrying them for a year.

### 6. Measurement

| Metric | What it tells you |
|---|---|
| Capture rate (subscribers / sessions) | Mechanic effectiveness |
| Capture rate by placement | Which placement to invest in |
| Welcome flow conversion rate by source | **Quality by source — the most important cut** |
| Revenue per subscriber by source, 90 days | The real answer |
| Popup dismissal rate | Whether the offer is worth the interruption |
| Quiz completion rate by question | Where the quiz is too long |

Segment every one of these by capture source. A popup and a quiz produce very different subscribers, and averaging them hides which one to scale.

---

## Output Format

### Capture Audit
Every current capture point, its offer, its capture rate, and the quality of subscribers it produces. Rank by revenue per subscriber, not volume.

### Offer Recommendation
The recommended primary offer, with the margin math where a discount is involved, and the reasoning against the alternatives considered.

### Placement Plan
Table of placements: location, trigger, offer, channel, and expected role. Including post-purchase and offline capture.

### Quiz Specification
If recommended: every question, its answer options, how each maps to a recommendation, the result page structure, and the profile attributes stored.

### Consent Language
Exact disclosure copy for every SMS capture point, placed where it must appear.

### Measurement Plan
What to track by source, and the threshold at which a source should be cut.

---

## Task-Specific Questions

1. What is your current email capture rate as a percentage of sessions?
2. What offer do you use today, and what does it cost you per new customer?
3. Do you have a welcome flow live?
4. Is SMS running, and how is consent collected?
5. Does the category have a genuine "which product is right for me" problem?
6. Do you have packaging, inserts, or retail distribution that could carry a QR or keyword?
7. What is revenue per subscriber over 90 days, split by capture source?

---

## Related Skills

- **lifecycle-flows**: Build the welcome flow before growing the list
- **email-sms-campaigns**: For deliverability implications of list quality and for segmenting on quiz data
- **site-cro**: For popup impact on the overall on-site experience
- **cart-and-checkout**: For post-purchase and confirmation-page capture
- **product-pages**: For back-in-stock capture on out-of-stock products
- **claims-and-compliance**: For SMS consent, disclosure language, and giveaway rules
- **post-purchase-experience**: For packaging inserts and QR capture
