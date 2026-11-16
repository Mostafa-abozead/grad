[← BRD Index](./README.md)

# 1. Introduction

## 1.1 Purpose of the Document

The purpose of this Business Requirements Document (BRD) is to define the business objectives, scope, and requirements for the AI-Powered Industrial Safety & Surveillance System project. It builds on the project's problem statement (problems P1 to P3) and is the input for the Software Requirements Specification (SRS).

## 1.2 Scope of the Project

The current BRD scope covers four core violation types: missing PPE, hazardous-zone intrusion, unprotected work at height, and unsafe machine proximity. It also covers the platform capabilities needed to deliver them: a standardized event stream, a central dashboard with alerts, a facility risk view and audit reports, an agentic AI assistant (`Must`), configuration of zones and rules, role-based security and privacy controls, and an end-to-end demo at one facility or a lab mockup.

| Area | Current scope |
|---|---|
| Detection | Four core violation types: missing PPE, hazardous-zone intrusion, unprotected work at height, and unsafe machine proximity. |
| Platform | Standardized event stream; dashboard with alerts and replays; facility risk view and audit reports; agentic AI assistant (`Must`); configuration; role-based security and privacy controls; demo replay. |
| Hardware and deployment | Existing CCTV/IP cameras and recorded footage only; no new cameras or sensors. Compute may be on-premises, in the cloud, or at the edge; the deployment model is TBD (OD-01). |
| Roadmap | Fire and smoke detection, housekeeping, worker location, access control, and behavioral unsafe-act detection remain roadmap items, not current scope. Vehicle safety is out of scope. |
| Out of scope | Buying or installing cameras or other sensors; automatic physical actions (such as stopping machines or locking doors) without a human decision; multi-site or multi-tenant rollout; face recognition; LiDAR, 3D or robotics perception. |

## 1.3 Document Overview

Section 2 states the business goals, project objectives (BR-01 to BR-11) and success criteria. Section 3 describes the current environment, its problems and market demand signals. Section 4 describes the proposed solution with its customer requirements (CR), high-level and low-level functional requirements (FR), and non-functional requirements (NFR). Sections 5 to 9 cover stakeholders, constraints, assumptions, risks and dependencies. Section 10 holds the approval. Appendix A traces business requirements to CRs, FRs and NFRs and includes CR-to-FR coverage; Appendix B summarizes the market evidence.

---

[← BRD Index](./README.md) | [Next: 2. Business Objectives →](./02-business-objectives.md)
