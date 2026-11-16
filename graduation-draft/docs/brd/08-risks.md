[← BRD Index](./README.md)

# 8. Risks

## 8.1 List of Risks

Potential risks that could impact the project:

| **ID** | **Risk** | **Impact** |
|---|---|---|
| R1 | Poor lighting, angle or resolution lowers detection accuracy. | Violations are missed or wrongly flagged. |
| R2 | Too many false alerts make operators ignore the system. | The system loses its value and real violations are overlooked. |
| R3 | Privacy and legal exposure from storing video of workers. | Legal risk and loss of workers' trust. |
| R4 | Scope is too large for the academic schedule. | Core features are not delivered in time. |
| R5 | No real facility data is available. | The system cannot be tested in real conditions. |

## 8.2 Risk Mitigation Strategies

The actions to mitigate each risk (proposed):

| **ID** | **Mitigation** |
|---|---|
| R1 | Test on varied footage early; set minimum camera guidance. |
| R2 | Tune thresholds per zone; let operators dismiss and mark each alert (FR-13). |
| R3 | Redaction, role-based access and audit logs (CON-07, FR-21 to FR-23). |
| R4 | Deliver Must items first; treat Should items as stretch (CON-09). |
| R5 | Use the lab mockup and replay mode (FR-24). |

---

[← BRD Index](./README.md) | [Previous: 7. Assumptions](./07-assumptions.md) | [Next: 9. Dependencies →](./09-dependencies.md)
