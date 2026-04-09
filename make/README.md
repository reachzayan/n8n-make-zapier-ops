<h1 align="center">📊 Daily Operations Report</h1>

<p align="center">
  <em>a daily ops snapshot in one Telegram message</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Make-scenario-6D00CC?logo=make&logoColor=white" alt="Make scenario">
  <img src="https://img.shields.io/badge/Airtable-source-18BFFF?logo=airtable&logoColor=white" alt="Airtable">
  <img src="https://img.shields.io/badge/Telegram-report-26A5E4?logo=telegram&logoColor=white" alt="Telegram">
  <img src="https://img.shields.io/badge/schedule-09%3A00%20(inactive)-lightgrey" alt="09:00 schedule inactive">
  <img src="https://img.shields.io/badge/data-demo%20%2F%20sanitized-5cd887" alt="demo / sanitized">
</p>

> A Make scenario that reads the lead pipeline's Airtable data, counts the day's event types, and delivers a summary to Telegram.

The owner needs a quick daily snapshot — how many leads came in, how many were duplicates, how many were missing an email, and how many workflow errors occurred — without opening Airtable and counting by hand.

---

## Architecture

```
Schedule (09:00 daily — intentionally inactive)
   │
   ▼
Airtable ─ search Leads_clean ───────┐
Airtable ─ search Automation_Logs ───┤
   │                                  ▼
Aggregators ─ count event types:
     • new leads          • duplicate attempts
     • missing-email      • workflow errors
   │
   ▼
Telegram ─ send daily summary  (totals + system checks)
```

---

## Built with

`Make` · `Airtable` · `Telegram`

---

## Files

| File | Purpose |
|---|---|
| `daily-operations-report.blueprint.json` | Scenario blueprint — Airtable reads → aggregators → Telegram summary (sanitized) |
| `case-study.html` | Case-study page with screenshots and walkthrough |

---

## Status & limitations

- **Intentionally inactive** — a 09:00 daily schedule is configured, but the scenario is deliberately **not running**.
- **Sanitized blueprint** — Airtable base/table IDs, the Airtable user ID, the Telegram chat ID, and Make connection IDs are placeholders (`<...>`). Reconnect your own Airtable and Telegram connections to run it.
- **Demo data** — figures are computed from sample data, not real client activity.
- **Fixed template** — the Telegram summary uses a fixed message layout.

---

## License

Released under the [MIT License](../LICENSE).
