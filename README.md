<h1 align="center">n8n / Make / Zapier Ops Suite</h1>

<p align="center">
  <em>three backend automations — evidence over hype</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/automations-3-ffb454" alt="3 automations">
  <img src="https://img.shields.io/badge/stack-n8n%20%7C%20Make%20%7C%20Zapier-EA4B71" alt="n8n | Make | Zapier">
  <img src="https://img.shields.io/badge/data-demo%20%2F%20sanitized-5cd887" alt="demo / sanitized data">
  <img src="https://img.shields.io/badge/secrets-redacted-f7913a" alt="secrets redacted">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="MIT License">
</p>

> Portfolio of three working backend automation systems — each shipped with a sanitized export and a case-study page as evidence.

This repository collects three no-/low-code backend automations built on **n8n**, **Make**, and **Zapier**. Each folder documents one system: the problem it solves, its architecture, the tools, and honest limitations.

> **Demo-data notice:** every record, name, and email visible in the exports and case studies is **demo/sample data**, not real client data. All secrets — webhooks, tokens, Telegram chat IDs, Airtable base/table/user IDs, and credential/connection IDs — were replaced with `<...>` placeholders before commit.

---

## Systems

| Folder | System | Stack | Status |
|---|---|---|---|
| [`n8n/`](n8n/) | **AI Lead Intake CRM** | n8n · Airtable · Telegram · webhook | Local/self-hosted · demo data · sanitized export |
| [`make/`](make/) | **Daily Operations Report** | Make · Airtable · Telegram | Built · 09:00 schedule intentionally inactive · demo data |
| [`zapier/`](zapier/) | **Client Onboarding & Follow-up** | Zapier · Airtable · Gmail · Calendar · Telegram | Built, then disabled after proof · no machine export |

---

## Repository layout

| Path | Purpose |
|---|---|
| `n8n/` | Sanitized workflow JSON (main + error handler) + case study |
| `make/` | Sanitized scenario blueprint JSON + case study |
| `zapier/` | Case study + architecture (Zapier has no public export) |
| `CLAUDE.md` | Repository rules and the verified facts these docs are based on |

---

## Conventions

- Secrets are never committed; every export is sanitized first.
- Each README states the problem solved, the architecture, the tools, and honest limitations.
- This repository is self-contained.

---


## License

MIT — see [LICENSE](./LICENSE).

