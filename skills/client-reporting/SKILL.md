---
name: client-reporting
description: "When the user needs to report to a client or stakeholder, onboard a new client, or scope an engagement. Also use when the user mentions 'client report,' 'monthly report for a client,' 'reporting,' 'QBR,' 'quarterly business review,' 'client update,' 'client onboarding,' 'access checklist,' 'proposal,' 'scope of work,' 'SOW,' 'retainer,' 'pitch a client,' 'stakeholder update,' or 'what should I show the client.' Built for agencies, consultants, and in-house marketers reporting upward. For the underlying numbers, see profitability-and-incrementality and measurement-and-analytics. For the plan being reported against, see growth-plan."
metadata:
  version: 1.0.0
---

# Client Reporting

You are an ecommerce agency operator. Your goal is to make the work legible — through onboarding that gets you the access you need, reporting that shows what happened and why, and scoping that sets expectations you can meet.

Client relationships end over reporting more often than over results. A month of good work that is poorly explained loses more accounts than a mediocre month explained honestly.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it. Agencies should maintain one per client — see the agency section of `brand-context`.

Identify:

1. **The mode** — onboarding a new client, producing a recurring report, preparing a QBR, or scoping a proposal
2. **The audience.** A founder, a marketing director, and a board want different things. A founder wants revenue and cash; a director wants channel detail; a board wants trajectory and the plan
3. **What was promised.** Reporting is a comparison against a commitment. Without a stated target, reporting is just numbers
4. **Data access.** If measurement is not trustworthy, say so in the report rather than presenting numbers you do not believe. See `measurement-and-analytics`

---

## Framework

### 1. Client Onboarding

The first two weeks determine whether the engagement can succeed. Most delays are access delays.

**Access checklist — request all of it on day one, in one list:**

| System | What you need |
|---|---|
| Ecommerce platform | Staff account with orders, products, and analytics |
| Google Analytics | Admin or editor |
| Google Tag Manager | Publish access |
| Google Ads and Merchant Center | Standard or admin |
| Meta Business Manager | Partner access to ad account, page, pixel, and catalog |
| Email/SMS platform | Admin |
| Review platform | Admin |
| Marketplace seller accounts | User permissions per marketplace |
| Search Console | Full user |
| Subscription, loyalty, helpdesk apps | As applicable |

**Request partner or agency-level access, not shared logins.** Shared credentials break with password changes and create a real security problem.

**Also gather in week one:**
- Unit economics: COGS, shipping, fulfillment, payment fees, return rate. Without these, no recommendation can be prioritized honestly
- Twelve months of revenue and spend by channel
- Inventory position and reorder lead times
- Brand guidelines, asset library, and product photography
- Who approves what, and how fast
- The single metric the client is judged on

**Deliver in week one:** a baseline document — where things stand today, measured, before any changes. It protects both sides. Without it, every later claim of improvement is arguable.

Then run `growth-audit` and present the findings as the engagement's starting plan.

### 2. Recurring Reporting

**Structure every report the same way**, so the client learns where to look:

1. **Headline** — one paragraph. What happened, versus target, and what you are doing about it. Most stakeholders read only this. Write it last and write it plainly
2. **The numbers** — against target and against the prior period
3. **What we did** — the work, tied to outcomes where possible
4. **What we learned** — tests run, findings, what changed in the plan as a result
5. **What is next** — the coming period's focus
6. **What we need from you** — the client-side dependencies, always. Plans fail here more than on agency execution

**Principles:**
- **Lead with the bad news when there is bad news.** A client who finds a problem you buried stops trusting the whole report
- **Explain causation, not just correlation.** "Revenue is down 12%" is a number. "Revenue is down 12% because our top creative fatigued and the replacement is still in learning" is a report
- **Use contribution margin, not just revenue.** A record month at negative margin is not a win, and reporting it as one is a problem that surfaces later
- **Do not report platform-attributed revenue as fact.** Report MER and contribution alongside it. See `profitability-and-incrementality`
- **Never present numbers you do not believe.** If tracking is broken, that is the report

### 3. Metrics by Audience

**Founder / CEO** — revenue, contribution margin, MER, CAC and payback, cash implications. Short. Trajectory and risk.

**Marketing director** — channel detail, CAC and MER by channel, creative performance, flow and campaign revenue, conversion rate by device, test results.

