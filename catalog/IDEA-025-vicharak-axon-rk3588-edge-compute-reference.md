# IDEA-025 — Vicharak AXON RK3588 edge-compute reference

## Status
**INVESTIGATE**

## Source
- Discovery reel: https://www.instagram.com/reel/DdvsTyEBSKp/
- User screenshots and design conversation: 2026-09-27 CDT
- Manufacturer documentation: https://docs.vicharak.in/vicharak_sbcs/axon/axon-home/
- Manufacturer product page: https://vicharak.in/axon/

## Why saved
The AXON combines an RK3588 application processor, NPU, camera and display interfaces, storage expansion, wired/wireless networking, and general-purpose I/O in a compact board. Its interface density makes it worth retaining as a reference for Cali-Eye vision processing, NOMAD/ground-station edge processing, and a possible secondary Portable Cali host.

This is a candidate/reference, not an approved ÆSIR compute baseline and not a replacement for the hardware-neutral Portable Cali validation sequence.

## Directly evidenced features
Manufacturer documentation identifies:
- Rockchip RK3588 SoC: 4× Cortex-A76 plus 4× Cortex-A55.
- Mali-G610 MP4 GPU and NPU rated up to 6 TOPS.
- Configurations up to 32 GB RAM.
- Multiple MIPI-CSI camera inputs and HDMI input.
- HDMI/DisplayPort/MIPI display outputs.
- M.2/NVMe/PCIe and SATA expansion.
- Gigabit Ethernet, Wi-Fi, Bluetooth, USB, and a 30-pin GPIO header.
- Linux/Ubuntu support.

Exact purchased configuration, sustained inference performance, software maturity, power profile, environmental suitability, and long-term availability are not yet verified.

## Provenance / trust boundary
- **Board designer/vendor:** Vicharak Computers Private Limited, Surat, Gujarat, India. The photographed PCB is marked “Designed in India by Vicharak.”
- **Primary logic-bearing component:** Rockchip RK3588, supplied by Rockchip, China.
- **Wireless and supporting components:** mixed supply chain; exact manufacturers, fabrication/assembly origins, firmware ownership, update paths, and lot traceability remain to be inventoried.
- **Software/firmware:** Vicharak/Rockchip Linux BSP, boot firmware, device tree, NPU runtime and associated binary components require review.
- **US-sourced status:** no; do not treat as satisfying a US-origin architecture requirement.
- **Regulatory/security status:** undetermined. No Covered List, NDAA, export, cybersecurity, or trusted-supply-chain conclusion is asserted by this card.

Apply the repository's logic-bearing-component provenance checklist before trusted, procurement-sensitive, safety-critical, or externally deployed use.

## Potential ÆSIR applications
- Cali-Eye multi-camera inspection and line-laser processing.
- NOMAD or UAV ground-station perception/recording node.
- Bench AI/vision development system.
- Secondary Portable Cali host or dock processor after the hardware-neutral identity/permission/logging test.

## Constraints
- The 6-TOPS Rockchip NPU is not equivalent to an NVIDIA CUDA GPU.
- Accelerated inference depends on compatible drivers, firmware, RKNN conversion and supported operators.
- ARM software compatibility and BSP maintenance must be evaluated.
- Do not select this board merely from headline specifications or the discovery reel.

## Smallest next verification step
Download and freeze the current schematic/pinout/BSP documentation, then build an MPN-level provenance table for the RK3588, wireless module, storage, Ethernet PHY, boot/update chain and NPU runtime. After that desk review, obtain or borrow one board only if it remains competitive and run a single camera → inference → logged-result test representative of Cali-Eye.
