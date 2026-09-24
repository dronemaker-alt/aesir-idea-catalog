# Idea Index

| ID | Idea | Technology | Applies to | Status |
|---|---|---|---|---|
| IDEA-001 | OpenArm open-source robot architecture | manipulation, ROS, actuators | Cali-Spider, UGV, ROV | INVESTIGATE |
| IDEA-002 | Enclosed XY gantry inspection architecture | motion-control, machine-vision | Cali-Eye | INVESTIGATE |
| IDEA-003 | ESP32 battery telemetry dashboard | power, telemetry, web-UI | UAV, USV, UGV, bench | INVESTIGATE |
| IDEA-004 | Mobile carrier / mothership architecture | deployment, autonomy | integrated SAR, UGV | RAW |
| IDEA-005 | Precious Plastic recycling cell | recycling, fabrication | e-waste, outreach, lab | INVESTIGATE |
| IDEA-006 | Low-cost plastic shredder prototype | recycling, fabrication | outreach, proof-of-concept | RAW |
| IDEA-007 | Articulated Horus / animatronic head | mechanisms, HMI | lab interface, Cali terminal | RAW |
| IDEA-008 | Modular drone electronics-stack construction | structures, serviceability | ÆSIR UAV family | RAW |
| IDEA-009 | Legacy radio battery modernization | power, reverse-engineering | lab, field equipment | RAW |
| IDEA-010 | Fiber-linked carrier-to-deployed-vehicle architecture | comms, deployment | UGV/USV integrated systems | INVESTIGATE |
| IDEA-011 | Sonar logging / mapping workflow | sensing, mapping | USV/ROV, ISAR | INVESTIGATE |
| IDEA-012 | CAN telemetry/display architecture | CAN, diagnostics | UAV, UGV, USV, service tools | INVESTIGATE |
| IDEA-013 | OASIS/UROS HUMS-like monitoring concept | health-monitoring, diagnostics | fleet-wide ÆSIR systems | INVESTIGATE |
| IDEA-014 | BeagleBone-class embedded controller | embedded Linux, I/O | robotics, test equipment | RAW |
| IDEA-015 | Encoder feedback for mechanisms | sensing, motion-control | Cali-Eye rotary stage, robotics | INCORPORATED |
| IDEA-016 | Modular U-channel spine + printed stations | structures, fabrication | ÆSIR airframes | INCORPORATED |
| IDEA-017 | Sonobot 5 commercial USV benchmark | hydrography, sonar, modular USV | FISK, ISAR, integrated fleet | INVESTIGATE |
| IDEA-018 | Project Quiver open-source heavy-lift UAV reference | heavy-lift UAV, modular payloads, open hardware | Sleipnir, Jotun, ÆSIR UAV family | INVESTIGATE |
| IDEA-019 | ARC-TOP recoverable water-column profiler | CTD, recoverable profiler, UAV/USV payload | Randy USV, Sleipnir, Sonarlogger | INVESTIGATE |
| IDEA-020 | Handheld UAV commissioning & diagnostic terminal / transmitter backpack | RC, diagnostics, MAVLink, ELRS, retrofit HMI | field diagnostics, NOMAD, experimental transmitters | INVESTIGATE |\n| IDEA-021 | DJI air-link characterization / ÆSIR COMSEC bench | RF characterization, protocol analysis, telemetry security | DJI test articles, transmitter backpack, VTX/FPV service tool, NOMAD | INVESTIGATE |

Individual cards can be added as investigation progresses. This index is deliberately cross-project: the same technology may solve problems in several systems.

## Provenance / Decision Log

### 2026-09-23

Project Quiver was authored late on 2026-09-22 CDT and committed on 2026-09-23 UTC. The ARC-TOP and IDEA-020 entries were authored and committed on 2026-09-23 CDT. Each entry below records a reference for investigation; none of these commits, by itself, changes a frozen ÆSIR hardware baseline.

| Idea / decision | Repository evidence | Source evidence | Affected ÆSIR projects | Current status | Next verification step |
|---|---|---|---|---|---|
| [IDEA-018 — Project Quiver](IDEA-018-project-quiver.md): retain as external prior art for modular heavy-lift architecture, payload interfaces, and release/documentation practice; do not replace the frozen U-channel-spine baseline without comparison evidence. | [Add reference card](https://github.com/dronemaker-alt/aesir-idea-catalog/commit/8aea6865e9601cf3c3daa065c47474d49258e2a3); [index entry](https://github.com/dronemaker-alt/aesir-idea-catalog/commit/2233f362f202721f84570dd494dd902fb529ea36) | [Project Quiver repository](https://github.com/Arrow-air/project-quiver); [discovery reel](https://www.instagram.com/reel/DdmmXmGyMnO/) | Sleipnir; Jotun; ÆSIR UAV family; NOMAD | **INVESTIGATE** — reference captured; no ÆSIR baseline change. | Freeze the upstream revision examined, then verify flight-tested maturity, licenses, payload mechanical/electrical interfaces, power protection, and data buses against the ÆSIR spine baseline. |
| [IDEA-019 — ARC-TOP](idea-019-arc-top-recoverable-profiler.md): mine the reusable deploy–profile–surface–recover architecture as a modular water-column payload, not a straight clone. | [Add reference card](https://github.com/dronemaker-alt/aesir-idea-catalog/commit/0b6ca3d80ea010e8b1e8b2f40d4cdd5316a08934); [index entry](https://github.com/dronemaker-alt/aesir-idea-catalog/commit/bd5e5793f039398b28a728bcd18ed8e910dc9ce3) | [Discovery reel](https://www.instagram.com/reel/Ddn9MJDiBFs/); [HardwareX paper](https://pmc.ncbi.nlm.nih.gov/articles/PMC9118920/); [published design/BOM dataset](https://data.mendeley.com/datasets/zdvb5hzv2x) | Randy USV; Sleipnir payloads; Sonarlogger; ÆSIR waterborne systems | **INVESTIGATE** — open reference and mission pattern captured; adaptation unverified. | Preserve a versioned copy of the design package and inspect its BOM, CAD, electronics, state machine, release mechanism, pressure housing, and recovery geometry; compare the later Aarhus winch-profiler work before selecting a carrier interface. |
| [IDEA-020 — Transmitter diagnostic backpack](IDEA-020-handheld-uav-commissioning-diagnostic-terminal.md): prototype a reversible external service module before considering a new integrated transmitter; prove one complete diagnostic path before expanding protocol coverage. | [Add reference card](https://github.com/dronemaker-alt/aesir-idea-catalog/commit/947fd0f89a1e6e6ac97661c8fee50a209d63697b); [index entry](https://github.com/dronemaker-alt/aesir-idea-catalog/commit/011d59b10e5065f1c423d795b5a408a2681f6f3e) | [Discovery reel](https://www.instagram.com/reel/Ddj8XmjCU-k/); user screenshot and design conversation, 2026-09-23 | ÆSIR field diagnostics; NOMAD; VTX/FPV service tool; experimental transmitters, including DJI candidates | **INVESTIGATE** — architecture direction selected; host interfaces and controllable functions not yet characterized. | Inventory each available transmitter's external module-bay, trainer, USB, UART, telemetry, and documented accessory/API paths; select one non-invasive host and demonstrate detect → diagnose → verify → record end to end. |
