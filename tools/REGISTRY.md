# Tool Registry

Agent-compatible tools for ecommerce marketing. Each entry links to an integration guide with auth, endpoints, and agent-relevant notes.

**How to use this file:** find the job, pick the tool, read the guide. Skills reference tools by name — when a skill says "see `catalog-and-feeds`," and you need the API for Merchant Center, this is where you find it.

- **API** — REST/GraphQL available
- **MCP** — has a Model Context Protocol server
- **CLI** — a zero-dependency Node script lives in [`clis/`](clis/)
- **Guide** — integration doc in [`integrations/`](integrations/)

---

## By Job

### Store platform

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Shopify | ✓ | - | ✓ | [shopify](integrations/shopify.md) |
| WooCommerce | ✓ | - | - | [woocommerce](integrations/woocommerce.md) |
| BigCommerce | ✓ | - | - | [bigcommerce](integrations/bigcommerce.md) |
| Stripe | ✓ | ✓ | - | [stripe](integrations/stripe.md) |

**Agent recommendation**: the platform is the source of truth for revenue and orders. Reconcile every analytics number against it before drawing conclusions.

### Product data and feeds

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Google Merchant Center | ✓ | - | - | [google-merchant-center](integrations/google-merchant-center.md) |
| Meta Catalog | ✓ | - | - | [meta-catalog](integrations/meta-catalog.md) |

**Agent recommendation**: start every feed investigation with `productstatuses` (Merchant Center) and `diagnostics` (Meta). Disapprovals are the fastest available revenue win and they are usually unnoticed. See `catalog-and-feeds`.

### Marketplaces

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Amazon SP-API | ✓ | - | - | [amazon-sp-api](integrations/amazon-sp-api.md) |
| Amazon Ads | ✓ | - | - | [amazon-ads](integrations/amazon-ads.md) |
| Walmart Marketplace | ✓ | - | - | [walmart-marketplace](integrations/walmart-marketplace.md) |
| Etsy | ✓ | - | - | [etsy](integrations/etsy.md) |
| TikTok Shop | ✓ | - | - | [tiktok-shop](integrations/tiktok-shop.md) |

**Agent recommendation**: TACoS requires joining Amazon Ads spend to SP-API total sales — neither API reports it alone. That join is what tells you whether ads are buying rank or renting sales. See `amazon-growth` and `marketplace-ads`.

### Wholesale

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Faire | ✓ | - | - | [faire](integrations/faire.md) |

**Agent recommendation**: Faire reports sell-**in**, not sell-through. Reordering depends on sell-through, so measure it separately. See `wholesale-and-retail`.

### Email and SMS

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Klaviyo | ✓ | - | ✓ | [klaviyo](integrations/klaviyo.md) |
| Postscript | ✓ | - | - | [postscript](integrations/postscript.md) |
| Attentive | ✓ | - | - | [attentive](integrations/attentive.md) |
| Omnisend | ✓ | - | - | [omnisend](integrations/omnisend.md) |
| Sendlane | ✓ | - | - | [sendlane](integrations/sendlane.md) |
| Customer.io | ✓ | - | ✓ | [customer-io](integrations/customer-io.md) |
| Mailchimp | ✓ | ✓ | ✓ | [mailchimp](integrations/mailchimp.md) |
| ActiveCampaign | ✓ | - | ✓ | [activecampaign](integrations/activecampaign.md) |
| Brevo | ✓ | - | ✓ | [brevo](integrations/brevo.md) |
| Kit | ✓ | - | ✓ | [kit](integrations/kit.md) |
| beehiiv | ✓ | - | ✓ | [beehiiv](integrations/beehiiv.md) |
| AudienceTap | ✓ | - | - | [audiencetap](integrations/audiencetap.md) |
| Twilio | ✓ | - | - | [twilio](integrations/twilio.md) |
| Plivo | ✓ | - | - | [plivo](integrations/plivo.md) |
| Resend | ✓ | ✓ | ✓ | [resend](integrations/resend.md) |
| Postmark | ✓ | - | ✓ | [postmark](integrations/postmark.md) |
| SendGrid | ✓ | - | ✓ | [sendgrid](integrations/sendgrid.md) |
| Sequenzy | ✓ | ✓ | - | [sequenzy](integrations/sequenzy.md) |
| NitroSend | ✓ | ✓ | - | [nitrosend](integrations/nitrosend.md) |
| OneSignal | ✓ | - | ✓ | [onesignal](integrations/onesignal.md) |

