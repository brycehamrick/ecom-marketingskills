# Contributing

Thanks for your interest in contributing to Ecommerce Marketing Skills.

## Scope

This repo covers **ecommerce marketing** for four operators: DTC brands, marketplace sellers, wholesale/omnichannel brands, and the agencies that serve them.

A skill belongs here if an ecommerce operator would recognize the job. A skill that only makes sense for a software product — trial activation, seat expansion, sales-led pipeline — does not, however good it is. [The upstream repo](https://github.com/coreyhaines31/marketingskills) covers that ground.

## Requesting a Skill

[Open a skill request](https://github.com/brycehamrick/ecom-marketingskills/issues/new?template=skill-request.yml).

## Before You Write Anything

Read these two files. They are short and they are the difference between a skill that gets invoked and one that never triggers.

1. **[ROUTING.md](ROUTING.md)** — the skill boundary contract. The `description` field is the **only** routing signal an agent has, so collisions are decided by phrase overlap, not by your mental hierarchy. If your new skill overlaps an existing one, both descriptions need a reciprocal boundary sentence, and it must be recorded here.
2. **[SKILL-TEMPLATE.md](SKILL-TEMPLATE.md)** — skill anatomy and the three-part description formula.

## Adding a New Skill

### 1. Create the directory

```bash
mkdir -p skills/your-skill-name
```

### 2. Write SKILL.md

```yaml
---
name: your-skill-name
description: "When the user wants to <job>. Also use when the user mentions '<trigger>,' '<trigger>.' For <adjacent job>, see <other-skill>."
metadata:
  version: 1.0.0
---
```

The description has three parts, in order: the capability sentence, the verbatim trigger phrases people actually type, and the routing pointers. See SKILL-TEMPLATE.md for the full formula.

### 3. Naming rules

- **Directory name**: lowercase `a-z`, digits, hyphens. No leading or trailing hyphen, no `--`
- **`name` field**: must match the directory name exactly
- **`description`**: 1–1024 characters

### 4. Structure

```
skills/your-skill-name/
├── SKILL.md           # Required — under 500 lines
└── references/        # Optional — platform specs, templates, lookup tables
    └── guide.md
```

`SKILL.md` holds the **decision logic**. `references/` holds what an agent needs only after it has decided what to do. Split when content is a per-platform spec, a template over ~40 lines, a lookup table, or when SKILL.md passes ~400 lines.

### 5. Required sections

Every skill needs, in this order:

- H1 title and a 1–3 sentence persona line
- `## Initial Assessment`, opening with the `.agents/brand-context.md` boilerplate
- The domain framework, with H3s ordered **by impact**, not by category
- **`## Output Format`** — non-negotiable. Name a concrete deliverable and its sections. This is what makes a skill produce work product instead of a conversation
- `## Task-Specific Questions`
- `## Related Skills`

### 6. If the skill produces customer-facing copy

Add `For claims, disclosures, and channel policy, see claims-and-compliance.` to the description, and a `claims-and-compliance` entry under Related Skills.

### 7. No Claude-Code-only syntax

Skills must stay portable across agents. No `` !`command` `` injection in `SKILL.md` — other agents render it as literal garbled text. See AGENTS.md for where those patterns belong.

## Improving Existing Skills

1. Read the whole skill first
2. Keep changes focused
3. **Bump `metadata.version`** on any shipped change — the update check diffs `VERSIONS.md` against users' local skill metadata, so an unbumped change is invisible to installed users
4. Mirror the bump in the `VERSIONS.md` table and add a bullet under the current release
5. If you change a description in a way that affects routing, update `ROUTING.md` and the other side of the boundary

## Before Opening a PR

```bash
./validate-skills.sh                              # name/dir match, description length, line count
./validate-skills-official.sh                     # upstream agentskills reference validator
node .github/scripts/sync-skills.js && git diff    # README table + skill count
```

## Checklist

- [ ] `name` matches the directory name exactly
- [ ] `description` follows the three-part formula and carries real trigger phrases
- [ ] Routing boundaries are reciprocal and recorded in `ROUTING.md`
- [ ] `## Output Format` names a concrete deliverable
- [ ] `SKILL.md` is under 500 lines
- [ ] `metadata.version` set, and `VERSIONS.md` updated
- [ ] Cross-references point at skills that actually exist
- [ ] No Claude-Code-only syntax
- [ ] No sensitive data or credentials
- [ ] `validate-skills.sh` passes

## Submitting

1. Fork the repository
2. Branch: `feature/skill-name`, `fix/skill-name-description`, or `docs/description`
3. Test locally with an agent — the real test is whether it triggers on the prompts in the ROUTING.md fixture
4. Open a PR using the appropriate template

## Questions?

Open an issue.
