# GP1 Midterm — Slide-by-Slide Talking Points

*Companion to [`GP1_Presentation_Template_Midterm.md`](GP1_Presentation_Template_Midterm.md). What to say on each of the 16 slides, drawn from the project documents. 20-minute presentation — roughly 60–75 seconds per slide.*

---

## Slide 1 — Title

- Project title: **AI-Powered Industrial Safety & Surveillance System**.
- Team: 1 AI engineer + 5 software engineers — state each member and their responsibility (AI/models; rules engine; event API & backend; dashboard; assistant; integration/testing).
- Supervisor name; course CSE493/AIE493; date 19/11/2026.

## Slide 2 — Outline

Read the roadmap of the talk in one breath: *motivation → background → problem → available solutions & our solution → market needs → literature review → user analysis → requirements → datasets → design.* Tell the audience the presentation follows the lifecycle of the project: why, what exists, what we build, and how.

## Slide 3 — General instructions

*(This is an instruction slide — skip it in the talk; make sure your slides themselves obey it: under 50% text, visuals-first.)*

## Slide 4 — Introduction & Motivation

**Hook story:** *"A supervisor in a factory watches 40 cameras on six screens. He can't. Violations happen in front of a camera and are discovered in the incident report the next morning."*

- Purpose of the presentation: show the problem, the market gap, and our camera-only solution.
- The insight that motivates us: **small and mid-sized factories already own the cameras — what they lack is a way to act on what those cameras see** ([what_we_offer.md](../project_overview/what_we_offer.md)).
- Visual suggestion: a camera wall image → overlay "who is watching all of these?"

## Slide 5 — Background

Define the vocabulary you'll use all presentation:

- **CCTV/VMS** — the camera + video-management systems every facility already owns.
- **Computer vision / video analytics** — AI that converts frames into detections (people, vehicles, PPE, smoke).
- **Rules engine / zone enforcement** — config-driven logic (zones, speeds, PPE) that turns detections into *events*.
- **Event schema** — the shared contract every event carries (time, camera, zone, type, clip).
- **How the landscape works today** — two disconnected systems: *passive CCTV reviewed after incidents* and *manual safety checks on paper/spreadsheets* ([existing_solutions_problems.md](../project_overview/existing_solutions_problems.md)).
- Mention the new category this creates: "site intelligence" — what Protex, Voxel, and Intenseye call it.

## Slide 6 — Problem

