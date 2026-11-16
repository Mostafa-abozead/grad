[← BRD Index](./README.md)

# 4.3 Functional Requirements

> Document: BRD-2026-Q4-001 · Section: 4.3 · Document owner: Muhammed Hany Hamdy AboAlia · Reviewer: TBD · Status: Draft

The functional requirements are grouped into 24 high-level requirements. Each high-level requirement is decomposed into atomic low-level requirements (`FR-xx.y`) that an SRS can test directly. Low-level requirements inherit the priority of their parent.

## 4.3.1 High-Level Functional Requirements

| **ID** | **High-level FR (verb title)** | **Priority** | **CR** | **BR** |
|---|---|---|---|---|
| FR-01 | Connect to camera streams and video files | Must | CR-06, CR-08 | BR-01, BR-02 |
| FR-02 | Detect people and objects in real time | Must | CR-01, CR-02 | BR-01 |
| FR-03 | Detect missing PPE | Must | CR-01, CR-02 | BR-01 |
| FR-04 | Detect hazardous-zone intrusion | Must | CR-01, CR-02, CR-08 | BR-01, BR-07 |
| FR-05 | Detect unprotected work at height | Must | CR-01, CR-02 | BR-01 |
| FR-06 | Detect unsafe person-machine proximity | Must | CR-01, CR-02 | BR-01 |
| FR-07 | Create structured safety events | Must | CR-02, CR-03, CR-09, CR-12 | BR-01, BR-04 |
| FR-08 | Publish a standardized event stream | Must | CR-12 | BR-04 |
| FR-09 | Store events and evidence | Must | CR-02, CR-03, CR-09, CR-10 | BR-04, BR-05 |
| FR-10 | Display live and recorded feeds | Must | CR-01, CR-02 | BR-03 |
| FR-11 | Display filterable alerts | Must | CR-01, CR-02, CR-03 | BR-03 |
| FR-12 | Display facility overview | Should | CR-03, CR-04 | BR-03 |
| FR-13 | Review and decide on alerts | Must | CR-02, CR-10 | BR-09 |
| FR-14 | Compute facility risk indicators | Must | CR-03, CR-04 | BR-05 |
| FR-15 | Generate and export audit reports | Must | CR-09, CR-10 | BR-05 |
| FR-16 | Answer questions about events | Must | CR-05 | BR-06 |
| FR-17 | Interpret and summarize events | Must | CR-05 | BR-06 |
| FR-18 | Draft reports for human review | Must | CR-05, CR-09, CR-10 | BR-06, BR-09 |
| FR-19 | Configure cameras, zones, schedules and rules | Must | CR-08 | BR-07 |
| FR-20 | Enable or disable safety services | Must | CR-07, CR-08, CR-10 | BR-08 |
| FR-21 | Enforce role-based access | Must | CR-08, CR-10 | BR-10 |
| FR-22 | Maintain audit log | Must | CR-09, CR-10 | BR-10 |
| FR-23 | Redact faces and identities | Should | CR-09, CR-10 | BR-10 |
| FR-24 | Replay demo footage | Must | CR-11 | BR-11 |

## 4.3.2 Low-Level Functional Requirements

### FR-01 — Connect to camera streams and video files

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-01.1 | The system shall connect to configured live camera streams using supported streaming protocols. | CR-06, CR-08 |
| FR-01.2 | The system shall ingest recorded video files from configured storage locations. | CR-06 |
| FR-01.3 | The system shall report each configured source as connecting, online, offline or failed. | CR-08 |
| FR-01.4 | The system shall validate source configuration before saving it. | CR-08 |

### FR-02 — Detect people and objects in real time

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-02.1 | The system shall detect people in each processed frame from an online source. | CR-01 |
| FR-02.2 | The system shall detect the objects relevant to each enabled safety rule. | CR-01 |
| FR-02.3 | The system shall track detected people and objects across consecutive frames. | CR-01 |
| FR-02.4 | The system shall attach a confidence value to each detection. | CR-02 |

