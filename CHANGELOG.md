# Changelog

## 2026-11-22 — Hardware documentation cleanup v1.8

- Removed the redundant Quick specifications table from the hardware landing page; the full inventory is the single specification reference.
- Rewrote hardware descriptions in my first-person voice and removed third-party attribution wording.
- Updated selected network notes to use the same voice without changing historical test statuses or claiming new verification.
- Documentation only; no live configurations were changed.

## 2026-11-22 — PBS throughput unit clarification v1.7

- Corrected the documented PBS backup transfer limit from 60 MB/s to **60 MiB/s** (approximately 62.9 MB/s); no configuration change was performed.

## 2026-11-22 — PBS disk model and backup throughput note v1.6

- Identified the primary PBS storage as two 6 TB WD Red HDDs in RAID1.
- Documented my selected approximate 60 MiB/s routine backup transfer limit to reduce sustained HDD workload, without implying that it is the drives' rated speed or that it guarantees longevity.
- Updated the detailed hardware inventory and quick-reference table. No device configuration was changed.

## 2026-11-22 — Wi-Fi sensor hardware clarification v1.5

- Identified the Wi-Fi sensor's SSD as a Samsung 970 EVO M.2 NVMe drive.
- Recorded the wireless adapter model as Alfa AWUS036AXML.
- Kept OS installation and monitoring deployment status separate from the confirmed hardware inventory.

## 2026-11-22 — Workstation CPU and inventory presentation v1.4

- Confirmed the Daily workstation CPU as AMD Ryzen 9 9950X.
- Matched the AI Node 02 platform table styling to AI Node 01 using bold Intel CPU and ASUS TUF Z390 motherboard fields.
- Clarified the isolated HP ProDesk test node's 2 TB SSD as an M.2 form-factor drive (exact interface/model not asserted).
- No changes to live infrastructure configurations.

## 2026-11-22 — Hardware platform and memory specification corrections v1.3

- Documented AI Node 01 as an ASUS ROG Maximus XI (Z390) build with an ASUS ROG Strix RTX 3090 24 GB.
- Identified AI Node 02 GPUs as a triple-fan Gigabyte RTX 3060 12 GB (exact variant not confirmed) and an ASUS ROG Strix RTX 2080 Ti 11 GB.
- Corrected RAM types: Daily workstation 64 GB DDR5; Security Onion host 64 GB DDR5; HP Victus 32 GB DDR5; primary PBS 32 GB DDR4; Raspberry Pi 4 8 GB LPDDR4.
- Added the Daily workstation's Samsung 9100 PRO 4 TB M.2 NVMe SSD.
- Updated the detailed hardware register and quick-reference table. No device configuration was changed.

## 2026-11-22 — Hardware inventory corrections v1.2

- Identified the workstation GPU as an ASUS ROG Astral GeForce RTX 5090 (32 GB).
- Confirmed the isolated HP ProDesk test node has 64 GB installed RAM and a 2 TB SSD; hardware ready, separate deployment/isolation validation still required.
- Confirmed the primary PBS hardware has 32 GB RAM and two 6 TB disks in RAID1.
- Confirmed the Raspberry Pi 4 has 8 GB RAM.
- No live IPs, backup placement, encryption or recovery secrets were disclosed.

## 2026-11-22 — Public hardware inventory v1.1

- Added a detailed public-safe register for 11 documented compute devices (13 in the wider inventory, 2 omitted from detailed public disclosure).
- Added CPU, RAM, accelerator and role details, plus a six-GPU summary.
- Distinguished operating hosts, hardware available for experimentation, and not-yet-deployed security nodes.
- Reconciled hardware navigation in the repository README and architecture overview.
- Kept private storage inventory, IPs, port mapping, serial numbers and administrative access out of GitHub.

This file tracks significant public documentation changes, not live device configuration changes.

## 2026-11-21 — Network baseline v1.0

- Added public-safe network architecture, conceptual role diagram and trust-zone model.
- Recorded the As-Is / To-Be split and an architecture decision about segmentation and recovery.
- Added MikroTik, TP-Link, firewall-policy and remote-administration notes.
- Added change-management and recovery runbook **frameworks**.
- Added a sanitized validation register, with evidence limitations made explicit.
- Improved repository navigation and ignored common sensitive configuration backup formats.

**No network change, new scan, restore drill or Security Onion deployment is claimed by this documentation commit.**
