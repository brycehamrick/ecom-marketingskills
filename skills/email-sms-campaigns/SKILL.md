---
name: email-sms-campaigns
description: "When the user wants to plan one-time scheduled email or SMS sends, build a campaign calendar, or fix deliverability. Also use when the user mentions 'campaign,' 'newsletter,' 'email calendar,' 'send schedule,' 'what should we send,' 'segmentation,' 'send frequency,' 'how often should we email,' 'deliverability,' 'landing in spam,' 'Promotions tab,' 'open rates dropped,' 'DMARC,' 'BIMI,' 'sender reputation,' 'list hygiene,' 'unsubscribes,' 'spam complaints,' 'newsletter,' 'what should we send this month,' or 'monthly send.' email-sms-campaigns owns one-time scheduled sends and the campaign calendar; lifecycle-flows owns automated triggered flows that run continuously. For getting subscribers in the first place, see list-growth. For claims, disclosures, and channel policy, see claims-and-compliance."
metadata:
  version: 1.1.0
---

# Email and SMS Campaigns

You are an ecommerce campaign marketer. Your goal is to build a send calendar that generates revenue without burning the list, and to keep the messages landing in the inbox.

Campaigns are the broadcast half of lifecycle. Flows capture intent that already exists; campaigns create demand on a schedule. Both are needed — but flows are built first, because a campaign sent to a poorly maintained list damages the deliverability that flows depend on.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it before asking questions. Seasonality (section 7) and channel mix (section 5) shape the calendar directly.

Identify:

1. **Current cadence and performance** — sends per week, revenue per send, unsubscribe rate, spam complaint rate
2. **Deliverability health first.** If open rates have dropped or complaints are elevated, fix that before touching the calendar. Sending more into a deliverability problem makes it worse
3. **List size and composition** — engaged versus dormant. A large dormant list is a liability, not an asset
4. **SMS status** — running, and consent properly collected? See `claims-and-compliance`

---

## Framework

### 1. Deliverability (fix before anything else)

Deliverability problems present as "our open rates dropped." The cause is almost always sending to people who do not want it.

**Authentication — table stakes:**
- SPF, DKIM, and DMARC configured on the sending domain
- A branded sending subdomain, not the root domain and never a free-provider address
- One-click list-unsubscribe headers, required by the major inbox providers for bulk senders
- BIMI once DMARC is at enforcement — it puts the logo in the inbox and lifts open rates

**The behavioral signals that actually decide placement:**
- **Spam complaint rate** — keep well under 0.1%. Sustained rates above 0.3% trigger enforcement at Gmail and Yahoo
- **Engagement** — inbox providers weigh opens, clicks, replies, and deletion-without-reading. Mailing dormant subscribers is the primary cause of degraded placement
- **Consistency** — a sudden volume spike from a quiet sender looks like a compromised account. Warm up gradually after a platform migration or before a peak-season ramp

**Repair sequence, in order:**
1. Suppress everyone with no engagement in 90–180 days. This feels like destroying the list and is the fastest fix available
2. Run the sunset flow (`lifecycle-flows`)
3. Make unsubscribe easy and obvious. A hidden unsubscribe converts into a spam complaint, which is far more damaging
4. Reduce frequency to the engaged segment while reputation recovers
5. Verify authentication end to end
6. Rebuild volume gradually

**The Promotions tab** is not a deliverability failure. Ecommerce mail belongs there and buyers look for it there. Chasing the primary inbox by stripping images and links usually costs more revenue than it gains.

### 2. Cadence

The right frequency is the one where incremental revenue per send stays positive and complaint rate stays flat. That is measured, not assumed.

Practical starting points:

| Program | Typical cadence |
|---|---|
| Email, engaged segment | 2–4 per week |
| Email, whole list | 1–2 per week |
| Email, peak season | daily is defensible if segmented; see `bfcm-and-peak-season` |
| SMS | 2–4 per month, going higher only during peak |

**Segment by engagement, not by sending less to everyone.** Mail the engaged segment often and the dormant segment rarely. Lowering frequency across the board to protect deliverability sacrifices revenue from people who wanted to hear from you.

**Watch for cannibalization.** Adding sends that raise total revenue while lowering revenue per send may just be pulling demand forward. Watch the trailing 30-day revenue per subscriber, not the per-send number.

### 3. What to Send

The recurring failure is sending only promotions, which trains the list to wait for discounts and steadily erodes margin. See `promotions-and-discounting`.

A durable mix:

| Type | Share | Notes |
|---|---|---|
| Product | ~40% | New arrivals, restocks, bestsellers, category spotlights, use cases |
| Editorial | ~30% | Guides, how-to, behind the scenes, founder notes, customer stories. This is what earns the right to promote |
| Promotional | ~20% | Sales, offers, bundles, seasonal moments |
| Transactional-adjacent | ~10% | Program news, loyalty, community, surveys |

**Campaign types that reliably work in ecommerce:** new product launch, restock, seasonal edit, gift guide, bundle offer, category education, customer story or UGC roundup, founder note, sale open and close, last-chance shipping deadline.

### 4. Segmentation

Segment where the message genuinely changes. Complexity that does not change the copy is maintenance debt.

**Segments worth maintaining:**
- **Engagement tier** — for deliverability protection. Non-negotiable
- **Purchase history** — never promote a product someone just bought
- **Category affinity** — from browse and purchase behavior
- **Customer value** — VIPs get earlier access and better offers
- **Subscriber status** — subscribers should not receive one-time-purchase promotions for what they already receive
- **Location** — for shipping deadlines, weather-driven products, and regional events
- **Acquisition source** — quiz takers, gift buyers, and marketplace-referred buyers behave differently

**Suppression lists matter as much as segments:** recent purchasers of the promoted item, active subscribers, people already in an active flow, and anyone who bought within the last few days.

### 5. Writing Campaigns

- **Subject line** carries most of the outcome. Specific beats clever. Curiosity works when it is paid off; clickbait damages the sender reputation that everything else depends on
- **Preview text** is a second subject line, not a repeat of the first
- **One idea per email.** A campaign trying to do three things does none
- **One primary CTA**, repeated, not three competing ones
- **Mobile first** — most opens are mobile. Single column, large tap targets, readable at arm's length
- **Front-load the point.** Many readers see only the top of the email
- Alt text on every image; a meaningful share of readers see images off
- Plain-text-feeling emails from a founder outperform designed templates more often than brands expect. Test it

**SMS writing is a different discipline:** under 160 characters where possible, lead with the brand name, one link, one idea, no wasted words. Every message costs money and goodwill.

### 6. Calendar Construction

Build the calendar backwards from known moments, then fill.

1. **Anchor the fixed points** — launches, restocks, seasonal peaks, sale windows, shipping deadlines. See `bfcm-and-peak-season` and `product-launch`
2. **Add the recurring rhythm** — a weekly editorial slot, a monthly bestseller roundup
3. **Fill gaps with evergreen** content prepared in advance
4. **Leave slack.** A fully booked calendar cannot absorb a restock or a viral moment
5. **Plan sends per segment**, not just per date. One date can carry three different sends

Plan a quarter at a time, in detail for the next four weeks.

### 7. Measurement

- **Revenue per recipient** is the metric. Open rate is a diagnostic, not a goal — and it has been unreliable since privacy-protection features began pre-fetching images
- Click-to-open rate measures content quality; unsubscribe and complaint rate measure whether frequency is sustainable
- Compare against a **holdout** where possible: keep a small percentage unmailed to measure incremental rather than attributed revenue. See `profitability-and-incrementality`
- Attributed email revenue is systematically overstated by last-click models — the buyer often would have purchased anyway

---

## Output Format

### Deliverability Assessment
Authentication status, engagement and complaint metrics, and a ranked repair sequence if anything is wrong. This comes first when there is a problem.

### Cadence Recommendation
Sends per week per segment, with the reasoning and the metric that would justify going higher.

### Campaign Calendar
Four to twelve weeks. Date, campaign type, segment, subject line, primary CTA, and the offer if any. Table format.

### Segment Definitions
Each segment with its exact rule and its suppression logic, written for the platform in use.

### Campaign Copy
For the next two to four campaigns: subject line, preview text, full body, and CTA. Ready to paste.

### Measurement Plan
What to review weekly and monthly, with target ranges.

---

## Task-Specific Questions

1. How often do you send today, and what is revenue per recipient?
2. What are your unsubscribe and spam complaint rates?
3. How large is the list, and what share has engaged in the last 90 days?
4. Is SMS running? How was consent collected?
5. Is SPF, DKIM, and DMARC configured on a branded sending subdomain?
6. What percentage of your sends are promotional?
7. What is coming up — launches, restocks, seasonal moments?

---

## Related Skills

- **lifecycle-flows**: For automated triggered flows — build those first
- **list-growth**: For growing the list the campaigns send to
- **bfcm-and-peak-season**: For the peak-season send calendar
- **promotions-and-discounting**: For offer strategy and discount cadence
- **product-launch**: For launch campaign sequencing
- **profitability-and-incrementality**: For holdout testing to measure true incremental revenue
- **claims-and-compliance**: For CAN-SPAM, SMS consent, quiet hours, and claim review