**Agent recommendation**: Klaviyo for DTC on Shopify; Postscript or Attentive when SMS is the primary channel. Audit **flow coverage** against the twelve flows in `lifecycle-flows` before optimizing any content — a missing flow beats a better version of an existing one.

### Subscriptions

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Recharge | ✓ | - | - | [recharge](integrations/recharge.md) |
| Skio | ✓ | - | - | [skio](integrations/skio.md) |
| Stay AI | ✓ | - | - | [stay-ai](integrations/stay-ai.md) |

**Agent recommendation**: always split churn into voluntary and involuntary. Failed payments are the cheapest churn to fix and they are usually a large share. See `subscriptions-and-replenishment`.

### Reviews and UGC

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Okendo | ✓ | - | - | [okendo](integrations/okendo.md) |
| Yotpo | ✓ | - | - | [yotpo](integrations/yotpo.md) |
| Judge.me | ✓ | - | - | [judgeme](integrations/judgeme.md) |
| Stamped | ✓ | - | - | [stamped](integrations/stamped.md) |
| Loox | ✓ | - | - | [loox](integrations/loox.md) |
| Trustpilot | ✓ | - | ✓ | [trustpilot](integrations/trustpilot.md) |

**Agent recommendation**: bulk-export the full review corpus for voice-of-customer mining, not the widget endpoint. Filter to 3-star first — highest signal density. Okendo for structured attribute capture (fit, skin type), Loox for photo-first. See `reviews-and-reputation` and `customer-research`.

### Loyalty and referral

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Smile.io | ✓ | - | - | [smile-io](integrations/smile-io.md) |
| LoyaltyLion | ✓ | - | - | [loyaltylion](integrations/loyaltylion.md) |
| Mention Me | ✓ | - | ✓ | [mention-me](integrations/mention-me.md) |
| Dub | ✓ | ✓ | ✓ | [dub-co](integrations/dub-co.md) |

**Agent recommendation**: model the points liability before recommending a richer program, and check whether the program changes behavior or just rewards behavior that was already happening. See `retention-and-loyalty`.

### Post-purchase and returns

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Loop Returns | ✓ | - | - | [loop-returns](integrations/loop-returns.md) |
| Redo | ✓ | - | - | [redo](integrations/redo.md) |
| AfterShip | ✓ | - | - | [aftership](integrations/aftership.md) |
| Gorgias | ✓ | - | - | [gorgias](integrations/gorgias.md) |
| Intercom | ✓ | - | ✓ | [intercom](integrations/intercom.md) |

**Agent recommendation**: return reason codes are the highest-value unread dataset in most stores. Route each reason to the upstream surface causing it. Trigger review requests on **delivery plus a use delay**, never on order date. See `post-purchase-experience`.

### Paid advertising

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Meta Ads | ✓ | - | ✓ | [meta-ads](integrations/meta-ads.md) |
| Google Ads | ✓ | ✓ | ✓ | [google-ads](integrations/google-ads.md) |
| TikTok Ads | ✓ | - | ✓ | [tiktok-ads](integrations/tiktok-ads.md) |
| Pinterest Ads | ✓ | - | - | [pinterest-ads](integrations/pinterest-ads.md) |
| Snapchat Ads | ✓ | - | - | [snapchat-ads](integrations/snapchat-ads.md) |
| LinkedIn Ads | ✓ | - | ✓ | [linkedin-ads](integrations/linkedin-ads.md) |
| Instacart Ads | ✓ | - | - | [instacart-ads](integrations/instacart-ads.md) |
| Criteo | ✓ | - | - | [criteo](integrations/criteo.md) |

