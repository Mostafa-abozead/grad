# Scope, MVP & Future Scope

## Scope

**In scope:**

- The MVP services below, plus a shared detection/rules pipeline, an event API, an operator interface, and the assistant.

**Out of scope:**

- Thermal imaging
- RFID / UWB / BLE / GPS tags
- Face recognition
- Autonomous access denial or machinery shutdown
- Multi-site deployment
- ERP/WMS integration

## MVP

The MVP set comes from the requirements we sat down and gathered from a factory — the safety problems their supervisors actually flagged — rather than from a generic feature list:

| MVP service | What it does |
|---|---|
| **Access control** | Detects and logs unauthorized presence at monitored entry points and restricted zones from existing cameras. |
| **Housekeeping** | Flags blocked walkways/egress routes, spills, and clutter that create slip, trip, and obstruction hazards. |
| **Fire detection** | Early visual detection of fire on camera feeds with immediate alerting — before heat sensors would trigger, if they exist at all. |
| **Risk Quantification Dashboard** | Aggregates events into per-zone, per-shift, per-crew risk views so managers can see where risk is concentrated and whether it is improving. |

These services run on the shared platform pieces (detection/rules pipeline, event API, operator interface), so each is delivered as a configured rules set over the same event schema — not separate products.

### Feasibility note

The platform (detection/rules pipeline, event API, operator interface) is the committed deliverable. Each MVP service is validated incrementally against real site conditions; services are prioritized by feasibility, and any that underperforms will be descoped with documented rationale and revisited in the future-scope phase. Risk varies by service: the risk dashboard is the most deterministic (rules, aggregation); access control and housekeeping are well-studied detection classes; visual fire detection carries the highest false-positive risk and is validated first in conditions closest to the target sites.

## Future scope

| Future capability | What it adds |
|---|---|
| **Worker location & zones** | Tracks workers on camera and maps them to explicit zones (following workers as they move) — the foundation for zone-based rules and proximity events. |
| **Agentic AI assistant** | Explains events, answers safety questions, and drafts reports from structured data and a regulatory corpus — and can also **see camera feeds** and answer queries about them ("what happened at dock 3 last night?"). |
| **Fire & smoke detection** | Extends fire detection with smoke-plume recognition for earlier warning in more conditions. |
| **Behavioral / unsafe acts** | Detects unsafe behavior (running, climbing, unsafe positioning, phone use in hazard zones) beyond object- and zone-based rules. |
| **Work at height safety** | Monitors work-at-height zones (scaffolding, ladders, roofing) for missing fall protection and unauthorized presence under active work. |
| **Fall detection** | Detects worker falls and down-person events on camera with immediate alerting, closing the gap between an accident and the response. |

See [`what_we_offer.md`](what_we_offer.md) for positioning and [`../market/README.md`](../market/README.md) for the provider benchmarks these scopes were drawn against.
