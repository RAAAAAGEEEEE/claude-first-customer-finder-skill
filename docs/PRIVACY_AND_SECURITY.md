# Privacy and security

Related: [Limitations](LIMITATIONS.md), [Architecture](ARCHITECTURE.md).

## What leaves your machine

- Claude Code's own web searches and page fetches. Words from your product description (name, audience, pain keywords) can appear in search queries.
- Whatever you write in the conversation goes to Claude as usual.
- `scripts/generate_report.py` makes no network call; the report is a local file.

## What is never sent

Per [SKILL.md](../first-customer-finder/SKILL.md) (step 5), the skill drafts outreach only. It does not send messages, submit forms, connect, follow, comment or create CRM records unless you separately request and authorize that action.

## Research rules the skill follows

From `SKILL.md` step 3: public, intentionally shared professional or business information only; no bypass of login walls, paywalls, access controls, rate limits or robots restrictions; no data brokers, leaked datasets, private groups, personal email or phone discovery; no inference of sensitive traits. Quotes are minimal and every material signal is linked.

## Your responsibilities

- A report lists named people or companies with links. Treat it as personal data under your local rules and do not publish it.
- Check each platform's rules and your local law (cold outreach, data protection) before contacting anyone.
- The generator escapes text and restricts links to http and https, but open HTML reports only from sources you trust.

No secret, API key or account is needed.
