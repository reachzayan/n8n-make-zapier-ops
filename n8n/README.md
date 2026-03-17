<h1 align="center">📥 AI Lead Intake CRM</h1>

<p align="center">
  <em>clean leads in, noise out</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/n8n-self--hosted-EA4B71?logo=n8n&logoColor=white" alt="n8n self-hosted">
  <img src="https://img.shields.io/badge/Airtable-CRM-18BFFF?logo=airtable&logoColor=white" alt="Airtable">
  <img src="https://img.shields.io/badge/Telegram-alerts-26A5E4?logo=telegram&logoColor=white" alt="Telegram">
  <img src="https://img.shields.io/badge/trigger-webhook%20(POST)-ffb454" alt="webhook POST trigger">
  <img src="https://img.shields.io/badge/data-demo%20%2F%20sanitized-5cd887" alt="demo / sanitized">
</p>

> An inbound-lead pipeline in n8n: receive a lead over a webhook, normalize and validate it, drop duplicates, store it in Airtable, log every outcome, and alert via Telegram — plus a separate error-handler workflow.

Manual lead handling is slow and error-prone — duplicate entries, missing data, no audit trail. This workflow turns a raw webhook submission into a clean Airtable record and an event log, and notifies on every new lead.

---

## Architecture

```
Webhook (POST)
   │
   ▼
Set ─ normalize fields  (name · email · phone · business_type · city · message)
   │
   ▼
IF ─ email present/valid? ──no──►  Respond: missing-email
   │ yes
   ▼
Airtable ─ search Leads_clean  (dedupe)
   │
   ▼
IF ─ already exists? ──yes──►  Respond: duplicate
   │ no
   ▼
Airtable ─ create in Leads_clean ──►  Airtable ─ log Automation_Logs
   │
   ├──►  Telegram ─ notify new lead
   └──►  Respond: success

[separate workflow]   Error Trigger ──►  Airtable ─ log Automation_Logs
```

Airtable base **AI Lead CRM** · tables **Leads_clean** and **Automation_Logs**.

---

## Built with

`n8n` (self-hosted) · `Airtable` · `Telegram` · HTTP `webhook`

---

## Files

| File | Purpose |
|---|---|
| `ai-lead-intake-crm.workflow.json` | Main workflow — intake → validate → dedupe → store → log → notify (sanitized) |
| `ai-lead-intake-crm.error-handler.json` | Separate error-handler workflow — logs failures to `Automation_Logs` (sanitized) |
| `case-study.html` | Case-study page with screenshots and walkthrough |

---

## Status & limitations

- **Local / self-hosted** n8n build, not n8n Cloud.
- **Unauthenticated webhook** — the intake endpoint has no auth in this build.
- **Sanitized export** — webhook path/ID, Airtable base/table IDs, Telegram chat ID, and n8n credential/instance IDs are placeholders (`<...>`). The JSON is **illustrative**, not drop-in importable; reconnect your own credentials and IDs to run it.
- **Demo data** — all visible lead records are sample data, not real clients.

---

## License

Released under the [MIT License](../LICENSE).
