# Usage

Related: [Configuration](CONFIGURATION.md), [Limitations](LIMITATIONS.md).

## Invoke

In plain language, or by name:

```
Use the skill first-customer-finder in standard mode to find first customers for https://example.com
```

```
/first-customer-finder
```

Give a product URL, a repository, landing-page copy or a plain description. If something material is ambiguous, the skill asks one concise question ([SKILL.md](../first-customer-finder/SKILL.md), step 1).

## Workflow

The skill follows the steps in `SKILL.md`: understand the product, plan the public-signal search, research safely, score and deduplicate, draft outreach (never send it), produce the report. `SKILL.md` is the single source of truth for the workflow; the scoring formula is in [research-framework.md](../first-customer-finder/references/research-framework.md).

## Modes

Listed in [CONFIGURATION.md](CONFIGURATION.md).

## Output

Unless you ask for chat-only output, the skill writes a JSON analysis, runs the generator and saves a standalone HTML report in the `outputs/` directory of the workspace, then returns a clickable absolute file link. Report sections: verdict, ICP (ideal customer profile), top prospect, shortlist, repeated patterns, seven-day outreach plan, limits. The image at the top of the [README](../README.md) is an anonymized example.

## Verify the report generator

This is the only check available; there is no test suite. From the repository root, extract the sample JSON from the schema and generate a report:

```bash
sed -n '/^```json/,/^```$/p' first-customer-finder/references/report-artifact.md | sed '1d;$d' > sample.json
python3 first-customer-finder/scripts/generate_report.py sample.json out/report.html
```

Expected: a `Created report: ...` line and an HTML file that contains the sample prospect "Example Gym". Run on 2026-10-05 with Python 3.11: the sample prospect appeared in the output, and a source URL that is not http or https was rendered as `#`. Delete `sample.json` and `out/` afterwards.
