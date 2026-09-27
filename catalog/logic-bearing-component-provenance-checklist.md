# Logic-Bearing Component Provenance Checklist

**Adopted:** 2026-09-27  
**Applies to:** all ÆSIR avionics BOM items that can execute code, store or transform mission data, communicate, navigate, sense, or accept updates.  
**Source decision:** [FCC logic-bearing component provenance requirement](https://github.com/dronemaker-alt/aesir-idea-catalog/commit/8c579d263766ef9a41ff72d5b71e976351ec66ad)

This is an engineering traceability screen, not a declaration that a part is compliant. A blank supplier claim is not evidence. “Not applicable” requires a reason.

## Reusable record

Copy one record per orderable component and per separately updateable module.

| Field | Required entry |
|---|---|
| BOM / assembly revision | Revision, date, owner, repository commit |
| Function and scrutiny class | Communications; navigation/timing; firmware execution/storage; update path; sensing/data; other |
| Manufacturer and exact legal entity | Name supported by manufacturer documentation |
| Exact manufacturer part number | Include package, memory, temperature, and silicon revision where relevant |
| Board/module supplier and seller | Distinguish designer, manufacturer, distributor, and marketplace seller |
| Country evidence | Country of wafer fabrication, assembly, test, module/board manufacture, and firmware origin when available; record **unknown** separately |
| Lot trace | Date/lot code, label photographs, invoice/packing record, chain of custody |
| Datasheet/design evidence | Manufacturer URL, document number/revision, schematic symbol and BOM line |
| Communications capability | Physical interfaces, RF capability, network reachability, protocols actually enabled, external radios/modems connected |
| Navigation/timing role | GNSS receiver, magnetometer, barometer, IMU, time source, or **none verified** |
| Executable/storage surfaces | MCU/FPGA/secure element, internal/external flash, EEPROM, SD/eMMC, option bytes/OTP, boot ROM |
| Firmware identity | Project, upstream source, version/tag, source commit, build configuration/toolchain, binary hash |
| Boot/update path | Boot ROM, USB/UART/SWD/JTAG/CAN/network/SD path, physical access, recovery method, who can authorize |
| Trust controls | Signature/encryption/rollback/debug-lock capability and the configuration actually verified |
| FCC Covered List evidence | Dated FCC list/FAQ/order checked; exact-name search; category applicability; result and reviewer |
| NDAA/contract evidence | Specific clause/program requirement and supplier declaration or primary evidence; do not treat FCC and NDAA as interchangeable |
| Disposition | **VERIFIED**, **PARTIAL**, **MISSING EVIDENCE**, **NOT APPLICABLE — reason**, or **REJECTED** |
| Smallest next verification | One bounded action that can change the disposition; owner/evidence destination |

## Review sequence

1. Freeze the assembly revision and photograph every marked logic-bearing part.
2. Reconcile markings to the schematic and orderable BOM; never infer a fitted part from a generic product page.
3. Map every executable store, communications/navigation interface, and update route.
4. Preserve manufacturer documents, supplier records, firmware source/build identity, and hashes.
5. Check the current FCC Covered List and UAS FAQ by exact legal entity and applicable component category; record the date and result.
6. Check any program-specific NDAA or procurement clause separately.
7. Close only the rows supported by retained evidence. Unknown country or firmware origin remains **MISSING EVIDENCE**.

## First application — RP2350 flight-controller BOM

**Baseline state:** concept/reference-controller BOM not present in this repository as of 2026-09-27. Only the RP2350 family and planned FC role are evidenced by the source decision. Rows below are the minimum logic-bearing roles to reconcile against the actual schematic/BOM; candidate devices are not selections.

| Component / role | Class | Verified facts | Missing evidence | Disposition | Smallest next verification |
|---|---|---|---|---|---|
| RP2350-family main MCU | Firmware; communications interfaces; update-capable | Raspberry Pi documents RP2350-family devices with boot ROM and serial boot/update capability; exact fitted suffix is not recorded here. The MCU has no inherent RF transmitter. | Exact suffix/package/revision; manufacturer entity and production/assembly/test origins; supplier/lot; enabled interfaces; firmware/build/hash; boot-security and debug configuration; dated FCC/NDAA screen | **PARTIAL** | Photograph the chip marking or freeze the schematic BOM line, then attach the exact manufacturer datasheet for that suffix. |
| Nonvolatile program store | Firmware storage; update-capable | RP2350A/B require external QSPI program storage; RP2354 variants may contain stacked flash. The selected architecture is not recorded. | Exact topology and MPN; flash manufacturer/origin/lot; write protection; stored bootloader/application identity; update/recovery path | **MISSING EVIDENCE** | Inspect the RP2350 BOM/schematic and record whether the design uses RP2350 + external QSPI or RP2354; capture the exact flash BOM line. |
| Flight firmware / boot configuration | Firmware; update-capable | A flight-controller role necessarily requires application firmware; no project, version, build, or policy is committed here. | Firmware project and source commit; reproducible build/toolchain; binary hash; signing/rollback/debug policy; authorized update procedure | **MISSING EVIDENCE** | Name the intended firmware target and archive one build manifest containing source commit, toolchain, configuration, and SHA-256. |
| Wired communications and service interfaces | Communications; update-capable | RP2350-family documentation exposes USB, UART, SPI and I2C-class interfaces; presence does not prove routing or use on the FC. | Which interfaces are routed; connector/pin map; attached devices/protocols; which can update firmware; physical/debug access controls | **PARTIAL** | Mark the schematic net/connector for each routed MCU communications interface and label it mission, service/update, or unused. |
| External RC/telemetry/Remote ID/RF module(s) | Communications; firmware/update-capable | The provenance decision names ELRS and other RF modules, telemetry, and Remote ID as in scope; none is identified in an RP2350 BOM here. | Presence, MPN, FCC ID/authorization, manufacturer/origin, firmware/update route, frequencies/protocols, Covered List/NDAA evidence | **MISSING EVIDENCE** | Select or identify the first attached RF module and preserve its label/FCC ID plus exact BOM line; do not screen a generic module family. |
| GNSS receiver | Navigation/timing; communications; firmware-capable where applicable | GNSS is named in the adopted scope; no receiver is identified for this controller. | Presence/MPN; manufacturer/origin; constellations/bands; firmware and updateability; correction/data ports; spoof/jam features; FCC/NDAA screen | **MISSING EVIDENCE** | Identify the intended GNSS module by exact MPN and archive its manufacturer datasheet and firmware/update statement. |
| Magnetometer / IMU / barometer | Navigation/sensing; possible embedded firmware | These roles are typical FC inputs, but no fitted devices are evidenced in this repository. | Exact devices; on-board versus external location; manufacturer/origin/lot; embedded firmware or trim storage; interfaces and updateability | **MISSING EVIDENCE** | Export the sensor lines from the actual BOM and photograph the fitted markings on the prototype, if one exists. |
| Other programmable coprocessor, FPGA, secure element, OSD, data logger or removable storage | Firmware/data; communications/update-capable as fitted | No such parts are recorded. Absence from this table is not proof of absence from the design. | Complete inventory and trust/update paths | **MISSING EVIDENCE** | Run a schematic/BOM search for MCU, FPGA, flash, EEPROM, secure element, OSD, SD/eMMC and add one row per hit. |

## First application — H743 flight-controller BOM

**Baseline state:** inventory establishes an H743 flight controller exists, but its board make/model, schematic, BOM, markings, and firmware identity are not present in this repository as of 2026-09-27. Therefore only the MCU family can be screened provisionally.

| Component / role | Class | Verified facts | Missing evidence | Disposition | Smallest next verification |
|---|---|---|---|---|---|
| STM32H743-family main MCU | Firmware; communications interfaces; update-capable | ST documents STM32H743 devices with internal flash, system-memory bootloader, and multiple wired communications peripherals. Exact fitted suffix/revision and enabled board interfaces are not recorded. The MCU has no inherent RF transmitter. | Board/model; exact MCU MPN/revision; manufacturer and origin evidence; supplier/lot; enabled interfaces; firmware/build/hash; option-byte/readout/debug configuration; dated FCC/NDAA screen | **PARTIAL** | Photograph both sides of the H743 board at readable resolution and transcribe the MCU top marking and board identifier. |
| Internal MCU flash / boot configuration | Firmware storage; update-capable | H743-family parts provide internal flash and an ST-programmed system bootloader; actual board/application configuration is unknown. | Boot pins and exposed update ports; bootloader path used; application/bootloader partitions; option bytes; readout protection; signing/rollback policy | **PARTIAL** | Connect non-destructively with the documented service method and save an option-byte/update-path report without changing settings. |
| Flight firmware | Firmware; update-capable | The board is intended as a flight controller; no firmware family or binary identity is evidenced. | ArduPilot/Betaflight/INAV/other target; board target; version/source commit; build config/toolchain; binary hash; updater and recovery method | **MISSING EVIDENCE** | Power the board and capture its reported target/version over its normal configurator or console; archive the output before any update. |
| Board USB/UART/CAN and debug/service interfaces | Communications; update-capable | The H743 family supports numerous communications peripherals, but a peripheral in the MCU datasheet is not proof that the board routes it. | Board connector/pin map; routed interfaces; attached protocols/devices; SWD/JTAG exposure; update-capable ports and access controls | **MISSING EVIDENCE** | Identify the exact board/model, obtain its pinout/manual, and reconcile every exposed connector to the MCU/interface. |
| External RC/telemetry/Remote ID/RF module(s) | Communications; firmware/update-capable | No RF module is identified; the H743 MCU itself is not an RF radio. | Attached modules, FCC IDs/authorizations, manufacturer/origin, firmware/update route, bands/protocols, Covered List/NDAA evidence | **MISSING EVIDENCE** | Photograph and inventory the actual connected receiver, telemetry, video/control link, and Remote ID modules by exact label. |
| GNSS receiver | Navigation/timing; communications; firmware-capable where applicable | No GNSS module is identified. | Same evidence set as the RP2350 application | **MISSING EVIDENCE** | Record the exact GNSS module connected or planned for this H743 board and archive its label and datasheet. |
| On-board/external magnetometer, IMU and barometer | Navigation/sensing; possible embedded firmware | No exact sensor is evidenced; generic H743 board listings are not acceptable substitutes. | Exact MPNs and markings; count/redundancy; manufacturer/origin; interfaces; embedded firmware/updateability | **MISSING EVIDENCE** | Use the board identifier to obtain its schematic/BOM, then confirm each sensor against physical markings. |
| On-board flash/EEPROM/OSD/data logger/removable storage/secondary MCU | Firmware/data; possible communications/update path | Common FC implementations may use these parts, but none is verified on this board. | Presence, MPN, origin, contents, write/update routes, trust boundary | **MISSING EVIDENCE** | Photograph both sides and reconcile every logic/storage IC with a schematic or manufacturer board BOM. |

## Primary-source anchors

- [FCC Covered List](https://www.fcc.gov/supplychain/coveredlist)
- [FCC UAS and UAS Critical Components FAQ](https://www.fcc.gov/covered-list-faqs-uas-and-uas-critical-components)
- [FCC DA 25-1086](https://docs.fcc.gov/public/attachments/DA-25-1086A1.pdf)
- [Raspberry Pi RP2350 datasheet](https://pip.raspberrypi.com/documents/RP-008373-DS-rp2350-datasheet.pdf)
- [Raspberry Pi hardware design with RP2350](https://pip.raspberrypi.com/documents/RP-008280-DS-hardware-design-with-rp2350.pdf)
- [ST STM32H743 product/datasheet page](https://www.st.com/en/microcontrollers-microprocessors/stm32h743-753.html)
- [ST AN2606 system-memory boot mode](https://www.st.com/resource/en/application_note/an2606-stm32-microcontroller-system-memory-boot-mode-stmicroelectronics.pdf)

## Traceability rule

A component remains **MISSING EVIDENCE** until the evidence belongs to the exact fitted part and frozen assembly revision. Capability stated in a silicon datasheet is not proof that the board routes or enables it; a supplier or marketplace country label is not proof of wafer, package, board, or firmware origin; and FCC Covered List review does not substitute for contract-specific NDAA review.
