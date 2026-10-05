# Configuration

Related: [Usage](USAGE.md).

There is no `.env` file, no settings file and no environment variable. The behavior is chosen in your request.

## Modes

Default: `standard`. Definitions come from [SKILL.md](../first-customer-finder/SKILL.md).

| Mode | Behavior |
| --- | --- |
| quick | Up to 5 strong prospects |
| standard | Up to 10 prospects across several public source types |
| deep | Up to 20 prospects, maps repeated pain patterns |
| design-partners | Favors users willing to test and give feedback over immediate buyers |
| b2b | Favors companies, public business triggers and decision roles |
| community | Favors public discussion and explicit request signals |

## Report generator

```
python3 first-customer-finder/scripts/generate_report.py <analysis.json> <report.html>
```

Two positional arguments only: the input JSON and the output HTML path (parent folders are created). The JSON schema is in [report-artifact.md](../first-customer-finder/references/report-artifact.md).
