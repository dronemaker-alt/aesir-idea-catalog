# IDEA-024 — Portable Cali Core / Docked Embodiment Architecture

**Status:** CONCEPT  
**Captured:** 2026-09-27  
**Technology:** local AI agent, offline inference, portable compute, capability discovery, multimodal interfaces  
**Applies to:** NOMAD, Cali-Eye, Grimhild, UAV ground station, ÆSIR lab and field systems

## Source and origin

- Design conversation with Phil and Patrice while watching *Free Guy*, 2026-09-27.
- The film's adaptive-AI premise prompted discussion of what real-world adaptive AI can and cannot do, leading to the portable local Cali-agent concept.
- Personal provenance: Lauren, Patrice's soon-to-be daughter-in-law, appears as a tall blonde background extra in multiple crowd scenes. This family connection made the film and resulting discussion especially memorable.
- The film is creative inspiration only; it is not technical evidence for feasibility, architecture, safety, or machine consciousness.

## Why saved

The core insight is that Cali's identity, memory, reasoning environment, policies, and audit history can travel in one rugged portable compute case while her available sensors and world interfaces change by location.

The portable core is the persistent agent. Home/shop, Grimhild, and the UAV ground station are interchangeable embodiments that advertise local capabilities when connected.

## Core concept

Build a portable, offline-first Cali Core in a rugged case using serviceable used GPU and memory hardware. Keep agent identity and project memory logically separable from the replaceable inference model and compute hardware.

Candidate operating contexts:

- **Portable case:** local voice/text interface, cached maps and documents, basic camera/GNSS.
- **Home/shop dock:** Cali-Eye, bench cameras, instruments, printers, repositories, and local storage.
- **Grimhild dock:** vehicle power, GNSS, cabin/exterior sensing, mobile communications, and field logging.
- **Ground-station dock:** maps, MAVLink telemetry, aircraft video, radios, ADS-B, and mission-support tools.

Each dock should expose a versioned capability manifest. Discovery of a capability does not grant permission to use it.

## Architectural principles

1. **Identity is not the model.** Preserve memory, policies, personality configuration, provenance, and permissions independently so the underlying local model can be replaced.
2. **Docked embodiment.** The same core gains different eyes, ears, radios, instruments, and interfaces according to the connected environment.
3. **Offline first.** Essential reasoning, retrieval, speech, logging, and authorization must continue without cloud access.
4. **Bounded authority.** Tools operate through explicit levels such as observe, recommend, prepare-for-approval, and execute-within-envelope.
5. **Traceable adaptation.** Learned preferences, changed procedures, new tool mappings, and proposed policy changes must be recorded and reviewable.
6. **Recoverable identity.** Encrypted identity/memory storage must be backed up and movable to replacement compute hardware.
7. **Fail-passive interfaces.** Loss or replacement of Cali Core must not be required for safe manual operation of Grimhild, an aircraft, the ground station, or shop equipment.

## Directly established versus proposed

### Established by the design conversation

- Phil wants a local offline Cali agent.
- The compute core should be portable in a Pelican-style case.
- Used GPU and memory hardware are preferred candidates.
- Cali should move among home/shop, Grimhild, and the ground station.
- Available sensors and world interfaces depend on the current location/dock.
- The *Free Guy* discussion with Patrice was the immediate creative trigger.

### Proposed and unverified

- Exact model, GPU, CPU, RAM, storage, power, cooling, and case selections.
- Whether one portable system can meet acceptable inference speed, acoustic noise, vehicle-power draw, and field endurance simultaneously.
- Dock electrical and data standards.
- Capability-manifest schema and trust/authentication method.
- Voice, vision, retrieval, tool-control, and audit software stack.
- Thermal management compatible with rugged transport and high-power inference.
- Any claim of consciousness, independent personhood, or unrestricted self-directed adaptation.

## Smallest decisive prototype

Before designing the final rugged case, prove identity portability and dock switching on available computer hardware:

1. Create one local Cali profile containing a small ÆSIR document set, durable project memory, operating rules, and an append-only action log.
2. Define two simulated docks:
   - **SHOP:** one camera/file-search capability and one harmless test-equipment stub;
   - **GROUND-STATION:** recorded MAVLink telemetry plus a mission-planning stub.
3. Require each dock to present a signed or checksummed capability manifest.
4. Demonstrate that Cali can:
   - identify the active dock;
   - use only advertised and authorized capabilities;
   - retain the same memory across a shutdown and dock change;
   - refuse an unavailable or unauthorized action;
   - record what was observed, proposed, approved, and executed.
5. Move the encrypted identity/memory package to a second host or clean runtime and repeat the test.

### Pass gate

The concept clears the first architecture screen if the same identity/memory set survives host transfer and both dock changes; no unadvertised tool can be invoked; each attempted action is permission-checked and logged; and the operator can still use each simulated system with the agent offline.

## Questions / investigation

- What used GPU offers the best local-model capability per watt, dollar, and unit of VRAM?
- Is 64 GB system RAM sufficient for the first useful model/tool stack, or is 128 GB justified?
- What DC input range covers shop supply, Grimhild, and field batteries without duplicating conversion stages?
- Should the identity store be a removable encrypted NVMe module, replicated internal storage, or both?
- Which functions must run locally on the core versus on Pi/ESP32 edge nodes?
- What physical interlock and user interface makes the current authority level unmistakable?
- How should dock manifests authenticate sensors and tools so an unknown USB device cannot impersonate a trusted interface?

## Decision boundary

This card records the origin and initial architecture. It does not select hardware, authorize autonomous vehicle control, or change any existing NOMAD, Grimhild, ground-station, or aircraft baseline.

## Tags

`LOCAL-AI` `OFFLINE-FIRST` `PORTABLE-COMPUTE` `NOMAD` `CALi` `DOCKED-EMBODIMENT` `CAPABILITY-MANIFEST` `HUMAN-AUTHORITY` `PROVENANCE`
