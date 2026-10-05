# Architecture

Related: [Usage](USAGE.md), [Configuration](CONFIGURATION.md).

```
first-customer-finder/
  SKILL.md                          workflow, modes, quality bar
  references/research-framework.md  query buckets, 0-5 scoring, outreach rules, evidence ledger
  references/report-artifact.md     report JSON schema and generator command
  scripts/generate_report.py        JSON -> standalone HTML
```

Flow: Claude reads `SKILL.md` when the request matches its description, reads the two reference files before researching and before reporting, does the web research itself, writes a JSON file that follows the schema, then runs `generate_report.py` to produce the HTML.

The generator uses only the Python standard library. It escapes all text, accepts only `http` and `https` source URLs (anything else becomes `#`), clamps scores to their range and embeds its CSS in the page. Reading the script, it makes no network call of its own.

Everything except three wording changes is unchanged from the original skill; see [LEGAL_AND_ATTRIBUTION.md](LEGAL_AND_ATTRIBUTION.md).