**Agent recommendation**: never judge a channel on platform-reported ROAS. Sum what every platform claims and compare it to actual revenue — the excess is the size of the problem. Manage on MER and test incrementality. See `profitability-and-incrementality`.

### Analytics and attribution

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| GA4 | ✓ | ✓ | ✓ | [ga4](integrations/ga4.md) |
| Triple Whale | ✓ | - | - | [triple-whale](integrations/triple-whale.md) |
| Northbeam | ✓ | - | - | [northbeam](integrations/northbeam.md) |
| Polar Analytics | ✓ | - | - | [polar-analytics](integrations/polar-analytics.md) |
| Elevar | ✓ | - | - | [elevar](integrations/elevar.md) |
| PostHog | ✓ | - | - | [posthog](integrations/posthog.md) |
| Mixpanel | ✓ | - | ✓ | [mixpanel](integrations/mixpanel.md) |
| Amplitude | ✓ | - | ✓ | [amplitude](integrations/amplitude.md) |
| Segment | ✓ | - | ✓ | [segment](integrations/segment.md) |
| Plausible | ✓ | - | ✓ | [plausible](integrations/plausible.md) |
| Adobe Analytics | ✓ | - | ✓ | [adobe-analytics](integrations/adobe-analytics.md) |
| Supermetrics | ✓ | ✓ | ✓ | [supermetrics](integrations/supermetrics.md) |
| Coupler | ✓ | ✓ | ✓ | [coupler](integrations/coupler.md) |

**Agent recommendation**: before any analysis, compare platform orders to analytics purchases for the last 30 days. A gap over ~5% means the data is unreliable and every downstream conclusion is suspect. See `measurement-and-analytics`.

### Conversion and merchandising

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Rebuy | ✓ | - | - | [rebuy](integrations/rebuy.md) |
| Searchspring | ✓ | - | - | [searchspring](integrations/searchspring.md) |
| Hotjar | ✓ | - | ✓ | [hotjar](integrations/hotjar.md) |
| Optimizely | ✓ | - | ✓ | [optimizely](integrations/optimizely.md) |
| Typeform | ✓ | - | ✓ | [typeform](integrations/typeform.md) |

**Agent recommendation**: run the sample-size calculation before designing any test. If the required duration exceeds a couple of months, ship the change on judgment instead. See `experimentation`.

### SEO and search

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Google Search Console | ✓ | - | ✓ | [google-search-console](integrations/google-search-console.md) |
| Semrush | ✓ | - | ✓ | [semrush](integrations/semrush.md) |
| Ahrefs | ✓ | - | ✓ | [ahrefs](integrations/ahrefs.md) |
| DataForSEO | ✓ | - | ✓ | [dataforseo](integrations/dataforseo.md) |
| Keywords Everywhere | ✓ | - | ✓ | [keywords-everywhere](integrations/keywords-everywhere.md) |
| RankParse | ✓ | ✓ | ✓ | [rankparse](integrations/rankparse.md) |

**Agent recommendation**: Search Console first — it is free and authoritative for your own site. Start any SEO audit by comparing indexed pages to real pages; a large excess means faceted-nav bloat and no content work will overcome it. See `ecommerce-seo`.

### Content, creative, and social

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Buffer | ✓ | - | ✓ | [buffer](integrations/buffer.md) |
| Wistia | ✓ | - | ✓ | [wistia](integrations/wistia.md) |
| HeyGen | ✓ | ✓ | - | [heygen](integrations/heygen.md) |
| Hyperframes | ✓ | - | - | [hyperframes](integrations/hyperframes.md) |
| AirOps | ✓ | - | ✓ | [airops](integrations/airops.md) |

