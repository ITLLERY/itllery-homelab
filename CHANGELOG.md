# Changelog

## 2026-11-22 — Hardware platform and memory specification corrections v1.3

- Documented AI Node 01 as an ASUS ROG Maximus XI (Z390) build with an ASUS ROG Strix RTX 3090 24 GB.
- Corrected RAM types: Security Onion host 64 GB DDR5; HP Victus 32 GB DDR5; primary PBS 32 GB DDR4; Raspberry Pi 4 8 GB LPDDR4.
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
