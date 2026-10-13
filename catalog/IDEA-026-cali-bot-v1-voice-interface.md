# IDEA-026 — Cali-Bot V1 / Cali-Quad voice interface integration

**Status:** INVESTIGATE  
**Parent asset:** Cali-Bot V1 (Cali-Quad), existing Æsir Autonomous Systems robotics inventory  
**Recorded:** 2026-10-13 (CDT)  
**Scope:** Add a local voice endpoint investigation to the existing robot; do not create a new robot project or change the motion-control baseline.

## Original design intent and observed evidence

The owner acquired an inexpensive Chinese quadruped as a prospective mobile embodiment for a voice assistant, and fitted a spherical Amazon Echo into a robot-shaped cradle. This predates the present EchoMuse discovery; the Echo is not merely a decorative accessory.

On 2026-10-13, the owner supplied three conversation photographs: (1) the label of a fabric-covered Echo puck, showing model C78MP8; (2) a second puck label, tentatively read as B7W64E, to be confirmed from a sharper image; (3) the robot cradle with spherical Echo installed. The original image binaries are conversation attachments **not committed here**. Preserve them unchanged with timestamps and hashes if later added to the evidence repository. The owner reports three Echo pucks plus one spherical Echo in inventory. Exact sphere generation and quadruped controller/actuator details are not yet established in this evidence set.

## Candidate architecture (not yet demonstrated)

Echo hardware (microphones / speaker) → local speech/wake-word interface → Portable Cali Core / NOMAD (AI, memory, permissions) → authorized quadruped motion commands and feedback.

[EchoMuse discovery reel](https://www.instagram.com/reel/DeU_t32DJOx/) inspired investigation of repurposing compatible Echo hardware. **Do not assume EchoMuse supports the spherical Echo or all puck generations.** Confirm its documented hardware matrix, firmware flashing method, recoverability, and actual local audio path before attempting integration. Alternative audio endpoints remain acceptable.

## Verification gates

1. Record exact model numbers and power requirements for all four Echo devices; determine which, if any, is supported by a documented local firmware path.
2. Inventory Cali-Quad's installed controller, actuators, power system, interfaces, and current working functions. Do not infer a particular ESP32/PCA9685 implementation without inspection.
3. Demonstrate microphone → local transcription → response → speaker on one supported endpoint, with network dependencies documented.
4. Demonstrate an explicitly authorized, bounded command path from Cali Core to the robot controller with status feedback, independent motion inhibit, and logs.
5. Preserve the original photographs, source reel, firmware versions, bench observations, and hashes in the project evidence archive.

**Current outcome:** existing hardware and intent documented; local voice operation, EchoMuse compatibility, autonomous behavior, and motion-control integration **unverified**.