**Agent recommendation**: creative volume is the constraint on paid growth. Build a production system, not a content calendar. See `ad-creative` and `organic-social`.

### Research and competitive intelligence

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Similarweb | ✓ | - | ✓ | [similarweb](integrations/similarweb.md) |
| SparkToro | ✓ | - | - | [sparktoro](integrations/sparktoro.md) |
| Exa | ✓ | ✓ | ✓ | [exa](integrations/exa.md) |
| Firecrawl | ✓ | ✓ | - | [firecrawl](integrations/firecrawl.md) |
| Browserbase | ✓ | ✓ | - | [browserbase](integrations/browserbase.md) |

**Agent recommendation**: the Meta Ad Library is free, public, and the single highest-value competitive input — a creative running for months is someone else's test result. See `category-intel`.

### CMS and content infrastructure

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| WordPress | ✓ | - | - | [wordpress](integrations/wordpress.md) |
| Webflow | ✓ | - | - | [webflow](integrations/webflow.md) |
| Sanity | ✓ | - | - | [sanity](integrations/sanity.md) |
| Contentful | ✓ | - | - | [contentful](integrations/contentful.md) |
| Strapi | ✓ | - | - | [strapi](integrations/strapi.md) |

### Utilities and integration layers

| Tool | API | MCP | CLI | Guide |
|------|-----|-----|-----|-------|
| Composio | ✓ | ✓ | - | [composio](integrations/composio.md) |
| Cogny | ✓ | ✓ | - | [cogny](integrations/cogny.md) |
| Zapier | ✓ | ✓ | ✓ | [zapier](integrations/zapier.md) |
| TrueList | ✓ | ✓ | ✓ | [truelist](integrations/truelist.md) |

**Agent recommendation**: Composio adds MCP access to OAuth-heavy tools without native MCP servers. See [composio/marketing-tools.md](composio/marketing-tools.md) for the toolkit mapping.

---

## MCP-Enabled Tools

Tools with a Model Context Protocol server, usable directly by an agent without writing HTTP calls:

ga4 · google-ads · mailchimp · resend · sequenzy · nitrosend · dub-co · supermetrics · coupler · rankparse · exa · firecrawl · browserbase · heygen · stripe · zapier · truelist · composio · cogny

---

## CLI Tools

Zero-dependency Node 18+ scripts in [`clis/`](clis/). Each takes `{TOOL}_API_KEY` from the environment, outputs JSON, supports `--dry-run`, and prints usage with no arguments.

```bash
node tools/clis/klaviyo.js                    # usage
node tools/clis/ga4.js report --dry-run       # preview the request
```

See [clis/README.md](clis/README.md) for the full environment-variable table.

---

## Quick Start by Job

**"Audit this store"** → platform API for orders and margin, GA4 for the funnel, Merchant Center and Meta Catalog for feed health, the ESP for flow coverage. Then `growth-audit`.

**"Why is Meta underperforming?"** → check Meta Catalog `diagnostics` and GA4-vs-platform order reconciliation *before* looking at the ad account. Most "algorithm" problems are signal problems. Then `paid-social`.

**"What do customers actually say?"** → bulk-export reviews from the review platform, pull tickets from Gorgias, and read competitor 1-star reviews. Then `customer-research`.

**"Are we profitable?"** → platform revenue, all ad platform spend, COGS and shipping from the platform or a spreadsheet. Sum the platform-claimed revenue and compare to actual. Then `profitability-and-incrementality`.

**"Grow on Amazon"** → SP-API Reports for search terms and fee preview, Amazon Ads for spend, join for TACoS. Then `amazon-growth` and `marketplace-ads`.

**"Fix retention"** → platform order history for cohorts, subscription platform for churn split, loyalty platform for tier state. Then `retention-and-loyalty`.