### FR-03 — Detect missing PPE

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-03.1 | The system shall detect a person inside a monitored zone who is not wearing the PPE required for that zone. | CR-01 |
| FR-03.2 | The system shall create an event when missing PPE is detected, including camera, zone, timestamp, confidence and evidence. | CR-02 |
| FR-03.3 | The system shall include the missing PPE type in the event. | CR-02 |
| FR-03.4 | The system shall suppress repeat missing-PPE events for the same person and zone within a configured debounce period. | CR-01 |

### FR-04 — Detect hazardous-zone intrusion

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-04.1 | The system shall detect a person entering a configured hazardous zone. | CR-01 |
| FR-04.2 | The system shall apply the configured schedule when evaluating zone intrusion. | CR-08 |
| FR-04.3 | The system shall create an intrusion event with camera, zone, timestamp, confidence and evidence. | CR-02 |
| FR-04.4 | The system shall ignore zone intrusion outside the configured schedule. | CR-08 |

### FR-05 — Detect unprotected work at height

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-05.1 | The system shall detect a person working at height in a monitored zone. | CR-01 |
| FR-05.2 | The system shall determine whether the required fall protection is present for that person. | CR-01 |
| FR-05.3 | The system shall create an event when unprotected work at height is detected, including camera, zone, timestamp, confidence and evidence. | CR-02 |
| FR-05.4 | The system shall suppress repeat work-at-height events for the same person and zone within a configured debounce period. | CR-01 |

### FR-06 — Detect unsafe person-machine proximity

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-06.1 | The system shall detect when a person enters the configured minimum distance of a machine. | CR-01 |
| FR-06.2 | The system shall create a proximity event with camera, zone, timestamp, confidence and evidence. | CR-02 |
| FR-06.3 | The system shall suppress repeat proximity events for the same person and machine within a configured debounce period. | CR-01 |

### FR-07 — Create structured safety events

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-07.1 | The system shall create a structured event for each confirmed rule detection. | CR-02 |
| FR-07.2 | The system shall include event type, timestamp, camera, zone, confidence and source in each event. | CR-02, CR-09, CR-12 |
| FR-07.3 | The system shall attach a snapshot or clip reference as evidence to each event. | CR-02 |
| FR-07.4 | The system shall assign a unique event identifier. | CR-12 |
| FR-07.5 | The system shall store each event in a form retrievable by dashboard, reporting and event-stream consumers. | CR-03, CR-09, CR-12 |

### FR-08 — Publish a standardized event stream

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-08.1 | The system shall expose a documented and versioned event interface. | CR-12 |
| FR-08.2 | The system shall publish events to authorized subscribers in near real time. | CR-12 |
| FR-08.3 | The system shall reject subscriptions that do not authenticate. | CR-12 |
| FR-08.4 | The system shall validate event payloads against the published schema before publishing. | CR-12 |

### FR-09 — Store events and evidence

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-09.1 | The system shall persist each event with its evidence reference. | CR-02 |
| FR-09.2 | The system shall retain events and evidence for the configured retention period. | CR-09 |
| FR-09.3 | The system shall retrieve stored events by time, camera, zone and event type. | CR-03, CR-09 |
| FR-09.4 | The system shall prevent deletion of audit-relevant events except through authorized retention or purge operations. | CR-09, CR-10 |

### FR-10 — Display live and recorded feeds

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-10.1 | The system shall display live feeds from authorized cameras. | CR-01 |
| FR-10.2 | The system shall display recorded footage for a selected time range. | CR-01, CR-02 |
| FR-10.3 | The system shall overlay detection and zone information on displayed feeds. | CR-01 |
| FR-10.4 | The system shall indicate when a camera feed is offline or unavailable. | CR-01 |

