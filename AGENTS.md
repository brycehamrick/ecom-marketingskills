# AGENTS.md

Guidelines for AI agents working in this repository.

## Repository Overview

This repository contains **Agent Skills** for AI agents following the [Agent Skills specification](https://agentskills.io/specification.md). Skills install to `.agents/skills/` (the cross-agent standard). This repo also serves as a **Claude Code plugin marketplace** via `.claude-plugin/marketplace.json`.

- **Name**: Ecommerce Marketing Skills
- **GitHub**: [brycehamrick/ecom-marketingskills](https://github.com/brycehamrick/ecom-marketingskills)
- **Maintainer**: Bryce Hamrick
- **License**: MIT
- **Upstream**: forked from [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) (B2B SaaS). The skill set was rewritten from scratch for ecommerce; the scaffolding is upstream's.

**Scope**: 40 skills serving four operators — DTC brands, marketplace sellers, wholesale/omnichannel brands, and agencies. If a proposed skill only makes sense for a software product, it does not belong here.

## Repository Structure

```
ecom-marketingskills/
├── .claude-plugin/
│   ├── marketplace.json   # Claude Code plugin marketplace manifest
│   └── plugin.json        # Plugin manifest (version synced from marketplace.json)
├── skills/                # 40 Agent Skills
│   └── skill-name/
│       ├── SKILL.md       # Required skill file (<500 lines)
│       └── references/    # Optional depth: platform specs, templates, lookup tables
├── tools/
│   ├── clis/              # Zero-dependency Node.js CLI tools
│   ├── composio/          # Composio integration layer (quick start + toolkit mapping)
│   ├── integrations/      # API integration guides per tool
│   └── REGISTRY.md        # Tool index, organized by job
├── ROUTING.md             # Skill boundary contract — read before writing a description
├── SKILL-TEMPLATE.md      # Skill anatomy and the description formula
├── VERSIONS.md            # Per-skill versions + changelog
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Build / Lint / Test Commands

**Skills** are content-only (no build step). Verify manually:
- YAML frontmatter is valid
- `name` field matches directory name exactly
- `name` is 1-64 chars, lowercase alphanumeric and hyphens only
- `description` is 1-1024 characters

**Skill routing** — the `description` field is the only signal an agent uses to pick a skill:
```bash
node .github/scripts/check-routing.js --verbose
```
Scores every description against the fixtures in `ROUTING.md`. A miss means a description omits vocabulary operators actually type. It is a bag-of-words proxy — a real agent matches semantically, so do not tune descriptions to reach 100%.

**CLI tools** (`tools/clis/*.js`) are zero-dependency Node.js scripts (Node 18+). Verify with:
```bash
node --check tools/clis/<name>.js   # Syntax check
node tools/clis/<name>.js           # Show usage (no args = help)
node tools/clis/<name>.js <cmd> --dry-run  # Preview request without sending
```

## Versioning

Two version layers, with different rules:

**Repo release version** — `.claude-plugin/plugin.json` `version`, `.claude-plugin/marketplace.json` `metadata.version`, and the `VERSIONS.md` changelog headings all share one x.y.z number:

- **x** — repo-wide changes (restructures, spec changes, breaking changes)
- **y** — new skill(s) added
- **z** — updates to existing skills

Do not bump y for content added to an existing skill, no matter how substantial — that's a z release (e.g. a new reference file in ad-creative is 2.8.0 → 2.8.1, not 2.9.0).

**Per-skill version** — `metadata.version` in each SKILL.md, mirrored in the `VERSIONS.md` table. Bump on ANY shipped change to that skill: the update check compares `VERSIONS.md` against users' local skill metadata, so an unbumped change is invisible to installed users. Minor for new capability or description triggers, patch for fixes and clarifications.

Bump the repo release version in the same PR that ships the change (2.7.0 and 2.8.0 shipped without touching plugin.json/marketplace.json and needed a catch-up later).

## Agent Skills Specification

**Before writing or editing a skill, read two files:**

1. **[ROUTING.md](ROUTING.md)** — the skill boundary contract. The `description` field is the *only* routing signal an agent has, so collisions are decided by phrase overlap. Every known collision has a prescribed reciprocal boundary sentence that must appear in both skills' descriptions.
2. **[SKILL-TEMPLATE.md](SKILL-TEMPLATE.md)** — skill anatomy and the three-part description formula.

Every skill must have an `## Output Format` section naming a concrete deliverable. This is what makes a skill produce work product rather than a conversation, and it is what serves the agency use case.


Skills follow the [Agent Skills spec](https://agentskills.io/specification.md).

### Required Frontmatter

```yaml
---
name: skill-name
description: What this skill does and when to use it. Include trigger phrases.
---
```

### Frontmatter Field Constraints

| Field         | Required | Constraints                                                      |
|---------------|----------|------------------------------------------------------------------|
| `name`        | Yes      | 1-64 chars, lowercase `a-z`, numbers, hyphens. Must match dir.   |
| `description` | Yes      | 1-1024 chars. Describe what it does and when to use it.          |
| `license`     | No       | License name (default: MIT)                                      |
| `metadata`    | No       | Key-value pairs (author, version, etc.)                          |

### Name Field Rules

- Lowercase letters, numbers, and hyphens only
- Cannot start or end with hyphen
- No consecutive hyphens (`--`)
- Must match parent directory name exactly

**Valid**: `site-cro`, `product-pages`, `bundles-and-aov`
**Invalid**: `Product-Pages`, `-pages`, `product--pages`

### Optional Skill Directories

```
skills/skill-name/
├── SKILL.md        # Required - main instructions (<500 lines)
├── references/     # Optional - detailed docs loaded on demand
├── scripts/        # Optional - executable code
└── assets/         # Optional - templates, data files
```

## Writing Style Guidelines

### Structure

- Keep `SKILL.md` under 500 lines (move details to `references/`)
- Use H2 (`##`) for main sections, H3 (`###`) for subsections
- Use bullet points and numbered lists liberally
- Short paragraphs (2-4 sentences max)

### Tone

- Direct and instructional
- Second person ("You are a conversion rate optimization expert")
- Professional but approachable

### Formatting

- Bold (`**text**`) for key terms
- Code blocks for examples and templates
- Tables for reference data
- No excessive emojis

### Clarity Principles

- Clarity over cleverness
- Specific over vague
- Active voice over passive
- One idea per section

### Description Field Best Practices

The `description` is critical for skill discovery. Include:
1. What the skill does
2. When to use it (trigger phrases)
3. Related skills for scope boundaries

```yaml
description: When the user wants to improve a product detail page. Also use when the user mentions 'PDP,' 'product page,' 'product description,' 'my product page isn\'t converting.' For homepage, navigation, and sitewide friction, see site-cro. For claims, disclosures, and channel policy, see claims-and-compliance.
```

## Claude Code Plugin

This repo also serves as a plugin marketplace. The manifest at `.claude-plugin/marketplace.json` lists all skills for installation via:

```bash
/plugin marketplace add brycehamrick/ecom-marketingskills
/plugin install ecommerce-marketing-skills
```

See [Claude Code plugins documentation](https://code.claude.com/docs/en/plugins.md) for details.

## Git Workflow

### Branch Naming

- New skills: `feature/skill-name`
- Improvements: `fix/skill-name-description`
- Documentation: `docs/description`

### Commit Messages

Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

- `feat: add skill-name skill`
- `fix: improve clarity in cro`
- `docs: update README`

### Pull Request Checklist

- [ ] `name` matches directory name exactly
- [ ] `name` follows naming rules (lowercase, hyphens, no `--`)
- [ ] `description` is 1-1024 chars with trigger phrases
- [ ] `SKILL.md` is under 500 lines
- [ ] No sensitive data or credentials

## Tool Integrations

This repository includes a tools registry for agent-compatible marketing tools.

- **Tool discovery**: Read `tools/REGISTRY.md` to see available tools and their capabilities
- **Integration details**: See `tools/integrations/{tool}.md` for API endpoints, auth, and common operations
- **MCP-enabled tools**: ga4, stripe, mailchimp, google-ads, resend, zapier, zoominfo, clay, supermetrics, coupler, outreach, crossbeam, introw, composio
- **Composio** (integration layer): Adds MCP access to OAuth-heavy tools without native MCP servers (HubSpot, Salesforce, Meta Ads, LinkedIn Ads, Google Sheets, Slack, etc.). See `tools/integrations/composio.md`

### Registry Structure

```
tools/
├── REGISTRY.md              # Index of all tools with capabilities
└── integrations/            # Detailed integration guides
    ├── klaviyo.md
    ├── shopify.md
    ├── amazon-sp-api.md
    └── ...
```

### When to Use Tools

Skills reference relevant tools for implementation. For example:
- `catalog-and-feeds` → google-merchant-center, meta-catalog guides
- `lifecycle-flows` → klaviyo, postscript, attentive, omnisend guides
- `amazon-growth` → amazon-sp-api, amazon-ads guides
- `reviews-and-reputation` → okendo, yotpo, judgeme, loox guides
- `subscriptions-and-replenishment` → recharge, skio, stay-ai guides
- `post-purchase-experience` → loop-returns, aftership, gorgias guides
- `profitability-and-incrementality` → triple-whale, northbeam, polar-analytics guides
- `wholesale-and-retail` → faire guide

`tools/REGISTRY.md` is organized **by job**, not alphabetically — find the job, pick the tool, read the guide.

For tools without native MCP servers, Composio provides MCP access via a single server. See `tools/integrations/composio.md` for setup and `tools/composio/marketing-tools.md` for the full toolkit mapping.

## Checking for Updates

When using any skill from this repository:

1. **Once per session**, on first skill use, check for updates:
   - Fetch `VERSIONS.md` from GitHub: https://raw.githubusercontent.com/brycehamrick/ecom-marketingskills/main/VERSIONS.md
   - Compare versions against local skill files

2. **Only prompt if meaningful**:
   - 2 or more skills have updates, OR
   - Any skill has a major version bump (e.g., 1.x to 2.x)

3. **Non-blocking notification** at end of response:
   ```
   ---
   Skills update available: X marketing skills have updates.
   Say "update skills" to update automatically, or run `git pull` in your ecom-marketingskills folder.
   ```

4. **If user says "update skills"**:
   - Run `git pull` in the ecom-marketingskills directory
   - Confirm what was updated

## Skill Categories

See `README.md` for the current list of skills organized by category. When adding new skills, follow the naming patterns of existing skills in that category.

## Claude Code-Specific Enhancements

These patterns are **Claude Code only** and must not be added to `SKILL.md` files directly, as skills are designed to be cross-agent compatible (Codex, Cursor, Windsurf, etc.). Apply them locally in your own project's `.claude/skills/` overrides instead.

### Dynamic content injection with `!`command``

Claude Code supports embedding shell commands in SKILL.md using `` !`command` `` syntax. When the skill is invoked, Claude Code runs the command and injects the output inline — the model sees the result, not the instruction.

**Most useful application: auto-inject the brand context file**

Instead of every skill telling the agent "go check if `.agents/brand-context.md` exists and read it," you can inject it automatically:

```markdown
Brand context: !`cat .agents/brand-context.md 2>/dev/null || echo "No brand context file found — run the brand-context skill before proceeding."`
```

Place this at the top of a skill's body (after frontmatter) to make context available immediately without any file-reading step.

**Other useful injections:**

```markdown
# Inject today's date for recency-sensitive skills
Today's date: !`date +%Y-%m-%d`

# Inject current git branch (useful for workflow skills)
Current branch: !`git branch --show-current 2>/dev/null`

# Inject recent commits for context
Recent commits: !`git log --oneline -5 2>/dev/null`
```

**Why this is Claude Code-only**: Other agents that load skills will see the literal `` !`command` `` string rather than executing it, which would appear as garbled instructions. Keep cross-agent skill files free of this syntax.
