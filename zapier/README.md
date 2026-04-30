<h1 align="center">🤝 Client Onboarding &amp; Follow-up</h1>

<p align="center">
  <em>onboard a client end to end — drafts, not sends</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Zapier-multi--step-FF4F00?logo=zapier&logoColor=white" alt="Zapier multi-step">
  <img src="https://img.shields.io/badge/Airtable-CRM-18BFFF?logo=airtable&logoColor=white" alt="Airtable">
  <img src="https://img.shields.io/badge/Gmail-draft%20only-EA4335?logo=gmail&logoColor=white" alt="Gmail draft only">
  <img src="https://img.shields.io/badge/Google%20Calendar-%2B2%20days-4285F4?logo=googlecalendar&logoColor=white" alt="Calendar +2 days">
  <img src="https://img.shields.io/badge/status-disabled%20after%20proof-lightgrey" alt="disabled after proof">
</p>

> A Zapier automation that onboards a new client end to end: capture, CRM record, a drafted welcome email (not sent), a calendar follow-up, and a team alert.

Onboarding a new client usually means several manual steps across email, calendar, and a CRM. This Zap chains them together while keeping a human in the loop for the actual email.

---

## Architecture

```
Webhook ─ new-client intake
   │
   ▼
Formatter ─ normalize & validate email
   │
   ▼
Airtable ─ create CRM record
   │
   ▼
Gmail ─ create DRAFT  (not auto-sent — kept for review)
   │
   ▼
Google Calendar ─ schedule follow-up  (+2 days)
   │
   ▼
Telegram ─ notify team
```

---

## Built with

`Zapier` · `Airtable` · `Gmail` · `Google Calendar` · `Telegram`

---

## Files

| File | Purpose |
|---|---|
| `case-study.html` | Case-study page with screenshots and the step-by-step architecture |

> Zapier has **no public export format**, so this system is documented via the case-study page and this README rather than an importable file.

---

## Status & limitations

- **Disabled after proof** — the Zap was built and verified, then **turned off**; it is not live.
- **Draft, not send** — the Gmail step only creates a draft; nothing is emailed automatically.
- **No machine-readable export** — the architecture is documented, not exported.
- **Demo data** — the records shown are sample data, not real clients.

---

## License

Released under the [MIT License](../LICENSE).