### FR-11 — Display filterable alerts

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-11.1 | The system shall display events as an alert list ordered by time. | CR-01, CR-03 |
| FR-11.2 | The system shall filter alerts by type, camera, zone, time and status. | CR-03 |
| FR-11.3 | The system shall show alert evidence and current status from the alert list. | CR-02 |
| FR-11.4 | The system shall update the alert list when a new event arrives. | CR-01 |

### FR-12 — Display facility overview

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-12.1 | The system shall display the facility layout with configured zones. | CR-03 |
| FR-12.2 | The system shall show current alert counts by zone and type. | CR-03, CR-04 |
| FR-12.3 | The system shall update the facility view when a zone or alert status changes. | CR-03 |

### FR-13 — Review and decide on alerts

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-13.1 | The system shall allow an authorized operator to confirm an alert. | CR-02, CR-10 |
| FR-13.2 | The system shall allow an authorized operator to dismiss an alert and record a reason. | CR-02, CR-10 |
| FR-13.3 | The system shall allow an authorized operator to escalate an alert. | CR-02, CR-10 |
| FR-13.4 | The system shall record the decision, user and timestamp for each alert. | CR-10 |
| FR-13.5 | The system shall not execute a high-consequence action without an operator decision. | CR-10 |

### FR-14 — Compute facility risk indicators

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-14.1 | The system shall compute event counts by violation type, zone and period. | CR-04 |
| FR-14.2 | The system shall compute trends for each violation type over time. | CR-04 |
| FR-14.3 | The system shall display the current risk indicators. | CR-03, CR-04 |
| FR-14.4 | The system shall recalculate risk indicators when new events are stored. | CR-04 |

### FR-15 — Generate and export audit reports

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-15.1 | The system shall generate a report for a selected period, facility or zone. | CR-09 |
| FR-15.2 | The system shall include event evidence and operator decisions in the report. | CR-09 |
| FR-15.3 | The system shall export reports in a shareable format. | CR-09 |
| FR-15.4 | The system shall record who exported each report and when. | CR-09, CR-10 |

### FR-16 — Answer questions about events

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-16.1 | The system shall accept natural-language questions about stored events and risk. | CR-05 |
| FR-16.2 | The system shall answer questions using only authorized stored data. | CR-05 |
| FR-16.3 | The system shall cite the events used in each answer. | CR-05 |
| FR-16.4 | The system shall state when stored data is insufficient to answer a question. | CR-05 |

### FR-17 — Interpret and summarize events

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-17.1 | The system shall summarize a selected event or group of events. | CR-05 |
| FR-17.2 | The system shall explain the rule and evidence associated with an event. | CR-05 |
| FR-17.3 | The system shall identify related events in a selected period or zone. | CR-05 |

### FR-18 — Draft reports for human review

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-18.1 | The system shall draft a report from selected events and risk indicators. | CR-05, CR-09 |
| FR-18.2 | The system shall present the draft for review before issue. | CR-05, CR-10 |
| FR-18.3 | The system shall allow an authorized reviewer to edit the draft. | CR-05, CR-10 |
| FR-18.4 | The system shall attribute the issued report to the human approver. | CR-09, CR-10 |

### FR-19 — Configure cameras, zones, schedules and rules

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-19.1 | The system shall allow an administrator to add, update and remove cameras. | CR-08 |
| FR-19.2 | The system shall allow an administrator to draw and update zones on a camera view. | CR-08 |
| FR-19.3 | The system shall allow an administrator to set schedules for zones and rules. | CR-08 |
| FR-19.4 | The system shall allow an administrator to select rule types and rule parameters, including required PPE and minimum distances, for each zone. | CR-08 |
| FR-19.5 | The system shall validate configuration and keep the previous valid configuration when a save fails. | CR-08 |

### FR-20 — Enable or disable safety services

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-20.1 | The system shall allow an administrator to enable or disable each safety service independently. | CR-07, CR-08 |
| FR-20.2 | The system shall stop producing events for a disabled service without affecting other services. | CR-07 |
| FR-20.3 | The system shall record service enable and disable changes in the audit log. | CR-10 |

