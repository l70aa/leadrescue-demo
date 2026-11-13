# LeadRescue — Lead Follow-up & CRM Automation Demo

A lightweight **Arabic (RTL) interactive prototype** showing how service companies and marketing agencies can track incoming leads, identify duplicates, prioritize follow-ups and spot stalled opportunities.

> **Portfolio demo, not a production CRM.** Uses fictional example data and browser `localStorage`. No third-party APIs are called, no customer messages are automatically sent, and no live n8n or PostgreSQL connection is configured.

**Demo:** open `index.html` in a browser. Screenshots are available in the downloadable project bundle.

## Quick start

Open **`index.html`** in a modern browser. No dependencies, authentication, build step, API keys or paid service required.

### Demo features

- Lead intake, local CRUD-like updates and duplicate detection by contact identifiers.
- Deterministic lead scoring and priority flags (not an AI inference).
- Follow-up deadlines, overdue indicators and activity history.
- Pipeline stage tracking, filters and sample-data KPI cards.
- Optional **manual** WhatsApp compose links when permission to contact is recorded.
- CSV import/export for demo records; sample file included.
- Configurable follow-up rules and local persistence.

### Preview on mobile

**Mobile preview:** the same `index.html` adapts to smaller screens. Preview screenshots are included in the [downloadable source package](https://github.com/l70aa/leadrescue-demo) from the project author.

## Architecture — demo versus production

| Area | In this repository | Production implementation needed |
|---|---|---|
| Frontend | Standalone HTML/CSS/JavaScript; Arabic RTL | Hosted app, auth and secure backend |
| Leads | Fictional records / localStorage | PostgreSQL + data-access controls |
| Automation | `n8n_webhook_starter.json` **template** | Signed webhooks, queue/retries, live workflow |
| Notifications | Draft-only message composition | Consent-aware notifications and logging |
| Reporting | Local, simulated pipeline statistics | Source-backed reporting with monitoring |

**Important:** The n8n starter accepts a POST payload, checks required fields and returns a priority assessment. It has **not** been deployed or tested against a live n8n instance. It does not itself store/deduplicate leads or schedule messages.

## Included files

- `index.html` — the complete interactive demo.
- `n8n_webhook_starter.json` — optional n8n intake-validation-scoring workflow template.
- `sample_leads.csv` — fictional sample leads for import.
- Screenshots are available in the separate project ZIP archive shared with the author.

## Live demo with GitHub Pages

If you publish this to a **public** GitHub repository, open **Settings → Pages**, select **Deploy from a branch**, choose **main / (root)**, then **Save**. GitHub will show the hosted URL after deployment. The hosted app still runs with local browser storage; **do not use real customer personal data**.

## Who this demonstrates value for

Marketing agencies, real estate teams and service businesses with incoming inquiries that require consistent tracking and timely human follow-up.

The proposed paid pilot is an integration with **one real lead source** and a clear operational measure (e.g. follow-up timeliness); this portfolio demo alone should not be sold as a deployed production solution.

## About

**Anwar Hussein** — SQL, Power BI, Python, data quality and automation.

[LinkedIn](https://www.linkedin.com/in/anwar-hussein-2b9b4b228)