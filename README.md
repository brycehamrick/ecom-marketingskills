# Ecommerce Marketing Skills for AI Agents

40 AI agent skills for ecommerce marketing. Built for DTC brands, marketplace sellers, wholesale and omnichannel brands, and the agencies that serve them. Works with Claude Code, OpenAI Codex, Cursor, Windsurf, and any agent that supports the [Agent Skills spec](https://agentskills.io).

Where a general marketing skill set assumes a software product, this one assumes a catalog: product detail pages, collection merchandising, product feeds, marketplace listings, subscriptions, post-purchase, wholesale, and peak season.

Run into a problem or have a question? [Open an issue](https://github.com/brycehamrick/ecom-marketingskills/issues).

## What are Skills?

Skills are markdown files that give AI agents specialized knowledge and workflows for specific tasks. When you add these to your project, your agent recognizes when you're working on an ecommerce marketing task and applies the right frameworks.

## How Skills Work Together

`brand-context` is the foundation. It writes `.agents/brand-context.md` — your catalog, margins, channels, customer, and constraints — and every other skill reads it before asking you anything.

```
                        ┌────────────────────────────────────────┐
                        │             brand-context              │
                        │   (read by all other skills first)     │
                        └───────────────────┬────────────────────┘
                                            │
        ┌──────────────┬───────────┬────────┴────┬───────────┬──────────────┐
        ▼              ▼           ▼             ▼           ▼              ▼
  ┌───────────┐ ┌───────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌────────────┐
  │ Product & │ │  Offer &  │ │   Paid   │ │ Organic  │ │Marketplace│ │ Conversion │
  │Merchandise│ │ Economics │ │Acquisitn │ │Discovery │ │ & Channel │ │            │
  ├───────────┤ ├───────────┤ ├──────────┤ ├──────────┤ ├──────────┤ ├────────────┤
  │product-   │ │pricing-   │ │paid-     │ │ecommerce-│ │amazon-   │ │site-cro    │
  │ pages     │ │ strategy  │ │ social   │ │ seo      │ │ growth   │ │cart-and-   │
  │collection-│ │promotions-│ │google-   │ │ai-search-│ │marketplace│ │ checkout   │
  │ merchandi │ │ and-disc  │ │ ads      │ │ visibilty│ │ -listings│ │post-purchase│
  │catalog-   │ │bundles-   │ │marketplc │ │organic-  │ │wholesale-│ │ -experience│
  │ and-feeds │ │ and-aov   │ │ -ads     │ │ social   │ │ and-retai│ │reviews-and-│
  │product-   │ │bfcm-and-  │ │ad-creativ│ │earned-   │ │internatnl│ │ reputation │
  │ launch    │ │ peak-seasn│ │creators- │ │ media    │ │ -expansn │ │experimentn │
  │           │ │           │ │ and-affil│ │          │ │          │ │            │
  └─────┬─────┘ └─────┬─────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘ └─────┬──────┘
        │             │            │            │            │             │
        └─────────────┴──────┬─────┴────────────┴────────────┴─────────────┘
                             │
        ┌────────────────────┴───────────────────┐
        ▼                                        ▼
  ┌──────────────────┐                  ┌─────────────────────┐
  │ Lifecycle &      │                  │ Measurement &       │
  │ Retention        │                  │ Planning            │
  ├──────────────────┤                  ├─────────────────────┤
  │lifecycle-flows   │                  │measurement-and-     │
  │email-sms-campaign│                  │ analytics           │
  │list-growth       │                  │profitability-and-   │
  │subscriptions-and-│                  │ incrementality      │
  │ replenishment    │                  │growth-plan          │
  │retention-and-    │                  │client-reporting     │
  │ loyalty          │                  │                     │
  └──────────────────┘                  └─────────────────────┘

  Research & diagnostics feed everything:
    customer-research · category-intel · growth-audit · claims-and-compliance
```

Every skill that produces customer-facing copy routes through `claims-and-compliance` before shipping in a regulated category.

Skill boundaries are documented in [ROUTING.md](ROUTING.md) — who owns which job, and the exact phrase that should route where.

## Available Skills

<!-- SKILLS:START -->
| Skill | Description |
|-------|-------------|
| [ad-creative](skills/ad-creative/) | When the user wants ad concepts, hooks, scripts, or copy for ecommerce advertising. Also use when the user mentions 'ad... |
| [ai-search-visibility](skills/ai-search-visibility/) | When the user wants their products or brand to appear in AI-generated answers and AI shopping surfaces. Also use when... |
| [amazon-growth](skills/amazon-growth/) | When the user wants to grow sales on Amazon — listings, keywords, content, reviews, Buy Box, account health, or FBA... |
| [bfcm-and-peak-season](skills/bfcm-and-peak-season/) | When the user wants to plan for Black Friday, the holiday season, or any peak retail moment. Also use when the user... |
| [brand-context](skills/brand-context/) | When the user wants to create or update the brand context document that every other ecommerce skill reads. Also use... |
| [bundles-and-aov](skills/bundles-and-aov/) | When the user wants to raise average order value through bundles, kits, multi-packs, or upsells. Also use when the user... |
| [cart-and-checkout](skills/cart-and-checkout/) | When the user wants to reduce cart or checkout abandonment and increase completion rate. Also use when the user... |
| [catalog-and-feeds](skills/catalog-and-feeds/) | When the user wants to fix product data, titles, attributes, or shopping feeds. Also use when the user mentions... |
| [category-intel](skills/category-intel/) | When the user wants to research competitors or map their ecommerce category — catalogs, price ladders, ad angles,... |
| [claims-and-compliance](skills/claims-and-compliance/) | When the user wants to check whether a marketing claim is defensible, or needs to follow advertising, disclosure, or... |
| [client-reporting](skills/client-reporting/) | When the user needs to report to a client or stakeholder, onboard a new client, or scope an engagement. Also use when... |
| [collection-merchandising](skills/collection-merchandising/) | When the user wants to decide what products appear on a collection page and in what order. Also use when the user... |
| [creators-and-affiliates](skills/creators-and-affiliates/) | When the user wants to work with creators, influencers, ambassadors, or affiliates. Also use when the user mentions... |
| [customer-research](skills/customer-research/) | When the user wants to understand their ecommerce customers — mining reviews, support tickets, surveys, and social... |
| [earned-media](skills/earned-media/) | When the user wants press coverage, gift guide placement, or commerce-content features. Also use when the user mentions... |
| [ecommerce-seo](skills/ecommerce-seo/) | When the user wants to improve organic search performance for an online store. Also use when the user mentions 'SEO,'... |
| [email-sms-campaigns](skills/email-sms-campaigns/) | When the user wants to plan one-time scheduled email or SMS sends, build a campaign calendar, or fix deliverability.... |
| [experimentation](skills/experimentation/) | When the user wants to design, run, or interpret an ecommerce test. Also use when the user mentions 'A/B test,' 'split... |
| [google-ads](skills/google-ads/) | When the user wants help with Google Ads for ecommerce — Shopping, Performance Max, Search, or Demand Gen. Also use... |
| [growth-audit](skills/growth-audit/) | When the user wants a full diagnostic sweep across an ecommerce brand and a prioritized list of where money is leaking.... |
| [growth-plan](skills/growth-plan/) | When the user wants an ecommerce marketing plan, budget allocation, or growth forecast. Also use when the user mentions... |
| [international-expansion](skills/international-expansion/) | When the user wants to sell into another country or improve an existing international market. Also use when the user... |
| [lifecycle-flows](skills/lifecycle-flows/) | When the user wants to build or improve automated, triggered email and SMS flows. Also use when the user mentions... |
| [list-growth](skills/list-growth/) | When the user wants to grow their email or SMS list or capture zero-party data on site. Also use when the user mentions... |
| [marketplace-ads](skills/marketplace-ads/) | When the user wants help with advertising on marketplaces or retail media networks. Also use when the user mentions... |
| [marketplace-listings](skills/marketplace-listings/) | When the user wants to optimize listings on Walmart, Etsy, TikTok Shop, or eBay. Also use when the user mentions... |
| [measurement-and-analytics](skills/measurement-and-analytics/) | When the user wants to set up or fix ecommerce tracking, analytics, or reporting infrastructure. Also use when the user... |
| [organic-social](skills/organic-social/) | When the user wants to plan or improve organic social content for an ecommerce brand. Also use when the user mentions... |
| [paid-social](skills/paid-social/) | When the user wants help with paid social advertising for ecommerce — Meta, TikTok, Pinterest, Snapchat, or Reddit.... |
| [post-purchase-experience](skills/post-purchase-experience/) | When the user wants to improve what happens between purchase and the second order — shipping communication, tracking,... |
| [pricing-strategy](skills/pricing-strategy/) | When the user wants help setting or changing ecommerce prices, price architecture, or margin structure. Also use when... |
| [product-launch](skills/product-launch/) | When the user wants to launch a new product, collection, or drop. Also use when the user mentions 'launch,' 'launch... |
| [product-pages](skills/product-pages/) | When the user wants to improve a product detail page — copy, images, variants, or conversion. Also use when the user... |
| [profitability-and-incrementality](skills/profitability-and-incrementality/) | When the user wants to know whether marketing is actually making money and which channels are truly incremental. Also... |
| [promotions-and-discounting](skills/promotions-and-discounting/) | When the user wants to plan a promotion, decide discount depth, or set a free-shipping threshold. Also use when the... |
| [retention-and-loyalty](skills/retention-and-loyalty/) | When the user wants more repeat purchases, a loyalty program, or a customer referral program. Also use when the user... |
| [reviews-and-reputation](skills/reviews-and-reputation/) | When the user wants more reviews, better review display, or help managing ratings and reputation. Also use when the... |
| [site-cro](skills/site-cro/) | When the user wants to improve sitewide ecommerce conversion outside of the product page and checkout — homepage,... |
| [subscriptions-and-replenishment](skills/subscriptions-and-replenishment/) | When the user wants to launch, grow, or fix a subscription or replenishment program. Also use when the user mentions... |
| [wholesale-and-retail](skills/wholesale-and-retail/) | When the user wants to sell through retailers, distributors, or wholesale marketplaces. Also use when the user mentions... |
<!-- SKILLS:END -->

## Installation

### Option 1: CLI Install (Recommended)

Use [npx skills](https://github.com/vercel-labs/skills) to install skills directly:

```bash
# Install all skills
npx skills add brycehamrick/ecom-marketingskills

# Install specific skills
npx skills add brycehamrick/ecom-marketingskills --skill product-pages lifecycle-flows

# List available skills
npx skills add brycehamrick/ecom-marketingskills --list
```

The CLI detects which agents you have installed and asks where to install. For Claude Code it installs into `.claude/skills/`; universal agents share `.agents/skills/`.

> [!TIP]
> If you run the command from **inside** an agent session (e.g., asking Claude Code to install the skills for you), the CLI runs non-interactively and may only install to the universal `.agents/skills/` directory, which Claude Code does not read. Pass the agent explicitly:
>
> ```bash
> npx skills add brycehamrick/ecom-marketingskills -a claude-code
> ```

### Option 2: Claude Code Plugin

```bash
# Add the marketplace
/plugin marketplace add brycehamrick/ecom-marketingskills

# Install all skills
/plugin install ecommerce-marketing-skills
```

### Option 3: Clone and Copy

```bash
git clone https://github.com/brycehamrick/ecom-marketingskills.git
cp -r ecom-marketingskills/skills/* .agents/skills/
```

### Option 4: Git Submodule

```bash
git submodule add https://github.com/brycehamrick/ecom-marketingskills.git .agents/ecom-marketingskills
```

Then reference skills from `.agents/ecom-marketingskills/skills/`.

### Option 5: Fork and Customize

1. Fork this repository
2. Customize skills for your catalog and channels
3. Clone your fork into your projects

## Start Here

Run `brand-context` first. It writes `.agents/brand-context.md`, which every other skill reads — so you describe your catalog, margins, and channels once instead of on every task.

```
"Set up brand context for my store"     → brand-context
"Audit my store"                        → growth-audit
```

`growth-audit` sweeps every surface, ranks what's leaking money, and hands each finding to the skill that fixes it. It's the fastest way to find out which of the other 38 skills you actually need.

## Usage

Ask your agent in plain language:

```
"My product page isn't converting"          → product-pages
"Write me 10 ad hooks for this product"     → ad-creative
"Set up an abandoned cart email"            → lifecycle-flows
"My Google Shopping feed has disapprovals"  → catalog-and-feeds
"My Amazon listing got suppressed"          → amazon-growth
"How do I get into Faire"                   → wholesale-and-retail
"Is my Meta ROAS real"                      → profitability-and-incrementality
"Can I say this supplement boosts immunity" → claims-and-compliance
"Plan BFCM"                                 → bfcm-and-peak-season
"Our repeat purchase rate is flat"          → retention-and-loyalty
```

Or invoke directly:

```
/product-pages
/lifecycle-flows
/growth-audit
```

## Skill Categories

### Foundation & Research
- `brand-context` — The context file every other skill reads. Start here
- `customer-research` — Voice of customer from reviews, tickets, and surveys
- `category-intel` — Competitor catalogs, price ladders, and ad angles
- `growth-audit` — Full-funnel diagnostic that routes findings to the right skill
- `claims-and-compliance` — FTC, ad policy, SMS consent, and marketplace claim rules

### Product & Merchandising
- `product-pages` — PDP copy, images, variants, fit, and objection handling
- `collection-merchandising` — What appears on collection pages and in what order
- `catalog-and-feeds` — Product data, titles, attributes, and shopping feeds
- `product-launch` — Drops, waitlists, pre-orders, seeding, and sell-through

### Offer & Economics
- `pricing-strategy` — Price architecture, margin, MAP, and price testing
- `promotions-and-discounting` — Discount mechanics, thresholds, and promo cadence
- `bundles-and-aov` — Bundles, multi-packs, upsells, and post-purchase offers
- `bfcm-and-peak-season` — BFCM, Q4, gifting, Q5, and Prime Day planning

### Paid Acquisition
- `paid-social` — Meta, TikTok, Pinterest, Snapchat, Reddit
- `google-ads` — Shopping, Performance Max, Search, Demand Gen
- `marketplace-ads` — Amazon PPC, Walmart Connect, Instacart, Criteo
- `ad-creative` — Hooks, angles, UGC scripts, and creative testing
- `creators-and-affiliates` — Seeding, whitelisting, affiliates, ambassadors

### Organic Discovery
- `ecommerce-seo` — Indexation, collection pages, schema, buying guides
- `ai-search-visibility` — LLM citations, AI Overviews, agentic commerce
- `organic-social` — TikTok, Reels, Pinterest, YouTube, social listening
- `earned-media` — Press, gift guides, and commerce-content placements

### Marketplace & Channel
- `amazon-growth` — Listings, A+, keywords, Vine, Buy Box, FBA economics
- `marketplace-listings` — Walmart, Etsy, TikTok Shop, eBay
- `wholesale-and-retail` — Line sheets, Faire, retailer pitches, MAP, sell-through
- `international-expansion` — Markets, duties, localization, GPSR, EPR

### Conversion
- `site-cro` — Homepage, navigation, site search, mobile, speed, trust
- `cart-and-checkout` — Cart, checkout, payment methods, cost surprise
- `post-purchase-experience` — Shipping, tracking, WISMO, inserts, returns
- `reviews-and-reputation` — Collection, display, syndication, ratings recovery
- `experimentation` — Test design, sample size, holdouts, and honest reads

### Lifecycle & Retention
- `lifecycle-flows` — The twelve automated email and SMS flows
- `email-sms-campaigns` — Campaign calendar, segmentation, deliverability
- `list-growth` — Popups, quizzes, SMS opt-in, and zero-party data
- `subscriptions-and-replenishment` — Subscribe and save, save flows, dunning
- `retention-and-loyalty` — Cohorts, RFM, loyalty, referral, winback

### Measurement & Planning
- `measurement-and-analytics` — GA4, server-side, CAPI, UTMs, dashboards
- `profitability-and-incrementality` — MER, contribution margin, geo holdouts
- `growth-plan` — Budget allocation, forecasting, channel go/no-go
- `client-reporting` — Onboarding, monthly reports, QBRs, proposals

## Tools

[`tools/REGISTRY.md`](tools/REGISTRY.md) indexes the ecommerce marketing stack — Shopify, Klaviyo, Recharge, Yotpo, Amazon SP-API, Merchant Center, Triple Whale, Gorgias, Loop, and more — with auth, endpoints, and agent notes per tool. Skills reference them by name.

Zero-dependency Node CLIs for a subset live in [`tools/clis/`](tools/clis/).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). New skills should follow [SKILL-TEMPLATE.md](SKILL-TEMPLATE.md) and register their boundaries in [ROUTING.md](ROUTING.md).

## Credits

Forked from [marketingskills](https://github.com/coreyhaines31/marketingskills) by [Corey Haines](https://corey.co), which covers the same ground for B2B SaaS. The skill set here was rewritten from scratch for ecommerce; the repo scaffolding, validation, and plugin structure are his.

## License

[MIT](LICENSE) — use these however you want.
