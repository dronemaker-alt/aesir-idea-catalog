# IDEA-017 — Sonobot 5 commercial USV benchmark

- **Captured:** 2026-09-21
- **Status:** INVESTIGATE
- **Source:** https://www.instagram.com/reel/DdgdY6cOoyX/ ; EvoLogics Sonobot 5 product information; screenshot `1000039061.png`
- **Technology tags:** USV, catamaran, hydrography, sonar, differential-thrust, modular-payload, swappable-battery
- **Project tags:** FISK, ISAR, ÆSIR integrated search/recovery
- **Problem tags:** portable-survey-platform, stable-sonar-carrier, field-deployment, endurance, sensor-integration

## Why saved
The Sonobot 5 independently validates the compact twin-hull architecture being considered for FISK: a stable sonar platform with a central electronics/payload bridge, autonomous waypoint operation, redundant communications and single-operator deployment.

This is a commercial benchmark, not a design to clone. Sonobot is primarily an individual professional survey instrument; FISK is intended to become an open, modular and lower-cost member of the larger ÆSIR integrated mission system.

## What to mine
- Foldable or quickly separable cross-structure between pontoons
- Stable catamaran geometry for bathymetry and acoustic search
- Differential electric propulsion and low-speed maneuvering
- Tool-free field assembly and single-person launch/recovery
- Swappable, sealed battery modules
- Protected central avionics and payload bay
- Antenna and GNSS placement above the waterline
- Modular single-beam, multibeam and environmental sensor installation
- Redundant long- and short-range control/data links
- Mission-planning and live survey-data workflow

## Possible applications
- **FISK:** shallow-water survey, sonar logging, environmental sensing and target search
- **ISAR:** rapid pre-dive mapping and evidence gathering
- **NOMAD:** mission planning, shared maps and sensor-data fusion
- **Kraken:** deployment, retrieval, charging and data offload for smaller FISK units
- **UAV/ROV cooperation:** aerial overview followed by surface mapping and submerged-contact inspection

## Benchmark targets to verify
Published configurations indicate approximately:
- Under 32 kg vehicle mass
- About 1.29 m × 0.96 m footprint
- Up to 9–10 hours operation
- Approximately 5 m/s (about 10 kn) maximum speed
- Survey speeds around 0.5–1.5 m/s
- Swappable batteries
- Wi-Fi plus sub-GHz redundant communications
- Single-operator transport and deployment

These figures are reference targets only; confirm the exact configuration and test conditions before using them as requirements.

## Questions / investigation
1. Which performance class does the first FISK demonstrator actually need: pond prototype, inland-water survey unit or deployable ISAR asset?
2. Can readily available kayak/outrigger hulls establish the geometry before fabricating custom pontoons?
3. What is the minimum useful sonar payload for the first mapping demonstration?
4. How should the central bridge separate for transport while preserving alignment and watertight electrical interfaces?
5. Can ArduPilot Rover plus MAVLink supply the first autonomous survey stack?
6. Which functions belong aboard FISK, and which should remain in NOMAD or the ground station?
7. What measurable cost, openness and serviceability advantages will distinguish FISK from professional closed survey systems?

## Outcome
Architecture validated as commercially credible. Retain Sonobot 5 as a performance and packaging benchmark while developing FISK around open interfaces, modular repair, lower acquisition cost and cooperation with the wider ÆSIR fleet.
