# IDEA-019 — ARC-TOP Recoverable Water-Column Profiler

**Status:** INVESTIGATE  
**Captured:** 2026-09-23  
**Technology:** recoverable profiler, CTD, pressure hull, ballast release, LoRa/GPS, UAV/USV deployment  
**Applies to:** Randy USV, Sleipnir payloads, Sonarlogger, ÆSIR waterborne systems

## Reference

ARC-TOP (Arctic Research Centre Torpedo), Aarhus University. Open-source recoverable oceanographic profiler intended for UAV deployment and recovery.

- Source reel: https://www.instagram.com/reel/Ddn9MJDiBFs/
- HardwareX paper: https://pmc.ncbi.nlm.nih.gov/articles/PMC9118920/
- Published design/BOM dataset: https://data.mendeley.com/datasets/zdvb5hzv2x

## Why it matters to ÆSIR

ARC-TOP is a useful reference architecture for a reusable deployable sensor node rather than an expendable probe. Its mission sequence maps well onto the emerging ÆSIR air/water ecosystem:

1. Carrier deploys profiler.
2. Profiler descends under ballast.
3. Sensors collect a vertical water-column profile.
4. Ballast is released at commanded depth.
5. Positive buoyancy returns the profiler to the surface.
6. GPS/radio support reacquisition.
7. Carrier recovers the profiler.

The concept can be adapted so Randy's USV is the primary deploy/recovery carrier while Sleipnir-class UAVs remain a possible aerial deployment/recovery path.

## Design elements to study

- pressure-hull construction and sealing
- ballast-release mechanism
- positive-buoyancy recovery strategy
- deployable pickup arms / recovery geometry
- CTD and pressure-sensor integration
- state-machine logic
- SD-card mission logging
- GPS + LoRa surface communications
- FDM-printable wet-side components
- carrier/profiler mechanical interface

## ÆSIR direction

Do **not** treat ARC-TOP as a straight clone. Extract the reusable architecture into an ÆSIR modular water-column payload with interchangeable sensor packages.

Candidate payloads include:

- CTD / temperature-depth profiling
- turbidity
- dissolved oxygen
- hydrophone/acoustic sensing
- sonar/environmental instrumentation

Cross-link this concept with Randy USV, Sonarlogger, and Sleipnir payload development.

## Follow-up

Preserve the published design package locally and inspect the BOM, CAD, electronics, firmware/state machine, release mechanism, and recovery hardware. Compare the original free-floating profiler with Aarhus University's later UAV winch-profiler work to capture the lessons learned around currents, recovery, and redeployment.
