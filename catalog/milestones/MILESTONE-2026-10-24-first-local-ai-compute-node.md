# MILESTONE — 2026-10-24: First Æsir local AI compute node

**Project:** Æsir Autonomous Systems / NOMAD / Cali-Eye / Portable Cali Core  
**Event date:** 2026-10-24 (local workshop date)  
**Status:** VERIFIED BENCH MILESTONE; further autonomy, voice integration, and GPU work pending  
**Source:** Owner-operated commissioning session, terminal output, hardware diagnostics, and screenshots shared in the dated project conversation. Original screenshots are **not** committed to this repository.

## Why this milestone matters

A discarded Dell OptiPlex 7010 was recovered, commissioned, converted to Linux Mint, and integrated into a working three-computer network. It became the first Æsir node to execute a small delegated archive-processing task and independently generate language-model text using local CPU inference. Separate text-to-speech output was audibly verified. This is a working *foundation* for a future locally controlled collaborator, **not** a demonstration of autonomous agency or a distributed AI model.

## Equipment and baseline observed

| Item | Recorded configuration / observation |
|---|---|
| Worker node | Rescued Dell OptiPlex 7010 |
| CPU | Intel Core i3-3220, 2 cores / 4 threads, 3.30 GHz |
| RAM | 8 GB DDR3-1600, dual-channel |
| Storage | Lite-On LCS-128M6S, nominal 128 GB SATA SSD |
| Operating system | Linux Mint XFCE, installed to internal SSD |
| Network | Built-in wired Ethernet on household LAN; DHCP address observed as 192.168.1.22 during testing |
| Cali-Eye workstation | Lenovo all-in-one running Linux Mint XFCE; LAB Archive mounted locally, approximately 2 TB |
| Command station | Lenovo Windows 11 laptop |
| Local language model | Qwen3 0.6B via Ollama 0.40.11; approximately 522 MB model download |
| Speech synthesizer | eSpeak NG (separate functional test) |
| GPU | **Not installed**; successful language-model response used the OptiPlex CPU |

The display path from the OptiPlex through a DisplayPort-to-HDMI adapter into the Lenovo all-in-one was operational; HDMI-carried audio was also observed. Later graphical access used XRDP from the Windows laptop.

## Verified sequence and acceptance evidence

1. **Firmware / hardware recovery — PASS.** Entered Dell BIOS; cleared a pre-existing administrator password using the labeled PSWD jumper; confirmed password state **Not Set**. Verified memory and SSD detection, SATA AHCI setting, and UEFI boot entry. Dell extended diagnostics completed with all tests passing. The Lite-On SSD's SMART self-test completed without error; this does not establish remaining flash write endurance.
2. **Operating system — PASS.** Booted Linux Mint live from USB, then installed Mint to the internal SSD, replacing the former Windows installation by owner instruction. Subsequently booted Mint from the SSD with the installer USB removed.
3. **Physical and network connectivity — PASS.** Wired Ethernet negotiated a link. The OptiPlex acquired a LAN address and successfully pinged the Cali-Eye workstation.
4. **Authenticated remote administration — PASS.** OpenSSH installed and reported `active`. Verified SSH from Cali-Eye to OptiPlex. Verified a two-hop session **Windows laptop → Cali-Eye → OptiPlex**, with the final remote shell showing the OptiPlex hostname.
5. **Remote graphical session — PASS.** Installed XRDP and XorgXRDP, configured an XFCE session, and verified the full OptiPlex desktop inside Windows Remote Desktop. A conflicting local XFCE login initially caused session termination; logging out locally enabled the successful remote session. Copied the Æsir logo to the OptiPlex for desktop branding.
6. **First delegated worker task — PASS, limited scope.** From the OptiPlex, accessed Cali-Eye's mounted LAB Archive over SSH; saved a manifest of **20 PDF file paths** locally as `pdfs.txt`; verified 20 lines. Performed an `awk | sort | uniq -c` grouping of those 20 paths by parent-directory name. This was metadata/path processing, **not** document text extraction, summarization, or semantic indexing. The source archive was not moved, renamed, or edited.
7. **First locally generated LLM response — PASS.** Installed Ollama and downloaded Qwen3 0.6B. Via SSH, entered an Æsir-themed prompt and observed the model finish text generation and return to the interactive prompt. No discrete GPU was present; this verifies CPU-side local inference. Text displayed as model 'thinking' is generated output, **not** proof of consciousness or privileged knowledge of the host.
8. **First audible synthesized voice — PASS, separate subsystem.** Installed eSpeak NG and audibly heard synthesized speech from the OptiPlex on the Windows laptop over the configured remote desktop audio path. The earlier OptiPlex-to-Lenovo HDMI audio route was also heard. The local LLM's generated replies were **not yet wired into eSpeak**, and microphone-based speech recognition was **not** demonstrated.

