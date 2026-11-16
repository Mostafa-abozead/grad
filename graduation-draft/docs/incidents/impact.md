---
title: "Impact of the Problem — The Cost of Workplace Injuries"
status: "reference"
last_updated: "2026-11-15"
tags:
  - impact
  - cost-of-injuries
  - work-injuries
  - evidence
---

# Impact of the Problem — The Cost of Workplace Injuries

## Purpose

This document quantifies **what workplace injuries cost** — the impact of the problem we are solving. It pairs with the CAPMAS 2024 analysis ([`capmas-work-injuries-2024.md`](./capmas-work-injuries-2024.md)) in this folder (Egypt-specific) by adding the global/US cost picture from official statistics and insurer indices.

**The solution side of the ledger** — what AI video analytics demonstrably delivers against these costs — is researched separately in [`../market/impact.md`](../market/impact.md).

---

## 1. Total cost — National Safety Council (NSC), 2023

From [NSC Injury Facts](https://injuryfacts.nsc.org/work/costs/work-injury%20-costs/) (also cited in the [AvidBeam PPE-detection article](https://www.avidbeam.com/why-personal-protective-equipment-detection-is-the-future-of-workplace-safety)):

| Cost of work injuries, 2023 | Amount |
|---|---|
| **Total cost** | **$176.5 billion** |
| Wage & productivity losses | $53.1B |
| Medical expenses | $36.8B |
| Administrative expenses | $59.5B |
| Employers' uninsured costs | $15.7B |
| Motor-vehicle damage | $5.9B |
| Fire losses | $5.6B |

Per-unit costs (2023):

- **$43,000** per medically consulted injury
- **$1.46 million** per death
- **$1,080 per worker** — the value of goods or services each worker must produce to offset the cost of work injuries

## 2. Direct employer cost — Liberty Mutual Workplace Safety Index

The [2026 WSI](https://marketinghub.libertymutual.com/AssetLink/6rbm53w1y4o50h8q6i040j86xvqglu6g.pdf) (reflecting 2023 data): US employers spent **$58.74B** on direct costs of disabling injuries — **more than $1 billion per week**. The [top-10 causes](https://www.safetyandhealthmagazine.com/injuries-and-illnesses-cost-u-s-employers-58-7-billion-in-2023-insurers-index-shows) account for $49.9B (84.9%):

| # | Cause | Direct cost |
|---|---|---|
| 1 | Overexertion (lifting, carrying, pushing) | $13.07B |
| 2 | **Falls on same level** | $9.92B |
| 3 | **Struck by object/equipment** | $6.21B |
| 4 | Falls to lower level | $5.23B |
| 5 | Slip or trip without fall | $3.83B |

> **Why this matters for a camera-only system:** causes 2–5 (falls, struck-by, slips) plus roadway/pedestrian incidents are exactly the event types computer vision can detect as leading indicators — before they become injuries. Egypt's CAPMAS data shows the same concentration: falls (32.1%) + collisions with objects (27.6%) ≈ **60% of all cases** ([CAPMAS analysis](./capmas-work-injuries-2024.md)).

## 3. The hidden multiplier — indirect costs

- For every **$1 of direct injury cost, an estimated $3+ in indirect costs** accrues: coworker lost productivity, investigation time, equipment downtime, replacement hiring and training, reputational damage ([inviol ROI article](https://www.inviol.com/post/the-roi-of-computer-vision-ai-for-safety-what-the-numbers-say)).
- OSHA's *Safety Pays* estimator applies indirect multipliers of **1.1–4.5×** depending on claim size.
- The ILO estimates safety incidents cost **~4% of global GDP** ([viso.ai HSE paper](https://viso.ai/wp-content/uploads/2025/06/Viso_HSE-Suite-Paper_2025.pdf)).
- Return on safety investment: **$4–6 back per $1 invested** (ASSP); Harvard School of Public Health / Liberty Mutual found **$4.41 per $1**.

## 4. Local anchor — Egypt (CAPMAS 2024)

From the official bulletin, analyzed in [`capmas-work-injuries-2024.md`](./capmas-work-injuries-2024.md):

| Indicator | Value |
|---|---|
| Work injuries | **8,091** across 2,225,169 covered workers |
| Injury rate | **363.6 per 100,000 workers** |
| Manufacturing share of cases | **45.6%** (3,687) — our target sector |
| Fatal cases | 48 (0.6%) |
| Falls + collisions with objects | **≈60%** of all cases |
| Absence days | **207,688** (≈25.7 days per case) |

The absence-day figure is the direct productivity equivalent: every injury removes a worker from the floor for weeks — in a sector that alone accounts for nearly half of all cases.

## 5. What this means for the project

- The problem is **expensive and measurable**: $176.5B total / $58.7B direct (US, 2023), ~4% of global GDP (ILO), and locally 8,091 injuries + 207,688 absence days (CAPMAS 2024).
- The cost is **concentrated in camera-detectable events**: falls, struck-by, slips, vehicle–pedestrian — ~60% of cases both globally (WSI causes 2–5) and in Egypt.
- The intervention side — what AI video analytics delivers against these costs — is documented in [`../market/impact.md`](../market/impact.md).

## Caveats

- NSC and Liberty Mutual figures are **US-based**; they establish magnitude, not an Egyptian cost basis.
- The CAPMAS bulletin is a **formal-sector snapshot** (7,596 establishments) — it excludes informal-sector work, so it understates the true injury toll.
- These figures support **problem framing and prioritization**, not demand or willingness-to-pay claims.

## References

1. NSC Injury Facts — Work Injury Costs — <https://injuryfacts.nsc.org/work/costs/work-injury%20-costs/>
2. Liberty Mutual Workplace Safety Index 2026 — <https://marketinghub.libertymutual.com/AssetLink/6rbm53w1y4o50h8q6i040j86xvqglu6g.pdf>
3. Safety+Health magazine — *Injuries and illnesses cost U.S. employers $58.7 billion in 2023* — <https://www.safetyandhealthmagazine.com/injuries-and-illnesses-cost-u-s-employers-58-7-billion-in-2023-insurers-index-shows>
4. AvidBeam — *Why PPE Detection Is the Future of Workplace Safety* — <https://www.avidbeam.com/why-personal-protective-equipment-detection-is-the-future-of-workplace-safety>
5. inviol — *The ROI of computer vision AI for safety* — <https://www.inviol.com/post/the-roi-of-computer-vision-ai-for-safety-what-the-numbers-say>
6. viso.ai — *HSE Suite paper* (2025) — <https://viso.ai/wp-content/uploads/2025/06/Viso_HSE-Suite-Paper_2025.pdf>

## Related

- [CAPMAS 2024 analysis](./capmas-work-injuries-2024.md) — the Egyptian figures in detail
- [Impact of the solution (AI video analytics outcomes)](../market/impact.md)
- [Egypt market & adopters](../market/egypt_market.md)
- [What We Offer & How We Differ](../project_overview/what_we_offer.md)
