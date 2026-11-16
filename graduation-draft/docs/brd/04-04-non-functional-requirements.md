[← BRD Index](./README.md)

# 4.4 Non-Functional Requirements

> Document: BRD-2026-Q4-001 · Section: 4.4 · Document owner: Muhammed Hany Hamdy AboAlia · Reviewer: TBD · Status: Draft

The non-functional requirements describe how well the system must perform. The summary states the requirement and target; the verification table states the conditions and the method used to decide pass or fail. Targets marked as proposed or TBD are starting points.

## 4.4.1 NFR Summary

| **ID** | **Category** | **Requirement** | **Target** | **BR** |
|---|---|---|---|---|
| NFR-01 | Performance | The system shall deliver a violation event to the dashboard within 5 seconds or less for at least 95% of events, measured from the violation appearing on camera to the alert appearing on the dashboard. | p95 5 seconds or less (proposed) | BR-01, BR-03 |
| NFR-02 | Accuracy | The system shall meet the precision and recall targets agreed for each of the four violation types on a labelled test set. | TBD after baseline (OD-02) | BR-01 |
| NFR-03 | False alerts | The system shall keep false alerts below the maximum rate agreed per camera per hour for each violation type. | TBD after baseline (OD-02) | BR-01, BR-09 |
| NFR-04 | Scalability | The system shall process the agreed number of concurrent camera streams on the chosen deployment while meeting NFR-01. | TBD after load test (OD-01) | BR-02, BR-08 |
| NFR-05 | Reliability | The system shall recover automatically from a dropped camera stream without manual restart. | Automatic recovery | BR-01 |
| NFR-06 | Security | The system shall enforce authentication and role-based authorization for every protected function, and encrypt data in transit and at rest. | All protected functions and data | BR-10 |
| NFR-07 | Privacy | The system shall redact faces or identities before footage is shown or exported to roles without identity access. | Redaction by default | BR-10 |
| NFR-08 | Usability | The system shall let an operator review and resolve an alert without training on the model. | 2 of 3 users within 2 minutes (proposed) | BR-03, BR-09 |
| NFR-09 | Maintainability | The system shall support adding a new rule type or safety service through configuration plus one new module, without changing the platform core. | One module; no core changes | BR-07, BR-08 |
| NFR-10 | Interoperability | The system shall expose a documented and versioned event interface. | Published, versioned schema | BR-04 |
| NFR-11 | Portability | The system shall run on the agreed demo deployment and on at least one alternate deployment target without a major architecture rewrite. | Demo target fixed; final TBD (OD-01) | BR-02, BR-11 |
| NFR-12 | Compliance | The system shall produce reports containing the fields required for audit traceability. | Field list TBD with supervisor | BR-05 |

## 4.4.2 NFR Verification

| **ID** | **Conditions** | **How measured** |
|---|---|---|
| NFR-01 | Proposed test profile: 4 concurrent camera streams at 1080p and 15 fps, 10-minute recorded run, synchronized camera and dashboard clocks, no manual intervention. | Scripted end-to-end test; compute p95 event-to-alert latency from timestamped events; pass if p95 is 5 seconds or less; fail otherwise. |
| NFR-02 | Labelled footage covering all four violation types, indoor and outdoor lighting, partial occlusion, and at least two camera angles; final thresholds TBD (OD-02). | Run each violation type against the labelled clips; compute precision, recall and confusion counts; pass when every type meets its agreed threshold; fail otherwise. |
| NFR-03 | Test footage from at least two cameras and two lighting conditions, with ground-truth labels and operator review; final thresholds TBD (OD-02). | Count false alerts per camera-hour and compute the rate for each violation type; pass when the rate is at or below the agreed maximum; fail otherwise. |
| NFR-04 | Agreed deployment model; step-load test from 1 to the target camera count at 1080p and 15 fps; target count TBD (OD-01). | Step-load test; record the highest stream count with p95 alert latency of 5 seconds or less and no event loss; pass when it meets or exceeds the agreed target; fail otherwise. |
| NFR-05 | Force a 60-second stream drop for one camera during an active detection run. | Automated stream-drop test; pass when the source returns online and events resume without a restart; fail if manual restart is required. |
| NFR-06 | Test environment with operator, manager, administrator and auditor roles; seeded events and configuration data. | API and UI tests for missing or invalid credentials and cross-role denial; transport and storage encryption checks; pass when all checks pass and no unauthorized access occurs. |
| NFR-07 | Test footage with identifiable faces; roles with and without identity access; display and export flows. | Review displayed and exported files; pass when redaction is applied by default and no unredacted frame is accessible to unauthorized roles; check access logging. |
| NFR-08 | Moderated test with at least 3 representative users, pre-seeded alerts, and a task statement only. | Record task completion, time and interventions; pass when at least 2 of 3 users resolve an alert within 2 minutes with no model-specific training and at most 1 intervention. |
| NFR-09 | Add one new rule type in a test branch using the documented extension point. | Code review plus configuration-only setup; pass when the new rule runs and no core module changes are required; fail if core changes are needed. |
| NFR-10 | Event schema and API documentation; one subscriber consuming events. | Schema validation test and subscriber integration test; pass when events validate against the published schema and the subscriber receives them; fail otherwise. |
| NFR-11 | Agreed demo target plus one alternate on-premises, cloud or edge target; same build artifact; final production model TBD (OD-01). | Deployment test on both targets; pass when the same build runs the demo flow on both with configuration-only changes; fail if a code rewrite is required. |
| NFR-12 | Auditor field checklist agreed with the supervisor; sample report generated from stored events. | Field-by-field checklist review; pass when every required field is present and traceable to its event; fail otherwise. |

## 4.4.3 Traceability Notes

- NFR-01 uses a proposed test profile and a 5-second p95 target. The profile can be adjusted before baseline testing, but the measurement method stays the same.
- NFR-02 and NFR-03 remain open as OD-02. Baseline testing will set precision, recall and false-alert thresholds per violation type.
- NFR-04 and NFR-11 depend on OD-01, because the deployment model sets the capacity and portability baseline.
- NFR-08 uses a proposed usability threshold so the requirement is testable now; confirm the participant count and time limit before the usability test.
- BR-06 has no dedicated NFR. Assistant answer quality is verified through S-08 and S-09 and the human-review controls in FR-18.

## 4.4.4 Checklist

- [x] Every NFR has a stable ID, category and measurable requirement.
- [x] Every NFR states the conditions under which it is measured.
- [x] Every NFR states how pass or fail is decided.
- [x] Every NFR traces to at least one BR.
- [x] Open targets are marked as proposed or TBD.

---

[← BRD Index](./README.md) | [Previous: 4.3 Functional Requirements](./04-03-functional-requirements.md) | [Next: 5. Stakeholders →](./05-stakeholders.md)
