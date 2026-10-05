# Troubleshooting

Related: [Installation](INSTALLATION.md), [Usage](USAGE.md).

| Symptom | Likely cause and fix |
| --- | --- |
| The skill is not listed or does not trigger | `SKILL.md` is not directly inside `.../skills/first-customer-finder/`. Copy the `first-customer-finder` folder, not the whole repository, then restart Claude Code. |
| `python3: command not found` | Use `python` instead, or install Python 3. |
| `FileNotFoundError` on the JSON file | Check the path of the analysis JSON passed to the generator. |
| Report contains `#` links | The source URL in the JSON is not `http` or `https`; fix the URL in the JSON. |
| Few or weak prospects | The skill excludes prospects without a cited signal on purpose. Try `deep` mode or give a more specific product description. |
| No link to the report | Ask Claude for the absolute path of the file in `outputs/`. |