## Sample PDF manifest processing results

The 20 paths were grouped by immediate parent directory; these are *folder names*, not verified classifications of document contents.

| Parent directory | Count |
|---|---:|
| DOCUMENTATION | 9 |
| docs | 5 |
| Wiring | 2 |
| html | 1 |
| papers | 1 |
| STM32_Network_Library | 1 |
| Ultimate_Guide_Arduino_Sensors_Modules | 1 |
| **Total** | **20** |

## What is **not** yet proven

- Autonomous librarian operation; arbitrary file access, safe tool selection, scheduled unattended work, and audit logging.
- Document-content extraction, source-grounded summaries, Recoll integration, or independent research retrieval.
- End-to-end voice conversation (speech recognition → local LLM → speech synthesis).
- Model distributed inference across multiple hosts; the established distributed work was **shell access and simple delegated path processing**.
- Persistent agent identity and state migration across machines; offline-disconnected test, MSI GPU/riser compatibility, or GPU acceleration.
- Long-run inference benchmarks, power draw, reliability, or model quality for technical tasks.

## Next verification gates

1. Preserve a reproducible host inventory: `uname -a`, `lscpu`, `free -h`, `lsblk`, `ollama --version`, `ollama list`; exclude credentials or sensitive machine details before publication.
2. Run a documented CPU-only benchmark for model latency/tokens per second and resource usage; repeat after a separately verified MSI GPU/riser installation.
3. Build a small **read-only** librarian worker: retrieve a bounded manifest from Cali-Eye; inspect a small permitted document sample; produce a report with source paths and a verifiable action log; no writes to the original archive.
4. Connect model-generated text to local TTS; only afterward assess offline speech-to-text and microphone input.
5. Test a genuinely disconnected local inference session and the isolated Æsir bench LAN. Keep network exposure narrow and authentication enabled.
6. Demonstrate durable memory/profile handling across a controlled restart and eventually across hosts, before promoting Portable Cali Core beyond concept.

## Engineering interpretation

**Companion engineering-method record:** [2026-10-24 human–AI collaborative systems engineering](MILESTONE-2026-10-24-human-ai-engineering-collaboration.md). This separately documents the owner-led, AI-assisted troubleshooting loop, responsibilities, qualitative productivity observation, and next verification method.


This milestone demonstrates owner-led multidisciplinary **systems integration, hardware recovery, Linux commissioning, networking, remote administration, task delegation, and local AI proof-of-concept validation** on low-cost repurposed hardware. It does not claim invention of a new distributed-computing method, completion of a general AI assistant, or proven commercial viability.

## Portfolio / CV phrasing (bounded to observed results)

**Personal R&D — Æsir Autonomous Systems | Systems Integration / Local AI Lab (2026–present)**

- Recommissioned surplus computing hardware and integrated Windows/Linux systems into a three-node laboratory network, validating chained SSH administration, XFCE remote desktop, Ethernet connectivity, and read-only inter-node archive-manifest processing.
- Deployed and verified CPU-only local LLM inference (Ollama / Qwen3 0.6B) and independent network-delivered text-to-speech on a refurbished OptiPlex 7010; documented diagnostic, acceptance, and next-stage verification gates.

## Provenance and boundaries

- **Direct evidence:** Owner-observed BIOS and diagnostic screens, Linux terminal results, SSH/XRDP sessions, Ollama text-generation screen, and audible eSpeak test reported during the dated October 24, 2026 conversation.
- **Repository evidence:** This entry records observations after the event; original photographs and complete terminal session logs remain outside Git. They must not be described as attached or cryptographically archived.
- **Controlled assets:** The LAB Archive was used for filenames only in this test; no claim is made that an automated agent had unrestricted access or modified source material.
- **Related architecture:** [IDEA-024 Portable Cali Core](../IDEA-024-portable-cali-core.md); [IDEA-026 Cali-Bot V1 voice interface](../IDEA-026-cali-bot-v1-voice-interface.md).

**Keywords:** `VERIFIED` `COMMISSIONING` `LOCAL-AI` `OLLAMA` `QWEN3` `LINUX` `SSH` `XRDP` `TTS` `RECYCLED-HARDWARE` `NOMAD` `CALI-EYE`
