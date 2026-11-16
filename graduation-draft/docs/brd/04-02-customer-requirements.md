[← BRD Index](./README.md)

# 4.2 Customer Requirements (CR)

> Document: BRD-2026-Q4-001 · Section: 4.2 · Document owner: Muhammed Hany Hamdy AboAlia · Reviewer: TBD · Status: Draft

Customer requirements state what each stakeholder group needs from the system, in their own terms. They come from the stakeholder pains in [section 5.1](./05-stakeholders.md#51-list-of-stakeholders) and trace to the business requirements.

## 4.2.1 Security / Control-Room Operator

| **ID** | **Requirement** | **BR** | **FR** |
|---|---|---|---|
| CR-01 | See safety violations as they happen on the existing cameras, without watching raw video all day. | BR-01, BR-03 | FR-02, FR-03, FR-04, FR-05, FR-06, FR-10, FR-11 |
| CR-02 | Get a clear alert with a snapshot or clip as evidence, so I can decide quickly. | BR-01, BR-09 | FR-02, FR-03, FR-04, FR-05, FR-06, FR-07, FR-09, FR-10, FR-11, FR-13 |

## 4.2.2 Safety / Operations Manager

| **ID** | **Requirement** | **BR** | **FR** |
|---|---|---|---|
| CR-03 | See all violations and the facility's risk in one place instead of paper logs and spreadsheets. | BR-03, BR-05 | FR-07, FR-09, FR-11, FR-12, FR-14 |
| CR-04 | Measure risk by violation type, zone and period to prioritise action. | BR-05 | FR-12, FR-14 |
| CR-05 | Ask questions in plain language and get draft reports I can review. | BR-06 | FR-16, FR-17, FR-18 |

## 4.2.3 Facility Owner

| **ID** | **Requirement** | **BR** | **FR** |
|---|---|---|---|
| CR-06 | Adopt the system without buying new cameras or sensors, using on-premises, cloud or edge compute at a cost a small or mid-sized site can afford. | BR-02 | FR-01 |
| CR-07 | Choose only the safety services my site needs. | BR-08 | FR-20 |

## 4.2.4 IT / System Administrator

| **ID** | **Requirement** | **BR** | **FR** |
|---|---|---|---|
| CR-08 | Configure cameras, zones, schedules and user access in one place, without code changes. | BR-07, BR-10 | FR-01, FR-04, FR-19, FR-20, FR-21 |
| CR-12 | Connect safety events to our existing alarm, dashboard or reporting tools through a documented, stable interface. | BR-04 | FR-07, FR-08 |

## 4.2.5 Auditor / Regulator

| **ID** | **Requirement** | **BR** | **FR** |
|---|---|---|---|
| CR-09 | Receive traceable evidence and reports that fit OSHA, ISO 45001 and Egyptian law. | BR-05 | FR-07, FR-09, FR-15, FR-18, FR-22, FR-23 |

## 4.2.6 Cross-Role Governance

| **ID** | **Requirement** | **BR** | **FR** |
|---|---|---|---|
| CR-10 | Keep decisions with people, and keep a record of who decided what. | BR-09, BR-10 | FR-09, FR-13, FR-15, FR-18, FR-20, FR-21, FR-22, FR-23 |

## 4.2.7 Supervisor and Examiners

| **ID** | **Requirement** | **BR** | **FR** |
|---|---|---|---|
| CR-11 | See a feasible, scoped, end-to-end demo from detection to report. | BR-11 | FR-24 |

## 4.2.8 Traceability Notes

- Each CR traces to at least one BR and at least one high-level FR. Low-level FR rows in [section 4.3](./04-03-functional-requirements.md) carry the direct CR link used by the SRS.
- CR-12 was added during traceability review because BR-04 had no customer requirement. It names the IT integration need that consumes the event stream.
- CR-10 is cross-role because recording human decisions and access applies to operators, managers and auditors.
- CR-11 is a project-delivery requirement for the supervisor and examiners, not an operational site role.

## 4.2.9 Checklist

- [x] Every CR has a stable ID.
- [x] Every CR traces to at least one BR.
- [x] Every CR links to at least one high-level FR.
- [x] CRs are grouped by stakeholder group.
- [x] CR-12 closes the BR-04 traceability gap.

---

[← BRD Index](./README.md) | [Previous: 4.1 Description of the Solution](./04-01-solution-description.md) | [Next: 4.3 Functional Requirements →](./04-03-functional-requirements.md)