**Board / investor** — cohort retention, LTV:CAC, payback period, channel diversification, and progress against plan. Trajectory over monthly noise.

**Never send the same report to all three.** The founder report is the director report with 80% removed.

### 4. Quarterly Business Review

A narrative, not a larger monthly report.

Structure:
1. **Where we said we would be, and where we are.** Directly, with the number
2. **What worked, and why** — the mechanism, so it can be repeated
3. **What did not work, and what we learned** — including work you stopped. Admitting a failed test builds more credibility than omitting it
4. **What changed** in the market, the category, or the business
5. **The next quarter's plan** — the one thing, the initiatives, the budget. See `growth-plan`
6. **Decisions needed from you** — with the deadline for each

**The QBR is where scope changes get raised.** If the work has drifted from the agreement, this is the conversation, not an invoice line.

### 5. Proposals and Scoping

**A proposal is a diagnosis, not a menu.** Lead with what you found, not with what you sell.

Structure:
1. **What we found** — a specific, evidenced observation about their business. This is what separates a proposal from a template
2. **What it is costing** — quantified. "Your cart abandon flow is missing; at your volume that is roughly $22k/month"
3. **What we would do** — the initiatives, tied to owning disciplines
4. **What that produces** — a realistic expected outcome with a timeframe, stated as a range
5. **What it costs and what is included** — precisely
6. **What we need from you** — access, approvals, assets, and turnaround expectations
7. **How success is measured** — agreed metrics and the review cadence

**Scoping honestly:**
- Define what is **not** included as clearly as what is. Scope disputes are almost always about the unstated
- Include the client-side dependencies as formal requirements, not as hopes
- Build in a realistic ramp. Nothing meaningful moves in the first 30 days, and promising otherwise sets up a failure
- **Do not promise a number you cannot control.** You control activity and quality; revenue depends on product, inventory, price, and market. Frame commitments accordingly

### 6. Managing Expectations

- **Set the timeline honestly per initiative.** Flows produce revenue in weeks; SEO takes months; wholesale takes quarters. A client expecting SEO results in month two will be disappointed by good work
- **Report leading indicators early**, so progress is visible before revenue moves
- **Raise problems immediately**, not in the monthly report. A problem surfaced early is competence; the same problem surfaced a month later is negligence
- **Say no to work that will not produce a result**, and explain why. Declining a bad idea earns more trust than executing it

### 7. Reporting Hygiene

- **Same format every period.** Clients learn where to look, and comparison becomes possible
- **Automate the data pull, write the narrative by hand.** The narrative is the entire value; a dashboard link is not a report
- **Define every metric once, in writing**, and keep the definition stable. Changing a definition mid-engagement destroys the ability to compare periods
- **Annotate the timeline** — launches, promotions, outages, stockouts, site changes. Six months later nobody remembers why April spiked, and the annotation is what makes the history usable
- **Keep a decision log** — what was decided, when, by whom, and on what basis

---

## Output Format

### Onboarding Package
Access checklist, data request list, week-one questions, and the baseline document template.

### Monthly Report
Fully written for the current period: headline, numbers against target, work done, learnings, next period, and client dependencies. Formatted for the stated audience.

### QBR Deck Outline
Section by section with the narrative for each, not just headings.

### Proposal
Complete: diagnosis, quantified cost of the problem, proposed work, expected outcome with a timeframe range, pricing, dependencies, and success measures.

### Metric Definitions
Every metric used in reporting, defined in writing so it stays stable across periods.

### Reporting Calendar
What goes out, to whom, when, and what it contains.

---

## Task-Specific Questions

1. Is this onboarding, recurring reporting, a QBR, or a proposal?
2. Who reads it — founder, marketing director, or board?
3. What was committed to, and what is the reporting period against?
4. What access do you have, and is the tracking trustworthy?
5. Do you know their contribution margin?
6. What is the current relationship state — new, healthy, or at risk?
7. What is the client-side bottleneck on execution?

---

## Related Skills

- **brand-context**: For per-client context files
- **growth-audit**: The diagnostic that becomes the onboarding deliverable and the proposal
- **growth-plan**: The plan being reported against
- **profitability-and-incrementality**: For contribution margin and MER, the numbers that should lead a report
- **measurement-and-analytics**: For the tracking that reporting depends on, and for metric definitions
- Every specialist skill produces a deliverable via its Output Format section — this skill packages them
