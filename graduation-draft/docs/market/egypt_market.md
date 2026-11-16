# The Egyptian Market for CV-Based Industrial Safety Providers

Egypt's industrial and construction boom — the ~$58B New Administrative Capital, the expanding Suez Canal Economic Zone, oil & gas development in the Western Desert and Gulf of Suez, and hundreds of FMCG, cement, steel, and textile factories — has created strong demand for AI-powered workplace safety. Domestic work-injury statistics (see [`docs/incidents/capmas-work-injuries-2024.md`](../incidents/capmas-work-injuries-2024.md), from the CAPMAS 2024 bulletin) underline the scale of the problem these providers target.

The common value proposition across all providers below: **plug into existing CCTV infrastructure** (no new cameras), run computer-vision AI to detect unsafe acts in real time — PPE compliance (helmets, vests, gloves), restricted-zone intrusion, vehicle–pedestrian proximity, fire/smoke, unsafe behavior — and push instant alerts (SMS/email/**WhatsApp**, sirens/lights, sometimes PLC-driven automation) plus dashboards, heatmaps, and compliance reports.

## Providers active in Egypt

| Provider | Origin | Founded | Core offering |
|---|---|---|---|
| [AvidBeam](companies/avidbeam-egypt.md) | Amsterdam HQ, Cairo office, Egyptian R&D | 2014 | Full video-analytics suite (security + safety + BI); strongest industrial footprint in Egypt |
| [GSD Technologies](companies/gsd-technologies.md) | Cairo | 2022 | HSE AI video analytics (Carrot Vision agent), fully on-premise |
| [Carrot Vision](companies/carrot-vision.md) | Egypt-focused | 2025 | "AI QHSE Engineer" with PLC auto-response; GSD is its exclusive Egyptian agent |
| [MAKKN](companies/makkn.md) | New Maadi, Cairo | ~2024 | MAKKN Guard — PPE, zones, forklift speed, face recognition on existing cameras |
| [InfoTraff](companies/infotraff.md) | Egypt | ~2020 | AI edge device per camera; retail, F&B, manufacturing safety + analytics |
| [Yellow Helmet Egypt](companies/yellow-helmet-egypt.md) | New Cairo | ~2019 | HSSEQ consulting & training house with an AI Monitoring ecosystem on top |
| Protex AI / viAct / Voxel / Intenseye (international) | Europe, HK, USA | 2018–2021 | No Egyptian delivery base; relevant as technology benchmarks (see [`companies.md`](companies/companies.md)) |

## Comparison — local providers

| Dimension | AvidBeam | GSD / Carrot Vision | MAKKN Guard | InfoTraff | Yellow Helmet |
|---|---|---|---|---|---|
| **Maturity** | High — 10+ yrs, WEF-recognized | Medium — new but field-proven | Early — Guard launched recently | Medium — national-scale CV track record | High in HSSEQ services, newer in AI |
| **Deployment** | On-premise / cloud / hybrid (Kubernetes) | Fully **on-premise** | On existing cameras | AI edge device on existing CCTV | Edge + existing CCTV, bundled service |
| **PPE detection** | ✅ (Coca-Cola, Nestlé) | ✅ (cement, construction) | ✅ | ✅ | ✅ |
| **Fire & smoke** | ✅ | ✅ | — | ✅ | ✅ |
| **Face recognition** | ✅ (flagship) | ✅ | ✅ | ❌ (deliberately biometric-free) | ✅ (per marketing) |
| **Vehicle / LPR** | ✅ AvidAuto (Arabic plates) | — | Forklift speed detection | Vehicle & dock activity | — |
| **PLC / machine response** | — | ✅ Carrot Vision | — | — | Robotics integration (claimed) |
| **Alert channels** | VMS-integrated alerts | Email, WhatsApp, sirens | SMS / email / WhatsApp | Telegram / SMS / email, <2 s | Dashboards, alerts, reports |
| **Vertical focus** | Factories, banks, smart cities, stadiums | Cement, construction, oil & gas | Manufacturing, warehousing, retail | Retail, F&B, manufacturing | Oil & gas, petrochemicals, industry-wide |
| **Local partners** | Giza Systems, GET Group | MCC (contractor) | — | — | EGPC/EGAS/ECHEM/GANOPE approvals, RRSC |

## Adopters (documented deployments in Egypt)

| Adopter | Provider | Use case |
|---|---|---|
| Coca-Cola Egypt (44+ factories) | AvidBeam | PPE compliance (helmet/vest), workforce presence & access control |
| Nestlé — 6th of October Zone, Giza (120+ cameras) | AvidBeam | PPE, fire & smoke, anomaly, LPR, face recognition |
| Mars factory — Giza | AvidBeam | Face recognition for workforce attendance |
| Banque Misr / Banque du Caire (200+ branches) | AvidBeam | Face recognition + anomaly detection replacing manual monitoring |
| Misr Stadium, Knowledge City, New Alamein, SODIC/Ora resorts | AvidBeam | Watchlist screening, mask detection, LPR & access control |
| 3 cement factories — world's 2nd-largest cement group | GSD Technologies | PPE, crane zones, fire/smoke, thermal, perimeter, face recognition |
| Precast-concrete national mega-project (via MCC) | Carrot Vision (GSD) | PPE, crane restricted zones, face recognition, fire/smoke, PLC response |
| ElAraby Group | InfoTraff | Real-time monitoring of employee safety & hygiene rule compliance in factories (reported via JETRO) |
| Electrolux Group, Arafa Group, Men's Club, Concrete, 2S Homewear, TBS Holding, BarkoTel | InfoTraff | Safety enforcement + operational analytics across stores and facilities |
| Egypt (government, national highways) | InfoTraff | First national seatbelt-violation detection software (1M+ violations) |
| BP, Shell, Eni, Total, Coca-Cola, Alstom, EzzSteel (HSSEQ/training engagements) | Yellow Helmet Egypt | Safety training, audits, management systems — AI monitoring sold as add-on |
| 10th of Ramadan industrial community — "Safe Industry" initiative (target: 5,000 factories, priority 400) | Yellow Helmet Egypt + British University in Egypt | Factory safety gap analysis & transformation program (launched Oct 2026) |
| (No publicly named Guard clients yet) | MAKKN | Product positioned at manufacturers/warehouses in Egypt & MENA |

## Market takeaways

1. **Local delivery wins in Egypt.** Every documented industrial-safety deployment in Egypt was delivered by a provider with an Egyptian engineering base or exclusive local agent (AvidBeam, GSD/Carrot Vision, InfoTraff, Yellow Helmet) — none by the international players (Protex, viAct, Voxel, Intenseye).
2. **On-premise is the default requirement.** Egyptian industrials (especially cement, oil & gas, banking) demand data stays on-site — GSD/Carrot Vision and AvidBeam both lead with on-premise/edge architectures.
3. **WhatsApp/Telegram alerting is table stakes.** Local providers route alerts through channels Egyptian supervisors actually use, rather than dashboard-only.
4. **Adoption is broadening from FMCG to heavy industry.** FMCG (Coca-Cola, Nestlé, Mars) pioneered adoption; cement, construction, and government-scaled programs (5,000-factory initiative) are the growth frontier.
5. **Opportunity gap.** No local provider yet matches the full international feature set (e.g., PLC hard-stops at ~0.8 s, REBA/RULA ergonomics scoring, generative-AI safety copilots) — combining that depth with local delivery is the open position for a new system.