### FR-21 — Enforce role-based access

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-21.1 | The system shall authenticate every user before granting access. | CR-10 |
| FR-21.2 | The system shall enforce permissions for each function by role. | CR-08, CR-10 |
| FR-21.3 | The system shall deny access to functions not permitted for the user's role. | CR-10 |
| FR-21.4 | The system shall record denied access attempts in the audit log. | CR-10 |

### FR-22 — Maintain audit log

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-22.1 | The system shall record authentication events. | CR-10 |
| FR-22.2 | The system shall record configuration changes with the user and timestamp. | CR-10 |
| FR-22.3 | The system shall record alert decisions, report exports and service changes. | CR-09, CR-10 |
| FR-22.4 | The system shall make audit records available to authorized auditors. | CR-09, CR-10 |

### FR-23 — Redact faces and identities

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-23.1 | The system shall apply redaction before footage is shown to roles without identity access. | CR-10 |
| FR-23.2 | The system shall apply redaction before footage is exported outside authorized roles. | CR-09, CR-10 |
| FR-23.3 | The system shall log access to unredacted footage. | CR-10 |

### FR-24 — Replay demo footage

| **ID** | **Requirement** | **CR** |
|---|---|---|
| FR-24.1 | The system shall provide a replay mode using sample footage. | CR-11 |
| FR-24.2 | The system shall run the full detection-to-report flow in replay mode. | CR-11 |
| FR-24.3 | The system shall reset demo data between runs. | CR-11 |

## 4.3.3 Use Cases

### UC-01 — Respond to a missing-PPE alert

| Use Case ID | UC-01 |
|---|---|
| Use Case Name | Respond to a missing-PPE alert |
| Actors | Security / control-room operator (primary); the system |
| Pre Conditions | A camera is connected and the PPE rule is enabled for the zone. The operator is logged in with permission to handle alerts. |
| Primary Steps | 1. The system processes the camera feed.<br>2. The system detects a person without the required PPE inside the monitored zone.<br>3. The system creates a timestamped event with evidence and shows it in the alert list.<br>4. The operator opens the alert and reviews the snapshot or clip.<br>5. The operator confirms, dismisses or escalates the alert.<br>6. The system records the decision and who made it. |
| Alternate Steps | A1. The detection is wrong: the operator dismisses it and marks it as a false alert.<br>A2. The camera stream drops: the system reconnects and shows the camera as offline until it returns.<br>A3. The violation is serious: the operator escalates it to the safety manager. |
| Business Objective | BR-01 - Convert camera feeds into real-time safety events<br>BR-03 - One central dashboard<br>BR-09 - Humans decide high-consequence actions |

### UC-02 — Generate an audit report

| Use Case ID | UC-02 |
|---|---|
| Use Case Name | Generate an audit report |
| Actors | Safety / operations manager (primary); Auditor / regulator; the AI assistant |
| Pre Conditions | Events are stored for the period. The user has a reporting role. |
| Primary Steps | 1. The manager selects the period and the facility or zone.<br>2. The system computes the risk indicators from stored events.<br>3. The AI assistant drafts the report.<br>4. The manager reviews and edits the draft.<br>5. The system exports the report in a shareable format.<br>6. The system logs the export. |
| Alternate Steps | A1. No events in the period: the report states that none were recorded.<br>A2. The AI assistant is unavailable: the manager generates the standard report without a draft. |
| Business Objective | BR-05 - Facility risk picture and audit reports<br>BR-06 - Agentic AI assistant<br>BR-09 - Humans decide high-consequence actions |

### UC-03 — Configure a hazardous zone

