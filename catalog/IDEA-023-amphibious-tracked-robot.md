# IDEA-023 — Amphibious Tracked Robot / Track-as-Propulsor Reference

**Status:** INVESTIGATE  
**Captured:** 2026-09-26  
**Technology:** amphibious UGV, tracked mobility, water propulsion, shoreline transition  
**Applies to:** ÆSIR UGV family, Bayou conversion, Randy USV support systems, NOMAD, Cali-Eye-derived inspection payloads

## Source

- Discovery reel: https://www.instagram.com/reel/DdwIrhOvvgV/
- User-provided screenshot and design discussion, 2026-09-26.
- Reel depicts a compact tracked robot entering a pool; the track shoes/grousers appear unusually deep and paddle-like.

## Why saved

The useful architectural idea is not merely a waterproof tracked vehicle. The visible track geometry suggests a possible dual-use mobility system in which the tracks provide terrestrial traction and also contribute water propulsion. If verified, that can eliminate or reduce separate marine propulsors, shafts, rudders, or waterjets on a small amphibious inspection vehicle.

This is an external reference for investigation, not evidence that the observed machine definitely uses track-only propulsion.

## Core concept

Investigate a compact sealed differential-drive tracked vehicle optimized for the difficult land/water transition. Candidate architecture:

- sealed central electronics/battery hull;
- independently driven left/right tracks;
- high-grouser or paddle-like track geometry;
- low CG with flotation arranged for passive stability;
- bow/track approach geometry intended to climb wet banks and ramps;
- modular top payload interface for cameras, environmental sensors, telemetry, GNSS/RTK, or inspection equipment.

## ÆSIR relevance

### Bayou / UGV work

Preserve the track-as-propulsor principle as a mobility reference for future amphibious UGV modules. It does **not** change the current electric Bayou conversion baseline.

### Randy USV

A smaller amphibious crawler could become a deployable daughter vehicle: USV transports it near shore, crawler enters the water/shore transition zone, performs inspection or sensing, and returns for recovery. This complements rather than replaces the current twin-waterjet direction for the primary USV.

### NOMAD / inspection

The vehicle is a plausible carrier for offline autonomy, mesh communications, and Cali-Eye-derived visual inspection sensors in environments where a wheeled UGV or boat alone cannot reach the target.

## Evidence and hypotheses

### Directly evidenced by the source material

- The depicted machine is a compact tracked robot operating at a pool edge/in water.
- Its visible track shoes have unusually deep, paddle-like grousers.

The source material does **not** establish that the tracks are the only water propulsors, quantify water speed or power, or demonstrate repeated unassisted shoreline exits.

### Hypotheses to test

- **H1 — water propulsion:** At the same commanded track speed, deep-grouser tracks produce materially greater forward water speed than conventional tracks without a disproportionate electrical-power penalty.
- **H2 — shoreline exit:** Deep-grouser tracks increase the probability of an unassisted exit from water onto a repeatable wet ramp.
- **H3 — tradeoff:** Any gain is large enough to justify added current, splash, steering effects, debris retention, and mechanical load.

## Smallest decisive A/B test

Use one small, positively buoyant, two-track differential-drive rig. Change **only** the interchangeable track set:

- **A — control:** conventional low-profile track shoes;
- **B — candidate:** deep paddle/grouser shoes of the same track width, pitch, material, and link count where practical.

Keep the hull, mass, ballast/CG, buoyancy, motors, reduction, battery, controller limits, track tension, software, commanded track speed, ramp, water depth, and start position unchanged. Record actual unloaded track speed for both sets; if geometry changes effective speed, report it rather than compensating silently.

### Test 1 — useful water propulsion

Run each track set in calm water from the same floating start line, with both tracks commanded straight ahead at one fixed setting. Perform at least five valid runs per configuration and alternate A/B order.

Measure:

1. time and distance over a marked water course; report median forward speed and run-to-run spread;
2. battery voltage and total current; report median electrical power and energy per metre;
3. heading change over the course as a basic straight-line/steering-authority check;
4. whether motion is sustained and controllable, rather than a brief launch effect.

**Water-propulsion gate:** B passes only if its median speed is at least **50% greater than A**, every B run completes under control, and B's median energy per metre is no more than **2× A**. If A cannot complete the course, B must complete all five runs and achieve at least **0.15 m/s** median speed. These are screening thresholds, not vehicle requirements.

### Test 2 — repeatable shoreline exit

Use one rigid ramp with a fixed slope and repeatable wet surface. Start floating square to the ramp at a marked distance, apply one fixed straight-ahead command, and allow no manual correction or assistance. Perform ten attempts per track set, alternating A/B; re-wet and inspect the ramp between attempts.

Measure:

1. successful exits out of ten, where the entire rig reaches the dry-side finish mark under its own power;
2. time from first ramp contact to the finish mark;
3. peak current and any controller limit, stall, thrown track, rollover, or high-centering;
4. failure location/mode from fixed-camera video.

**Shoreline-exit gate:** B passes only if it completes at least **8/10** exits and improves on A by at least **3 successful exits**, with no rollover, thrown track, or repeated over-current shutdown. If both configurations score 8/10 or better, the deep grousers have not shown a decisive transition advantage on this rig.

### Decision rule

The concept clears this first screen only if B passes **both** gates. A mixed result remains **INVESTIGATE** and should drive one narrowly targeted follow-up (for example ramp texture, grouser height, or buoyancy/CG), not a larger vehicle build. Failure of both gates rejects this tested geometry, not all possible track-as-propulsor designs.

The primary result is repeatable shoreline transition; maximum swimming speed is secondary.

## Decision boundary

No ÆSIR vehicle baseline changes from this reference. The electric Bayou conversion and Randy USV twin-waterjet direction remain unchanged. Keep IDEA-023 at **INVESTIGATE** through this screening test; any later promotion requires review of the recorded results and a separate decision.

## Tags

`AMPHIBIOUS` `UGV` `USV` `TRACKED-MOBILITY` `WATER-PROPULSION` `SHORE-TRANSITION` `NOMAD` `INSPECTION`
