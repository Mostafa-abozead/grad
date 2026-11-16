# AI-Powered Industrial Safety & Surveillance System

> **No new hardware — an AI safety layer that turns the CCTV cameras a factory already owns into real-time, structured safety events; camera-only, pluggable, API-driven, and configurable per site without code.**

Graduation project (CSE493/AIE493) · [AIU-SoftWave](https://github.com/AIU-SoftWave) · Team: 1 AI engineer + 5 software engineers

---

## The problem in one paragraph

Small and mid-sized factories and warehouses in Egypt and MENA already own the cameras; what they lack is a way to act on what those cameras see. CCTV is reviewed after an incident, safety checks are manual and fragmented, and the evidence needed for audits, insurance, and regulators is incomplete. Commercial AI platforms (Protex, Voxel, Intenseye) prove the capability is real — but they are closed, enterprise-priced, and have no Egyptian delivery base. Hardware alternatives (thermal cameras, RFID/UWB tags) add per-worker cost this segment cannot absorb. Result: violations go unnoticed until an audit or an accident.

**The scale:** Egypt logged **8,091 work injuries in 2024** (363.6 per 100k workers) — **manufacturing alone accounts for 45.6%** of cases, and ~60% of all injuries are falls and collisions with objects, exactly the event types a camera can catch in real time. ([CAPMAS 2024 analysis](docs/incidents/capmas-work-injuries-2024.md))

## What we're building

A **config-driven platform** that converts existing RGB camera feeds into safety events — three layers, one shared backbone:

```
RTSP camera → YOLO (fine-tuned, shared) → ByteTrack → zone/rules engine (Shapely/PolygonZone)
  → dwell/debounce filter → event schema → event API → alerts + risk dashboard + agentic AI
```

| Layer | What it does |
|---|---|
| **Detection** | One shared fine-tuned YOLO-family detector + ByteTrack tracking over the existing CCTV/IP feeds |
| **Rules** | Config-driven zones & rules (polygon zones, PPE, speeds, dwell/debounce) — site policy as configuration, not code |
| **Output** | Structured events via API → instant alerts, risk-quantification dashboard, agentic-AI assistant, audit-ready evidence trail |

**Principles:** camera-only (no thermal, no RFID/UWB/BLE/GPS tags, no face recognition, no autonomous shutdown) · every service pluggable via the shared event schema · compute on existing infrastructure (deployment model TBD) · honest reporting of uncertainty and coverage gaps.

## The MVP — from a real factory, not a feature list

Gathered from requirements we sat down and collected at a factory during Research Round 3. The platform is the committed deliverable; each service is validated incrementally and prioritized by feasibility. Full scope: **[Scope, MVP & Future Scope](docs/project_overview/scope_mvp.md)**

| MVP service | Feasibility |
|---|---|
| Access control (unauthorized presence at entries/restricted zones) | medium — well-studied detection class |
| Housekeeping (blocked routes, spills, clutter) | medium — heuristic-first |
| Fire detection (early visual detection + alerting) | highest risk — validated first |
| Risk Quantification Dashboard (risk by zone/shift/crew) | most deterministic — integration backbone |

**Future:** worker location & zones (tracking mapped to explicit zones) · agentic AI assistant (explains events, drafts reports, answers questions about camera feeds) · fire & smoke extension · behavioral/unsafe acts · work-at-height safety · fall detection.

## Why us

- **No hardware** — software overlay on cameras the facility already owns; nothing per-worker to buy or charge.
- **Pluggable & API-driven** — independent services on one event schema; no rip-and-replace.
- **Configurable** — site rules set by the customer without code (the pattern Protex proves, aimed at a different market).
- **Evidence-first** — every event carries time, camera, zone, and clip: audit-ready by construction.
- **Right-sized** — built and priced for the SME segment global platforms don't serve.

Details: [What We Offer & How We Differ](docs/project_overview/what_we_offer.md) · [Egypt market & adopters](docs/market/egypt_market.md) · [Provider benchmark](docs/market/companies/README.md)

## Where everything lives

| Path | What's inside |
|---|---|
| [`docs/project_overview/`](docs/project_overview/README.md) | One-liner · offer & differentiators · executive summary · scope/MVP · problem context |
| [`docs/brd/`](docs/brd/README.md) | Business Requirements Document — objectives, requirements, risks, traceability & market-evidence appendices |
| [`docs/market/`](docs/market/README.md) | Provider benchmark (10 companies incl. Protex deep dive) · Egypt market landscape & adopters · 23-listing demand evidence |
| [`docs/incidents/`](docs/incidents/capmas-work-injuries-2024.md) | CAPMAS 2024 work-injury statistics + incident report sheet |
| [`docs/GP_Midterm/`](docs/GP_Midterm/) | Mid-semester evaluation + [slide-by-slide talking points](docs/GP_Midterm/midterm_talking_points.md) |
| `archticure/` · `Porposals/` · `archive/` | Architecture research · early proposals · frozen project snapshot (legacy) |

## Roadmap

| # | Milestone | Status |
|---|---|---|
| 1 | Research Round 1 — broad idea landscape scan | ✅ Done |
| 2 | Research Round 2 — filter to RGB-only catalog, 11 feasibility studies | ✅ Done |
| 3 | Research Round 3 — business & technical overview + factory tour → MVP requirements | 🔵 Current |
| 4 | Research Round 4 — per-service technical decisions (models, data, compute) | ⬜ Next |
| 5 | Implementation Round 1 — build services, pluggable via API | ⬜ |
| 6 | Implementation Round 2 — integration, unit tests, real-world validation | ⬜ |

Mid-semester evaluation (Nov 2026) documentation: [`docs/GP_Midterm/`](docs/GP_Midterm/).

---

*Internal meeting notes & history: [Notion](https://app.notion.com/p/the-Router-meeting-10-4-3ef63e100467800ca5ccd88b1e4652e7?source=copy_link) · legacy material in `archive/` and `Porposals/`.*
