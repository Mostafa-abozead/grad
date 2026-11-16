[← BRD Index](./README.md)

# Appendix A: Traceability Matrix

> Document: BRD-2026-Q4-001 · Appendix A · Document owner: Muhammed Hany Hamdy AboAlia · Reviewer: TBD · Status: Draft

## A.1 Business Requirements to Requirements

Every business requirement traces back to a core problem and forward to the customer, functional and non-functional requirements that deliver it. Constraints (CON-01 to CON-10, [section 6](./06-constraints.md)) list their own sources in that section.

| **BR** | **FR** | **NFR** | **CR** |
|---|---|---|---|
| BR-01 | FR-01, FR-02, FR-03, FR-04, FR-05, FR-06, FR-07 | NFR-01, NFR-02, NFR-03, NFR-05 | CR-01, CR-02 |
| BR-02 | FR-01 | NFR-04, NFR-11 | CR-06 |
| BR-03 | FR-10, FR-11, FR-12 | NFR-01, NFR-08 | CR-01, CR-03 |
| BR-04 | FR-07, FR-08, FR-09 | NFR-10 | CR-12 |
| BR-05 | FR-09, FR-14, FR-15 | NFR-12 | CR-03, CR-04, CR-09 |
| BR-06 | FR-16, FR-17, FR-18 | none | CR-05 |
| BR-07 | FR-04, FR-19 | NFR-09 | CR-08 |
| BR-08 | FR-20 | NFR-04, NFR-09 | CR-07 |
| BR-09 | FR-13, FR-18 | NFR-03, NFR-08 | CR-02, CR-10 |
| BR-10 | FR-21, FR-22, FR-23 | NFR-06, NFR-07 | CR-08, CR-10 |
| BR-11 | FR-24 | NFR-11 | CR-11 |

## A.2 Customer Requirements to Functional Requirements

This matrix links each customer requirement to its business requirement and high-level functional requirements. Direct low-level CR links are in [section 4.3.2](./04-03-functional-requirements.md#432-low-level-functional-requirements).

| **CR** | **BR** | **FR** |
|---|---|---|
| CR-01 | BR-01, BR-03 | FR-02, FR-03, FR-04, FR-05, FR-06, FR-10, FR-11 |
| CR-02 | BR-01, BR-09 | FR-02, FR-03, FR-04, FR-05, FR-06, FR-07, FR-09, FR-10, FR-11, FR-13 |
| CR-03 | BR-03, BR-05 | FR-07, FR-09, FR-11, FR-12, FR-14 |
| CR-04 | BR-05 | FR-12, FR-14 |
| CR-05 | BR-06 | FR-16, FR-17, FR-18 |
| CR-06 | BR-02 | FR-01 |
| CR-07 | BR-08 | FR-20 |
| CR-08 | BR-07, BR-10 | FR-01, FR-04, FR-19, FR-20, FR-21 |
| CR-09 | BR-05 | FR-07, FR-09, FR-15, FR-18, FR-22, FR-23 |
| CR-10 | BR-09, BR-10 | FR-09, FR-13, FR-15, FR-18, FR-20, FR-21, FR-22, FR-23 |
| CR-11 | BR-11 | FR-24 |
| CR-12 | BR-04 | FR-07, FR-08 |

## A.3 Coverage Summary

| **Requirement set** | **Count** | **Coverage result** |
|---|---|---|
| Business requirements | 11 | Every BR has at least one CR and at least one FR. |
| Customer requirements | 12 | Every CR has at least one BR and at least one high-level FR. |
| High-level functional requirements | 24 | Every high-level FR has at least one CR and at least one BR. |
| Low-level functional requirements | 93 | Every low-level FR links to a CR; every CR appears in at least one low-level FR. |
| Non-functional requirements | 12 | Every NFR links to at least one BR. |

**Orphan check:** none. BR-04 is no longer an orphan because CR-12 links the standardized event stream to an IT integration need. BR-06 has functional coverage but no dedicated NFR by design; its quality is verified through S-08, S-09 and FR-18.

## A.4 Traceability Rules

- Requirement IDs are stable. New requirements take the next free ID and existing IDs are not renumbered.
- A high-level FR may have 2 to 5 low-level FRs. Each low-level FR inherits the parent priority and has its own CR link.
- Every NFR states its measurement conditions and method; unresolved targets stay visible as proposed or TBD.
- The matrix is updated whenever a BR, CR, FR or NFR is added, removed or re-linked.
- A requirement with no upstream or downstream link is treated as a traceability defect until the team records an explicit rationale.

## A.5 Checklist

- [x] BR to CR links are present for all 11 BRs.
- [x] BR to FR and NFR links are present.
- [x] CR to high-level FR links are present for all 12 CRs.
- [x] Low-level FR to CR links are present in section 4.3.2.
- [x] Orphan check is recorded.
- [x] Open decisions and proposed targets are identified.

---

[← BRD Index](./README.md) | [Previous: 10. Approval](./10-approval.md)
