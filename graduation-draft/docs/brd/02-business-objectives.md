[← BRD Index](./README.md)

# 2. Business Objectives

> Document: BRD-2026-Q4-001 · Section: 2 · Document owner: Muhammed Hany Hamdy AboAlia · Reviewer: TBD · Status: Draft

## 2.1 Business Goals

The business goals the project aims to achieve:

| **ID** | **Business goal** | **Solves** |
|---|---|---|
| G-01 | Detect safety violations as they happen, instead of at audits or after incidents. | P1 |
| G-02 | Give one unified view of floor activity and facility risk. | P2 |
| G-03 | Make AI safety monitoring affordable by reusing existing cameras, with no new cameras or sensors. | P3 |
| G-04 | Produce the data needed for audits and regulatory reporting. | P1 |

## 2.2 Project Objectives

The project objectives are the business requirements (BR). Each one answers at least one of the core [problems in section 3.2](./03-current-business-environment.md#32-challenges-and-issues) and is delivered through the linked customer requirements (CR) in [section 4.2](./04-02-customer-requirements.md).

| **ID** | **Business requirement** | **Solves** | **Linked CRs** |
|---|---|---|---|
| BR-01 | Continuously convert existing camera feeds into structured, timestamped, actionable safety events in real time for the four in-scope violation types. | P1 | CR-01, CR-02 |
| BR-02 | Operate on existing CCTV/IP cameras and recorded footage only, with no new cameras or sensors. | P3 | CR-06 |
| BR-03 | Provide one central dashboard with live or replayed feeds, an alert list and a facility-wide view. | P2 | CR-01, CR-03 |
| BR-04 | Expose a standardized event stream usable by alerts, dashboards and external systems. | P2 | CR-12 |
| BR-05 | Provide a facility-level risk picture and reports for audits and regulatory reporting. | P1, P2 | CR-03, CR-04, CR-09 |
| BR-06 | Provide an agentic AI assistant that interprets events, answers questions and drafts reports. | P1, P2 | CR-05 |
| BR-07 | Be generic and reusable: zones, schedules and rule types come from configuration, not code. | P3 | CR-08 |
| BR-08 | Let a facility adopt any subset of safety services without affecting the platform core. | P3 | CR-07 |
| BR-09 | Keep high-consequence decisions with humans; the system recommends, operators decide. | P1 | CR-02, CR-10 |
| BR-10 | Meet privacy and security obligations: role-based access, encryption, redaction, audit logs. | P1 | CR-08, CR-10 |
| BR-11 | Deliver a defendable end-to-end graduation demo across model, pipeline, dashboard and reporting. | P3 | CR-11 |

## 2.3 Success Criteria

The project is successful when the following criteria are met. Targets marked as proposed or TBD are to be confirmed with the supervisor.

| **ID** | **Success criterion** | **Traces to** |
|---|---|---|
| S-01 | Each of the four violation types (missing PPE, hazardous-zone intrusion, unprotected work at height, unsafe machine proximity) is detected and raised as an event in the end-to-end demo. | BR-01 |
| S-02 | Alerts reach the dashboard within the latency target in NFR-01 (proposed: 5 seconds or less). | BR-01, BR-03 |
| S-03 | Detection accuracy and false-alert rates meet the targets agreed after baseline testing (NFR-02, NFR-03); the targets are TBD. | BR-01, BR-09 |
| S-04 | The demo runs on camera-style footage using existing or recorded feeds, with no new cameras or sensors. | BR-02, BR-11 |
| S-05 | A new zone, schedule or rule is added through configuration only, without code changes. | BR-07 |
| S-06 | An audit report is generated from stored events and exported. | BR-05 |
| S-07 | The supervisor and examiners accept the end-to-end demo. | BR-11 |
| S-08 | The assistant answers at least three representative natural-language questions about stored events and cites the events used. | BR-06, BR-09 |
| S-09 | The assistant drafts a report that a manager reviews and edits before export; the final report is attributed to the human approver. | BR-06, BR-09 |

## 2.4 Traceability Notes

- Every business requirement has at least one linked customer requirement and at least one functional requirement. The reverse links are in [Appendix A](./appendix-a-traceability-matrix.md).
- BR-04 previously had no customer requirement. CR-12 was added for the IT / system administrator role so that the standardized event stream has a named consumer need rather than an orphan business objective.
- BR-06 is covered by CR-05 and FR-16 to FR-18. It has no dedicated NFR because assistant answer quality is verified through success criteria S-08 and S-09 and the human-review controls in FR-18.
- BR-06 and BR-09 both depend on human review. This is intentional: the assistant may draft and explain, but a person approves reports and high-consequence decisions.

## 2.5 Checklist

- [x] Each business goal traces to a core problem or delivery objective.
- [x] Each BR has a stable ID and a linked CR.
- [x] Each BR has at least one linked FR in Appendix A.
- [x] Success criteria identify the BR they verify.
- [x] Open targets are marked as proposed or TBD.

---

[← BRD Index](./README.md) | [Previous: 1. Introduction](./01-introduction.md) | [Next: 3. Current Business Environment →](./03-current-business-environment.md)
