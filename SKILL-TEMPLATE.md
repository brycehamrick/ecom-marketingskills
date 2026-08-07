# Skill Authoring Template

Copy the block below into `skills/<name>/SKILL.md`. Read [ROUTING.md](ROUTING.md) first — the `description` is the only routing signal, and every collision has a prescribed boundary sentence.

**Hard constraints:**

- `name` must match the directory name exactly. Lowercase `a-z`, digits, hyphens. No leading/trailing hyphen, no `--`.
- `description` is 1–1024 characters.
- `SKILL.md` stays under 500 lines. Depth goes in `references/`.
- `metadata.version` starts at `1.0.0` and mirrors the row in `VERSIONS.md`.
- No `!`command`` syntax — skills must stay portable across agents.

---

## The description formula

Three parts, in this order:

1. **`When the user wants to <job>.`** — the capability sentence.
2. **`Also use when the user mentions '<phrase>,' '<phrase>,' …`** — verbatim trigger phrases, including the colloquial failure phrasings people actually type ("my product page isn't converting," "our ACOS is too high," "nobody's buying"). Front-load the nouns this skill must win.
3. **`For <adjacent job>, see <other-skill>.`** — routing pointers, copied from ROUTING.md. If this skill lost a collision, the negative pointer is mandatory.

If the skill produces customer-facing copy, append: `For claims, disclosures, and channel policy, see claims-and-compliance.`

---

## Template

```markdown
---
name: skill-name
description: "When the user wants to <job>. Also use when the user mentions '<trigger>,' '<trigger>,' '<trigger>.' For <adjacent job>, see <other-skill>."
metadata:
  version: 1.0.0
---

# Human-Readable Skill Title

You are a <role>. Your goal is to <outcome>.

## Initial Assessment

**Check for brand context first:**
If `.agents/brand-context.md` exists, read it before asking questions. Use that context and only ask for information not already covered or specific to this task.

Before proceeding, identify:

1. **<Dimension>**: <the options>
2. **<Dimension>**: <the options>
3. **<Dimension>**: <the options>

---

## <Domain> Framework

Work through these in order of impact.

### 1. <Highest-impact dimension>

**Check for:**
- <specific, checkable thing>

**Common issues:**
- <the mistake operators actually make>

### 2. <Next dimension>

...

---

## Output Format

<REQUIRED. Every skill ends in a named deliverable. State the artifact and its
sections so the output is consistent enough for an agency to hand to a client.>

### <Section>
<what goes here>

### <Section>
<what goes here>

---

## Task-Specific Questions

1. <question>
2. <question>
3. <question>

---

## Related Skills

- **<skill>**: <when to switch to it>
- **<skill>**: <when to switch to it>
```

---

## Section rules

| Section | Required | Notes |
|---|---|---|
| H1 title + persona line | Yes | 1–3 sentences, second person, "You are a…" |
| `## Initial Assessment` | Yes | Always opens with the brand-context boilerplate verbatim |
| Domain framework | Yes | H3s ordered by impact, not by category |
| `## Output Format` | **Yes** | Non-negotiable. This is what makes the skill produce a deliverable rather than a conversation |
| `## Task-Specific Questions` | Yes | 5–10, numbered |
| `## Related Skills` | Yes | Mirrors the routing tail in the frontmatter |
| `references/*.md` | As needed | Link inline: `See [references/x.md](references/x.md)` with a bolded lead-in |

Separate every H2 with a `---` horizontal rule.

---

## Reference file conventions

`SKILL.md` holds the **decision logic**. `references/` holds lookup tables, platform specs, templates, and long examples — the things an agent needs only after it has decided what to do.

Split to `references/` when:

- The content is a per-platform spec that varies (one file per platform).
- It is a template or example over ~40 lines.
- It is a lookup table the agent scans rather than reads.
- `SKILL.md` is approaching 400 lines.

---

## Before opening a PR

```bash
./validate-skills.sh              # name/dir match, description length, line count
./validate-skills-official.sh     # upstream agentskills reference validator
node .github/scripts/sync-skills.js && git diff   # README table + skill count
```

Then add the skill's row to `VERSIONS.md` and a bullet under the current release heading.
