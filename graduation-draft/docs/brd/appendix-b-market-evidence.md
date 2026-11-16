[← BRD Index](./README.md)

# Appendix B: Market Evidence

## B.1 Purpose and Snapshot

This appendix summarizes the market context used to sanity-check the BRD. It is not a market-size study, pricing benchmark or proof of willingness to pay.

- **Snapshot:** 23 public listings collected on October 26, 2026.
- **Sources:** Upwork and Freelancer.com.
- **Selection:** computer vision, YOLO, OpenCV, PPE detection, surveillance, object detection, video analytics and natural-language monitoring.
- **Breakdown:** 8 directly relevant, 11 adjacent, 4 outside the current technical scope.
- **Full catalog:** [Similar Job Listings and Projects](../market/similar-job-listings.md).

## B.2 Demand Signals

| Signal | Evidence | BRD relevance |
|---|---|---|
| PPE and safety compliance | Listings 1, 2 and 18 request PPE detection or industrial safety monitoring. | FR-03, BR-01 |
| Fixed-camera video analytics | Listings 1, 7 and 19 work with existing or fixed camera feeds. | FR-01, FR-02, FR-07, BR-01, BR-02 |
| Surveillance event detection | Listings 19, 20 and 22 detect events in live or recorded video. | FR-04, FR-07, FR-11 |
| Object detection and tracking | Listings 4, 5, 8, 9, 11, 12, 16 and 17 use YOLO, tracking or related CV techniques. | FR-02, NFR-01 |
| Natural-language monitoring | Listings 9 and 10 add a text interface for searching or managing monitoring data. | BR-06, FR-16 |
| Duplicate/event filtering | Listing 20 explicitly asks to flag duplicate events in real time. | NFR-03 |
| Edge, cloud or on-premises deployment | Listings 4, 5, 13, 17 and 21 show edge, GPU or local deployment patterns. | NFR-11, OD-01 |
| Face recognition | Listings 2 and 21 include face recognition. | Out of current scope: privacy and legal risk |
| LiDAR, 3D and robotics | Listings 13, 14 and 15 use LiDAR, 3D or ROS. | Out of current scope |

## B.3 Mapping to Requirements

| BRD element | Evidence | Implication |
|---|---|---|
| BR-01 Real-time safety events | 1, 7, 10, 20, 22 | Demand for real-time video analytics and event detection. |
| BR-02 Existing cameras | 7, 18, 20 | Clients work with fixed, CCTV or existing camera feeds. |
| BR-03 Central dashboard | 10, 19 | Monitoring and display needs recur. |
| BR-06 Agentic AI assistant | 10, 9 | Natural-language access to monitoring data is an explicit demand signal. |
| FR-03 Missing PPE | 2, 18 | Direct PPE-detection demand. |
| FR-04 Zone and surveillance detection | 7, 19, 20, 22 | Detection of configured events in camera scenes. |
| FR-16 Natural-language questions | 10 | Direct match for querying events in plain language. |
| NFR-01 Low latency | 4, 5, 21 | Real-time or edge latency appears in several listings. |
| NFR-03 Low false alerts | 20 | Duplicate/event filtering is explicitly requested. |
| NFR-11 Deployment portability | 4, 5, 13, 21 | Edge, cloud and on-premises patterns all appear. |
| OD-01 Deployment model | 4, 5, 13, 21 | The market does not settle the deployment choice; keep it TBD. |

## B.4 Implications for Current Scope

- The evidence supports the **four-core scope**: PPE, hazardous-zone intrusion, work at height and unsafe machine proximity are commercially legible, and PPE/surveillance are the clearest direct matches.
- The evidence supports keeping the **AI assistant as `Must`**: buyers explicitly ask for natural-language access to monitoring data.
- The evidence supports keeping **deployment flexible**: edge, cloud and on-premises patterns all appear, so OD-01 remains open.
- **Face recognition is not added to scope.** Demand exists, but it carries privacy and legal risk that the BRD does not currently address.
- **LiDAR, 3D and robotics are not added to scope.** They fall outside the RGB-camera-only constraint.

## B.5 Egypt-Specific Injury Evidence

CAPMAS reports **8,091 work injuries** across **2,225,169 workers** in covered establishments in 2024. The evidence supports the current scope without changing it:

- **Manufacturing** accounts for 3,687 cases (45.6%), making it the main volume segment.
- **Construction** accounts for 557 cases (6.9%) but 22 of 48 deaths (45.8%) and a fatal-injury rate of 37.1 per 100,000 workers.
- **Falls (32.1%)** and **collision with objects (27.6%)** are the leading causes; upper and lower limbs account for 54.3% of injured organs.
- This supports PPE, falls, obstacle/collision, exclusion-zone and machine-proximity detection, but it is problem evidence rather than proof of demand.

Full extraction: [CAPMAS Work Injuries 2024](../market/capmas-work-injuries-2024.md).

## B.6 Limitations

- These are freelance listings, not enterprise procurement contracts.
- The sample is small and not statistically representative.
- Some listings are search-result pages and may change or expire.
- Budgets and experience levels are recorded as displayed and are not normalized.
- The evidence says nothing definitive about Egyptian or MENA market size or willingness to pay.

---

[← BRD Index](./README.md) | [Previous: Appendix A: Traceability Matrix](./appendix-a-traceability-matrix.md)
