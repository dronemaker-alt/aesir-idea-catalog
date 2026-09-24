# IDEA-021 — DJI Air-Link Characterization / ÆSIR COMSEC Bench

**Status:** INVESTIGATE  
**Captured:** 2026-09-23  
**Technology:** RF characterization, protocol analysis, telemetry security, synchronized instrumentation

## Why saved

A MAVLink/Wireshark telemetry-capture demonstration prompted the question whether the same investigative process can be applied to DJI links. The useful ÆSIR objective is not to begin by defeating a proprietary/encrypted air link, but to map the communications architecture of ÆSIR-owned DJI test articles by correlating RF activity, accessible endpoint/bus traffic, known operator inputs, and vehicle responses.

This extends the existing transmitter-diagnostic-backpack and VTX/FPV service-tool concepts into a repeatable communications-security bench.

## Candidate test articles

- DJI Mini / Mini 2 damaged or sacrificial aircraft
- Mavic Air
- Available DJI controllers/transmitters
- SDR receiver(s)
- Logic analyzer / oscilloscope
- Transmitter diagnostic backpack hardware as it develops

## Initial investigation sequence

1. Characterize RF behavior during power-up, pairing, idle, video streaming, telemetry changes, and controlled stick/gimbal inputs.
2. Instrument accessible endpoints and internal buses on owned/sacrificial hardware.
3. Maintain a synchronized event log: operator action → internal traffic → RF event → aircraft response.
4. Change one variable at a time and repeat captures to identify traffic classes and timing relationships.
5. Record what can be observed externally versus what requires endpoint access.
6. Feed useful interfaces and measurements back into IDEA-020 and the VTX/FPV service-tool architecture.

## Verification goal

Produce a documented DJI communications map sufficient to identify observable RF characteristics, accessible host interfaces, useful diagnostic points, and defensible trust boundaries without assuming protocol contents are readable.

## Source evidence

- Discovery reel: https://www.instagram.com/reel/Ddjl7u_tung/
- User screenshots and design discussion, 2026-09-23.

## Related ÆSIR work

- IDEA-020 transmitter diagnostic backpack
- VTX/FPV service tool
- NOMAD
- MAVLink command-security testing
- DJI repair/test fleet

## Next verification step

Select one DJI aircraft/controller pair and establish a baseline capture set for power-up, pairing, idle, video, and one controlled input while recording synchronized RF and endpoint observations.
