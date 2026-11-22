# Changelog

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