**International scale:** workplace hazards claim ~2.4M lives annually (Intenseye's framing); every 8 seconds a worker is injured.

**Local numbers (CAPMAS 2024, Egypt — [capmas-work-injuries-2024.md](../incidents/capmas-work-injuries-2024.md)):**
- **8,091 work injuries** across 2.2M covered workers — rate **363.6 per 100,000**.
- **Manufacturing = 45.6%** of all cases (3,687) — our exact target sector.
- **Construction: 6.9% of cases but 45.8% of deaths** — severity concentrated where monitoring is weakest.
- **Falls (32.1%) + collisions (27.6%) = ~60%** of cases; **207,688 absence days**, ~26 days per case.

**Why we chose it / our aim:** violations go unnoticed until an audit or an accident; managers can't answer "where is risk concentrated and why?" Our aim: convert existing cameras into real-time, structured safety events and auditable risk information — no new hardware.

## Slide 7 — Available Solutions (feature matrix)

Present the benchmark from [`companies/README.md`](../market/companies/README.md) as a feature matrix:

| | Protex | viAct | Voxel | Intenseye | AvidBeam | **Us** |
|---|---|---|---|---|---|---|
| Works on existing CCTV | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| No hardware per worker | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Config-driven rules (customer-set) | ✅ | modules | partial | ❌ closed | ❌ | ✅ |
| PLC / automated response | ✅ | — | — | ✅ | — | roadmap |
| Agentic AI assistant | ✅ | partial | — | ✅ | partial | ✅ |
| Built & priced for SMEs / Egypt delivery | ❌ | ❌ | ❌ | ❌ | partial | ✅ |

**What they lack / why we chose our solution:** closed architectures and unpublished models; enterprise pricing; no Egyptian delivery base (only AvidBeam has a Cairo office). Show one line: *"capability is proven — access, affordability, and configurability are the gap."*

## Slide 8 — Proposed Solution

- Main focus: an **AI-powered industrial safety & surveillance system** that converts existing RGB camera feeds into **real-time, structured safety events and auditable risk information — with no additional hardware**.
- Three layers: **CV pipeline** (shared fine-tuned detector + tracking) → **config-driven rules engine** (zones, PPE, speeds → events) → **output layer** (event API → alerts, risk dashboard, agentic-AI assistant).
- Why this focus: it's the missing work identified in the research — "a detector that draws boxes is not a safety product; the missing work is the rules layer, the event contract, the dashboard, the evidence trail."
- Scope discipline: camera-only, no thermal, no tags, no face recognition, no autonomous shutdown — keeps it affordable and buildable ([scope_mvp.md](../project_overview/scope_mvp.md)).

## Slide 9 — Market Needs

- **Global:** the "site intelligence / EHS-AI" category is growing fast — Protex ($54M raised, Verdantix top ranking), Intenseye ($90M, 400+ facilities in 45+ countries), viAct (500+ projects in 20+ countries) — evidence that enterprises pay for exactly this capability ([companies/README.md](../market/companies/README.md)).
- **Local (Egypt):** every documented industrial-safety deployment was delivered by an Egypt-based provider — Coca-Cola, Nestlé (120+ cameras), Mars (AvidBeam); 3 cement factories (GSD); ElAraby factories (InfoTraff); a "Safe Industry" initiative targeting **5,000 factories** ([egypt_market.md](../market/egypt_market.md)).
- **Demand evidence:** 23 Upwork/Freelancer listings for CV surveillance/PPE/video analytics with budgets and skills mapped to our BRD ([job_listings/README.md](../market/job_listings/README.md)).
- The gap: SME factories are priced out of global platforms and underserved by local ones.

## Slide 10 — Literature Review

- How we gathered: two research rounds — (1) broad landscape scan, (2) filtering to an RGB-only service catalog; each service got a **feasibility study** with a fixed template: problem scope, provider survey, architecture, models & data, compute, edge cases, Egypt/MENA context, verdict.
- Inclusion criteria: camera-only feasibility on standard RGB, availability of datasets, compute realism for an academic team, Egypt/MENA relevance.
- Sources: provider documentation & case studies (Protex, viAct, Voxel, Intenseye, AvidBeam, Siemens), CAPMAS official statistics, marketplace listings, public dataset papers (e.g., SH17 PPE dataset, Construction-PPE).
- Outcome: methodology chosen — shared detector + ByteTrack + polygon-zone rules engine + event schema, rather than per-service silos. Reference the appendix matrices in the BRD.

## Slide 11 — User Analysis

From [existing_solutions_problems.md](../project_overview/existing_solutions_problems.md) — the problem seen from each user:

| User | Their pain | What they need from us |
|---|---|---|
| **Worker** | bears the physical risk; unsafe conditions unnoticed | hazards caught before they become injuries |
| **Safety officer** | detection & reporting burden; can't watch every zone | automatic detection + evidence, not more paperwork |
| **Manager** | no reliable picture of site risk | risk dashboard by zone/shift/crew |
| **Auditor / insurer / regulator** | incomplete, contestable evidence | structured, timestamped, clip-backed events |

## Slide 12 — Requirements

- Gathered from a **real factory visit** (Research Round 3) — what supervisors actually flagged, not a generic list.
- **Main functionalities (MVP):** access control, housekeeping, fire detection, risk-quantification dashboard — on the shared platform (detection/rules pipeline, event API, operator interface) ([scope_mvp.md](../project_overview/scope_mvp.md)).
- **Nice-to-have (future):** worker location & zones, agentic AI assistant (answers questions, drafts reports, reads camera feeds), fire & smoke extension, behavioral/unsafe acts, work-at-height, fall detection.
- Feasibility note: platform is committed; each service validated incrementally and prioritized by feasibility.

## Slide 13 — Available Datasets

Frame as pros/cons per detection class (details in the Round-2 feasibility studies):

- **PPE:** SH17 (17 classes, strong annotations) and Construction-PPE — ✅ large, real-world; ⚠️ construction-domain bias → fine-tune on factory frames.
- **Person/vehicle:** COCO / crowd-human / common tracking sets — ✅ mature; ⚠️ domain gap for factory floors.
- **Fire/smoke:** public fire-smoke sets — ✅ exist; ⚠️ high false-positive risk in dusty/foggy industrial air (our highest-risk detector).
- **Housekeeping:** no dominant public dataset → heuristic-first (blocked-exit/spill logic over detections).
- Choice rationale: start from the strongest public sets, fine-tune with frames from the target factory; validate per service before committing.

## Slide 14 — Design

Show the shared architecture (all services run on it):

```
RTSP camera → YOLO (fine-tuned, shared) → ByteTrack → zone/rules engine (Shapely/PolygonZone)
  → dwell/debounce filter → event schema → event API → alerts + risk dashboard + agentic AI
```

- Components: pluggable services over one event schema; operator interface; config-driven zones.
- SE diagrams: use-case (operator/safety officer/manager), component diagram of the 3 layers, event-flow sequence diagram.
- Refinement note: we started per-service pipelines, converged on **one shared detection+rules backbone** after the Round-2/3 research — that's the design story to tell.
- MVP wireframe: operator dashboard (live events feed, zone map, risk heatmap) + alert flow (WhatsApp/SMS/dashboard).

## Slide 15 — Time Plan

Map the remaining milestones to semester dates (Gantt):

- **Research Round 3 (current)** — business/technical overview ✅ + factory requirements ✅
- **Research Round 4** — per-service technical decisions (models, data, compute) → weeks X–Y
- **Implementation Round 1** — build services pluggable via API → weeks X–Y
- **Implementation Round 2** — integration, unit tests, real-world validation → weeks X–Y
- Deliverable markers: working MVP demo (access control + housekeeping + fire detection) on factory footage before final evaluation.

## Slide 16 — Thank You / Questions

Anticipate these questions:
- *"Why camera-only?"* — SMEs already own cameras; hardware-based alternatives add per-worker cost that kills adoption (and our CAPMAS/market analysis shows the segment).
- *"How is this different from AvidBeam/viAct?"* — configurable generic platform + SME pricing + event schema/API openness; they are closed or enterprise-priced.
- *"What about privacy?"* — no face recognition, no biometric tagging; events reference zones/clips, not identities.
- *"What if a detector underperforms?"* — platform is the committed deliverable; services validated incrementally and descoped with rationale (feasibility note).

---

*Every claim above traces to a doc: companies benchmark → `docs/market/companies/`, Egypt adopters → `docs/market/egypt_market.md`, CAPMAS numbers → `docs/incidents/capmas-work-injuries-2024.md`, problem framing → `docs/project_overview/`, requirements → `docs/brd/` + `docs/project_overview/scope_mvp.md`.*
