# Problem Context — Existing Solutions & Their Limitations

## 2.1 Context

Factories and warehouses in Egypt and the wider MENA region typically operate safety and security through two disconnected systems:

- **Security** is passive CCTV, reviewed reactively after an incident.
- **Safety** is manual inspection, paper logs, and spreadsheets maintained by supervisors who cannot watch every zone, every shift.

The people affected are not only facility owners. Workers bear the physical risk; safety officers carry the detection and reporting burden; managers lack a reliable picture of site risk; and auditors, insurers, and regulators receive incomplete or inconsistent evidence.

## 2.2 The operational problem (motivation for our project)

| Problem | Current reality | Consequence |
|---|---|---|
| **Reactive monitoring** | Footage is reviewed after an event, if at all | Delayed response; violations become incidents |
| **Fragmented visibility** | Cameras, safety logs, and access control do not communicate | No unified view of which zone, shift, or crew is deteriorating |
| **Weak evidence** | Manual notes and disconnected clips | Audits, insurance claims, and regulatory reports are slow and contestable |
| **Manual monitoring does not scale** | One supervisor cannot continuously watch many cameras | Blind spots, fatigue, inconsistent enforcement |
| **Alert fatigue** | Naive systems fire on every frame or low-confidence detection | Operators stop trusting the system and ignore real alerts |

## 2.3 Why existing approaches fall short

- **Traditional CCTV is passive.** It records what happened but does not convert observations into structured, actionable events.
- **Commercial AI platforms are closed and expensive.** Protex AI, Voxel, viAct, and Intenseye demonstrate that the capability is real, but their architectures, models, and scoring formulas are not published; they are priced and packaged for larger enterprises, and they are not designed as a generic, configurable, education-grade platform.
- **Hardware-centric alternatives shift the cost.** Thermal cameras, RFID/UWB/BLE tags, and wearable sensors add per-worker hardware, installation, and compliance burden — precisely what small and mid-sized facilities cannot absorb.
- **Isolated computer-vision prototypes do not become operational systems.** A detector that draws boxes on a video is not a safety product. The missing work is the rules layer, the event contract, the dashboard, the evidence trail, and the ability to configure a new site without rewriting code.
- **Generic models do not transfer for free.** Lighting, camera angle, occlusion, PPE, and site layout vary; without validation and configuration, accuracy claims do not survive real conditions.
- **Camera-only systems are honest about their limits.** Occlusion, blind spots, and 2D geometry mean a credible system must report uncertainty and coverage gaps rather than imply complete observation.
