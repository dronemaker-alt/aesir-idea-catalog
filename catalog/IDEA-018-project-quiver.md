# IDEA-018 — Project Quiver open-source heavy-lift UAV reference

- **Captured:** 2026-09-22
- **Status:** INVESTIGATE
- **Source:** https://github.com/Arrow-air/project-quiver ; Instagram discovery: https://www.instagram.com/reel/DdmmXmGyMnO/
- **Technology tags:** open-source UAV, heavy-lift, modular payloads, hot-swap interfaces, distributed architecture, BOM, manufacturing documentation
- **Project tags:** Sleipnir, Jotun, ÆSIR UAV family, NOMAD
- **Problem tags:** payload modularity, serviceability, scalable airframe, open reference architecture, build documentation

## Why saved
Project Quiver is unusually close to several ÆSIR design goals: an open-source heavy-lift multirotor, approximately 25 kg MTOW with a stated 5–8 kg payload range, modular/hot-swappable attachment interfaces, and a repository that treats CAD, BOM, manufacturing data and software as a coherent system rather than a collection of loose files.

This is not merely visual inspiration. It is a useful reference implementation to compare against the existing ÆSIR modular airframe philosophy and Sleipnir/Jotun development.

## What to mine
- Mechanical layout and structural load paths.
- Payload attachment and hot-swap interface geometry.
- Separation of primary structure from payload/equipment mounting.
- Power distribution, harness architecture and connector choices.
- Flight-controller, companion-computer and distributed-node architecture.
- CAD organization and part-number/BOM discipline.
- Machine-readable BOM workflow and validation against CAD.
- Manufacturing documentation, assembly instructions and release/version practices.
- Test procedures and issue/PR history for failure modes and design evolution.
- Patterns that can be adapted to ÆSIR without blindly copying Quiver-specific assumptions.

## Possible applications
- **Sleipnir:** heavy-lift reference and payload-interface benchmark.
- **Jotun:** modular equipment-stack and serviceability ideas.
- **ÆSIR family:** common payload/data/power interface standards.
- **NOMAD:** companion-computer and vehicle/ground-system integration patterns.
- **Decision/Development Log:** external prior-art/reference evidence for architectural decisions.

## Questions / investigation
1. What is the exact attachment-interface mechanical/electrical specification?
2. Which portions are mature flight-tested hardware versus development targets?
3. How is power isolated and protected across payload interfaces?
4. What data buses are exposed to payloads and how are nodes discovered/configured?
5. Which Quiver structural choices scale down cleanly to ÆSIR frames?
6. What licensing obligations apply to CAD, software, documentation and derivative hardware?
7. Which BOM/CI/documentation practices should ÆSIR adopt directly as process improvements?
8. Compare Quiver's architecture against the frozen ÆSIR U-channel-spine + printed-station baseline before changing any structural decisions.

## Outcome
Reference captured for structured teardown/comparison. No ÆSIR baseline change yet.
