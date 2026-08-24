# CLAUDE.md — n8n-make-zapier-ops

## Purpose
Public portfolio repo of three backend automation systems. Audience: recruiters and clients. Tone: evidence over hype. This repo is self-contained; do not reference other projects or repositories.

## Contents
- n8n/   — AI Lead Intake CRM: n8n + Airtable + Telegram + webhook. Normalize → validate email → dedupe → Leads_clean / Automation_Logs → success/duplicate/missing-email paths → separate error-handler workflow.
- make/  — Daily Operations Report: reads Airtable Leads_clean + Automation_Logs, aggregates, counts event types, sends a Telegram summary. 09:00 schedule configured but intentionally inactive.
- zapier/ — Client Onboarding & Follow-up: webhook intake → email normalize/validate → Airtable CRM record → Gmail DRAFT (not auto-send) → Google Calendar follow-up (+2 days) → Telegram alert. Zap disabled after proof. No public export exists, so this folder is README + screenshots + architecture.

## Hard rules
1. NEVER commit secrets: webhooks, tokens, chat IDs, base IDs, credential IDs, .env. Sanitize all exports before committing.
2. NEVER invent or exaggerate. Use only verified facts; visible records are demo/sample data, not real client data — say so.
3. Keep README claims matched to the actual exports. State limitations honestly.
4. Stay inside this repo. Do not touch or mention any other repository.

## Git
- Single repo: n8n-make-zapier-ops. Concise imperative commit messages.
- .gitignore must ignore .env, credentials/token files, node_modules, OS files.
- Push PRIVATE first; owner reviews, then flips to public manually.

Last reviewed: 2026-08-24
