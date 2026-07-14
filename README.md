# First Customer Finder — Claude Code port

This is a **port to Claude Code** of the original [`codex-first-customer-finder-skill`](https://github.com/Kappaemme-git/codex-first-customer-finder-skill), a Codex skill created by **[Kappaemme](https://github.com/Kappaemme-git)**.

All credit for the skill's design, workflow, research framework, and report generator goes to the original author. This repository only adapts the skill so it can be installed and invoked inside [Claude Code](https://claude.com/claude-code).

- Original repository: https://github.com/Kappaemme-git/codex-first-customer-finder-skill
- Original author: [Kappaemme](https://github.com/Kappaemme-git) (Francesco Mistero)
- License: MIT (see [LICENSE](LICENSE)), copyright retained by the original author

## What the skill does

Turns a startup URL or product description into a short, evidence-backed list of plausible first customers, sourced from public pain and buying signals (forums, reviews, public posts, company pages, etc.), and produces a standalone HTML report. It never sends outreach automatically — it only drafts it.

See [`first-customer-finder/SKILL.md`](first-customer-finder/SKILL.md) for the full workflow, modes, and quality bar.

## Changes made for this port

Only 3 changes were made relative to the original Codex skill — everything else (workflow, scoring framework, JSON schema, HTML report generator) is unchanged:

1. `first-customer-finder/SKILL.md` — frontmatter `description`: replaced "Codex" with "Claude Code" so the skill triggers correctly in Claude Code's skill index.
2. `first-customer-finder/SKILL.md` — step 6.5 of the workflow: "so it opens from Codex" → "so it opens from Claude Code".
3. `first-customer-finder/references/report-artifact.md` — "Return a clickable absolute file link in Codex" → "in Claude Code", fixing a reference left over from the original that the upstream port to Claude Code had missed.

No behavioral, structural, or scoring logic was changed. `scripts/generate_report.py` and `references/research-framework.md` are copied byte-for-byte from the original.

## Install for Claude Code

Copy the skill folder into your Claude Code skills directory:

```bash
cp -r first-customer-finder ~/.claude/skills/first-customer-finder
```

Claude Code will pick it up automatically on the next session. Verify it's available by asking Claude to list its skills, or by invoking it directly (see usage below).

## Usage

Ask Claude Code to run the skill against a product URL or description, optionally specifying a mode:

```
Use the skill first-customer-finder in standard mode to find first customers for https://example.com
```

Available modes: `quick` (up to 5 prospects), `standard` (default, up to 10), `deep` (up to 20), `design-partners`, `b2b`, `community`.

The skill will research public signals, qualify and score prospects, and generate a standalone HTML report under `outputs/` in your workspace, with a clickable link returned in the chat.

## License

MIT — see [LICENSE](LICENSE). Copyright belongs to the original author, Francesco Mistero ([Kappaemme](https://github.com/Kappaemme-git)). This port does not claim authorship of the underlying skill design.