| Use Case ID | UC-03 |
|---|---|
| Use Case Name | Configure a hazardous zone |
| Actors | IT / system administrator (primary) |
| Pre Conditions | A camera is connected. The administrator is logged in with the administrator role. |
| Primary Steps | 1. The administrator selects a camera.<br>2. The administrator draws the zone on the camera view.<br>3. The administrator sets the schedule and the rule type for the zone.<br>4. The administrator saves the configuration.<br>5. The system applies the zone to detection without any code change. |
| Alternate Steps | A1. The zone or schedule is invalid: the system shows the error and keeps the previous configuration. |
| Business Objective | BR-07 - Configuration, not code<br>BR-08 - Adopt any subset of services |

## 4.3.4 Scenarios

### SCN-01 — Missing PPE raises an alert

| Scenario ID | SCN-01 |
|---|---|
| Scenario Name | Missing PPE raises an alert |
| GIVEN | A camera is connected and the PPE rule is enabled for Zone A. |
| WHEN | A person without the required PPE is detected in Zone A. |
| THEN | An event is created within the latency target, with camera, zone, timestamp and evidence, and it appears in the alert list. |
| Business Objective | BR-01 - Convert camera feeds into real-time safety events<br>BR-03 - One central dashboard |

### SCN-02 — Zone intrusion follows the schedule

| Scenario ID | SCN-02 |
|---|---|
| Scenario Name | Zone intrusion follows the schedule |
| GIVEN | Zone B is configured as hazardous with a schedule. |
| WHEN | A person enters Zone B during the scheduled period; and, separately, outside the scheduled period. |
| THEN | An intrusion event is raised during the scheduled period and no event is raised outside it. |
| Business Objective | BR-01 - Convert camera feeds into real-time safety events<br>BR-07 - Configuration, not code |

### SCN-03 — Operator dismisses a false alert

| Scenario ID | SCN-03 |
|---|---|
| Scenario Name | Operator dismisses a false alert |
| GIVEN | An alert is open in the alert list. |
| WHEN | The operator dismisses it as a false alert. |
| THEN | The alert is closed and the decision is logged with the user and the time. |
| Business Objective | BR-09 - Humans decide high-consequence actions<br>BR-10 - Privacy and security |

### SCN-04 — Role restriction

| Scenario ID | SCN-04 |
|---|---|
| Scenario Name | Role restriction |
| GIVEN | A user without the administrator role is logged in. |
| WHEN | The user opens the configuration screen. |
| THEN | Access is denied and the attempt is written to the audit log. |
| Business Objective | BR-10 - Privacy and security |

### SCN-05 — Operator asks the assistant about events

| Scenario ID | SCN-05 |
|---|---|
| Scenario Name | Operator asks the assistant about events |
| GIVEN | Events are stored and the AI assistant is available. |
| WHEN | The operator asks a natural-language question about events in a zone or period. |
| THEN | The assistant answers using stored events and cites the events used. |
| Business Objective | BR-06 - Agentic AI assistant |

## 4.3.5 Traceability Notes

- FR-01 links to CR-06 for existing-camera adoption and CR-08 for source setup.
- FR-04 links to CR-08 because zone schedules change detection behaviour without code changes.
- FR-07, FR-08 and FR-09 link to CR-12, which closes the BR-04 event-stream traceability gap.
- FR-09, FR-15, FR-20 and FR-22 link to CR-10 because human decisions and system changes must be recorded.
- FR-12 and FR-23 remain `Should`; all other high-level requirements are `Must`. Low-level requirements inherit this priority.

## 4.3.6 Checklist

- [x] 24 high-level functional requirements are defined.
- [x] 93 low-level functional requirements are defined.
- [x] Every low-level requirement starts with "The system shall".
- [x] Every low-level requirement links to an existing CR.
- [x] Every high-level requirement links to at least one CR and one BR.
- [x] Use cases and scenarios are retained.

---

[← BRD Index](./README.md) | [Previous: 4.2 Customer Requirements](./04-02-customer-requirements.md) | [Next: 4.4 Non-Functional Requirements →](./04-04-non-functional-requirements.md)
