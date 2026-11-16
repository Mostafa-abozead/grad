---
title: "Users & Roles"
status: "reference"
last_updated: "2026-11-15"
tags:
  - users
  - personas
  - roles
---

# Users & Roles

## Purpose

Who uses the system, split by phase: **MVP users** (IT + Supervisor) and **future users** (Supervisor, QA, Manager). Detailed customer requirements per actor live in the CR documents (IT, Safety Supervisor, Factory General Manager).

> Naming note: the "Supervisor and examiners" in the [BRD stakeholders](../brd/05-stakeholders.md) are the **graduation-project supervisors** — different from the Safety Supervisor user below.

---

## 1. MVP users

- **Supervisor** — monitors workplace safety day to day. Receives real-time alerts with evidence, works from one dashboard (live/recorded feeds, detection overlays, alert list), filters and searches alerts, reviews risk summaries by zone and period, exports reports, and follows up on violations. Requests configuration changes (zones, schedules, PPE, thresholds) through administrator approval.

- **IT (maintenance)** — keeps the platform running. Deploys it on existing infrastructure with no added hardware, connects and troubleshoots cameras, watches system health (streams, services, storage), handles backups, updates and user accounts. Maintains the platform but does not decide what the system monitors — that belongs to the business users.

## 2. Future users

Three distinct users, three separate roles:

- **Supervisor** — continues as the daily operator of dashboard and alerts, with fuller configuration rights once approval workflows exist.

- **QA (Safety Operator)** — a separate user; owns the safety logic: defines zones, rule types, thresholds and required PPE, and tunes rule effectiveness over time.

- **Factory General Manager** — a separate user; facility-wide oversight: views the risk overview and trends, receives escalated critical events, approves high-consequence actions, reviews audit & regulatory reports, and oversees privacy and security.

## 3. How users flow through the system (MVP)

```
Cameras → CV pipeline → Rules engine → Event API ─┬─ Alerts + dashboard (feeds, overlays, search) → Supervisor
                                                  ├─ Reports / risk summaries → Supervisor
                                                  └─ Health & platform maintenance ←→ IT (cameras, services, storage, accounts)
```

## Related

- [BRD 5. Stakeholders](../brd/05-stakeholders.md) — stakeholder pains and formal roles
- [Scope, MVP & Future Scope](./scope_mvp.md) — the features mapped above
- [What We Offer & How We Differ](./what_we_offer.md) — the layers users interact with
