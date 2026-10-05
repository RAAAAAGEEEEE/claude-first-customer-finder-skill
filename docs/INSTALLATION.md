# Installation

Related: [Usage](USAGE.md), [Troubleshooting](TROUBLESHOOTING.md).

## Requirements

- Claude Code with web access.
- Python 3, standard library only (used by `first-customer-finder/scripts/generate_report.py`).
- Git.

## Personal install (all projects)

macOS, Linux, Git Bash:

```bash
git clone https://github.com/RAAAAAGEEEEE/claude-first-customer-finder-skill
mkdir -p ~/.claude/skills
cp -r claude-first-customer-finder-skill/first-customer-finder ~/.claude/skills/first-customer-finder
```

Windows PowerShell:

```powershell
git clone https://github.com/RAAAAAGEEEEE/claude-first-customer-finder-skill
New-Item -ItemType Directory -Force "$HOME\.claude\skills" | Out-Null
Copy-Item -Recurse claude-first-customer-finder-skill\first-customer-finder "$HOME\.claude\skills\first-customer-finder"
```

## Project install (one project)

Copy the same `first-customer-finder` folder to `.claude/skills/first-customer-finder` at the root of the project.

The folder you copy is `first-customer-finder`, not the whole repository: `SKILL.md` must end up directly inside `.../skills/first-customer-finder/`.

## Verify

1. Check the files are in place: listing `~/.claude/skills/first-customer-finder` shows `SKILL.md`, `references` and `scripts`.
2. Start (or restart) Claude Code and ask it to list its skills, or type `/first-customer-finder`.

## Update

Run `git pull` in the clone, then copy the folder again over the installed one.
