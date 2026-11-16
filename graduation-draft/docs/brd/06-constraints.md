[← BRD Index](./README.md)

# 6. Constraints

## 6.1 Budgetary Constraints

No budget for new sensors or cameras, and a low-cost design that small and mid-sized facilities can afford:

| **ID** | **Constraint** | **Source** |
|---|---|---|
| CON-01 | The system uses existing CCTV/IP cameras and recorded footage only; no new cameras or sensors are required or assumed. | BR-02, P3 |
| CON-02 | The solution is software and AI only; compute may be on-premises, cloud, or edge; no mandatory AI-specific accelerators are assumed. | BR-02, P3 |
| CON-10 | The design must not depend on a closed commercial analytics platform. | P3 |

## 6.2 Timeline Constraints

The project is delivered within the academic schedule of the graduation project:

| **ID** | **Constraint** | **Source** |
|---|---|---|
| CON-09 | Scope is one facility (or lab mockup) at graduation-project level, delivered within the academic schedule. Final milestone dates are to be confirmed with the supervisor. | BR-11, P3 |

## 6.3 Regulatory Constraints

Regulatory and compliance requirements that must be adhered to:

| **ID** | **Constraint** | **Source** |
|---|---|---|
| CON-07 | Handling of video and personal data follows applicable Egyptian data-protection law, with role-based access, encryption, redaction and audit logs. | BR-10 |
| CON-08 | Safety rule types and reports align with OSHA, ISO 45001 and Egyptian workplace-safety law. | BR-05, Auditor |

## 6.4 Technical and Scope Constraints

Technical and scope limits that any solution must respect:

| **ID** | **Constraint** | **Source** |
|---|---|---|
| CON-03 | Video input comes from standard camera streams or recorded video files, so a lab mockup can replace a live site. | BR-02, BR-11 |
| CON-04 | Zones, schedules and rule types are set through configuration, never by changing code. | BR-07 |
| CON-05 | Each safety service is a separate module; removing or adding one must not change the platform core. | BR-08 |
| CON-06 | The system only recommends; any high-consequence action requires an operator decision. | BR-09 |

---

[← BRD Index](./README.md) | [Previous: 5. Stakeholders](./05-stakeholders.md) | [Next: 7. Assumptions →](./07-assumptions.md)
