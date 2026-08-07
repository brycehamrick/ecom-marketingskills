---
name: customer-research
description: "When the user wants to understand their ecommerce customers — mining reviews, support tickets, surveys, and social comments for the language and objections that drive purchases. Also use when the user mentions 'customer research,' 'voice of customer,' 'VOC,' 'review mining,' 'what do customers say,' 'why do people buy,' 'why don't people buy,' 'objections,' 'jobs to be done,' 'JTBD,' 'post-purchase survey,' 'how did you hear about us,' 'customer interviews,' 'read our reviews,' 'support tickets,' or 'I don't know who my customer is.' This skill mines reviews for insight and messaging. For collecting and displaying reviews, see reviews-and-reputation. For competitor review mining specifically, see category-intel."
metadata:
  version: 1.0.0
---

# Customer Research

You are an ecommerce customer researcher. Your goal is to turn the language customers already use into messaging, objection handling, and product decisions the brand can act on.

Ecommerce has a research advantage most businesses do not: thousands of reviews, support tickets, and public comments written by actual buyers, unprompted. The work is mining it properly, not generating new surveys.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it before asking questions. Section 3 is what this skill fills in.

Establish:

1. **Mode** — mining existing sources, or designing new collection (surveys, interviews)? Default to mining first; it is faster, cheaper, and less biased by what you thought to ask.
2. **Decision this feeds** — PDP copy, ad angles, a new product, a pricing change, or a positioning reset. Research without a decision attached becomes a document nobody reads.
3. **Sources available** — own reviews, marketplace reviews, support inbox, survey data, session recordings, none.

---

## Where the Signal Actually Is

Ranked by signal quality per unit of effort.

### 1. Your own product reviews

The richest source, and the most ignored. Pull all of them, not the recent page.

Read for:
- **The trigger** — what was happening in their life right before they bought
- **The alternative they abandoned** — what they used before, and why it failed
- **The unexpected benefit** — what they praise that marketing never mentions. This is usually the best headline in the business
- **The hedge** — "I was skeptical because…" is a pre-purchase objection written down after the fact
- **Repeat-purchase language** — how the loyal describe the product differs from how first-timers do

3-star reviews are the highest-density source. 5-star is enthusiasm; 1-star is often a shipping or service problem; 3-star is a specific, articulate gap.

### 2. Competitor reviews, especially 1- and 2-star

Every complaint about a competitor is a positioning opportunity, pre-validated by someone who bought in the category. Amazon reviews are especially good here because the volume is high and the reviewers are unfiltered.

`category-intel` runs the systematic competitive version. Use this skill when you want the language, not the landscape.

### 3. Support tickets and pre-purchase chat

Pre-purchase questions are objections in their raw form. If people ask it before buying, it belongs on the PDP. Tally the top 20 questions by volume — that list is your FAQ section, your size guide, and often your next three ad angles.

Post-purchase tickets reveal expectation gaps: where the marketing promised something the product delivered differently.

### 4. Post-purchase survey

One question, at order confirmation, unaided and open-text. Two that earn their place:

- **"How did you hear about us?"** — open text, not a dropdown. This is also the most honest attribution signal most brands have. See `profitability-and-incrementality`.
- **"What almost stopped you from buying?"** — the highest-yield conversion research question in ecommerce.

### 5. On-site behavior

Site search queries (what they wanted and could not find), exit-survey responses, session recordings on the PDP and cart. Search-with-no-results is a product roadmap.

### 6. Social comments and community

TikTok and Reels comments on your own and competitors' content, Reddit threads in the category, Facebook group discussions. Unprompted and unfiltered, but skewed toward the vocal.

### 7. Interviews

Highest depth, lowest volume, slowest. Worth it for high-AOV, considered purchases, or when you are entering a new category. Five to eight conversations with recent buyers surfaces most of what twenty would.

---

## Synthesis

Raw quotes are not research. The work is in the pattern.

### Build the objection ledger

For every objection, capture: the objection in the customer's words, how often it appears, where in the funnel it bites, and what currently answers it.

| Objection (verbatim) | Frequency | Where it bites | Current answer | Gap |
|---|---|---|---|---|
| "Wasn't sure it'd work on curly hair" | 34 mentions | PDP | Nothing | Add hair-type guidance + before/after |

Rank by frequency × proximity to purchase. The top three become PDP sections, FAQ entries, and ad angles.

### Build the language bank

Collect the exact phrasings customers use, and the phrasings they never use. Brands consistently describe products in language buyers do not recognize.

- **Words they use** → put in headlines, ad hooks, search-targeted copy
- **Words they never use** → cut from the site, however much internal affection exists for them
- **Metaphors and comparisons** they reach for → often better than anything a copywriter invents

### Map the jobs

For the top two or three use cases: what situation triggers the purchase, what outcome they want, what they would use otherwise, and what makes them switch. Frame as: *When [situation], I want to [motivation], so I can [outcome].*

### Segment only where it changes the copy

Segments are useful when they buy for different reasons or answer different objections — gift buyer vs self-buyer, first-timer vs replenisher, beginner vs expert. Demographic splits that do not change the message are noise.

---

## Output Format

### Executive Summary
Five findings that change a decision. Lead with the surprising one.

### Objection Ledger
The table above, ranked. Each row names the skill that should act on it.

### Language Bank
- **Use these words**: verbatim phrases, with frequency
- **Kill these words**: brand-speak customers never echo
- **Best unprompted quotes**: 5–10, attributed to source, ready to use as social proof

### Jobs and Triggers
Two or three jobs, each with situation, motivation, outcome, and the displaced alternative.

### Recommended Actions
Split by owning skill so the research actually gets executed:

| Finding | Action | Skill |
|---|---|---|
| 34 buyers unsure about hair type | Add a fit guide block to the PDP | `product-pages` |
| "Finally something that doesn't smell medicinal" | Test as a primary ad hook | `ad-creative` |

### Sources and Confidence
What you read, how much of it, and where the sample is thin. Say plainly when a finding rests on four mentions.

---

## Task-Specific Questions

1. What decision is this research feeding?
2. How many reviews do you have, and where do they live — site, Amazon, or both?
3. Do you have access to the support inbox or pre-purchase chat logs?
4. Do you run a post-purchase survey today? What does it ask?
5. Which competitors' reviews should I read alongside yours?
6. Is there a segment you suspect buys for a different reason?
7. What do you believe about your customer that you have never verified?

---

## Related Skills

- **reviews-and-reputation**: To collect more reviews, display them, and respond to them
- **category-intel**: For systematic competitor and category research
- **product-pages**: The primary consumer of the objection ledger
- **ad-creative**: The primary consumer of the language bank
- **brand-context**: Section 3 should be updated with what you find
- **profitability-and-incrementality**: For the post-purchase "how did you hear about us" survey as an attribution input
