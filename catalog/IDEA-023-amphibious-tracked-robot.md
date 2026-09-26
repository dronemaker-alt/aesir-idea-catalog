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

## First prototype hypothesis

Do not scale immediately to a full vehicle. Build a small inexpensive test article with two independent tracks, a sealed electronics enclosure, and interchangeable grouser/paddle geometries.

Compare conventional and paddle-track configurations for:

1. water speed and steering authority;
2. electrical power/current at equal commanded track speed;
3. static and dynamic stability;
4. ability to enter and exit water over a wet ramp;
5. mud/debris retention and track shedding;
6. propulsion performance versus grouser height, pitch, and track velocity.

The key success metric is **reliable shoreline transition**, not maximum swimming speed.

## Decision boundary

No ÆSIR vehicle baseline changes from this reference. Promote from **INVESTIGATE** only after the reel's propulsion method is verified or an ÆSIR bench model independently demonstrates useful track-driven water propulsion and repeatable water exit.

## Tags

`AMPHIBIOUS` `UGV` `USV` `TRACKED-MOBILITY` `WATER-PROPULSION` `SHORE-TRANSITION` `NOMAD` `INSPECTION`
