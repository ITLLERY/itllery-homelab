# ITLLERY | Network Infrastructure Overview

| Field | Value |
| --- | --- |
| Document ID | NET-ARCH-001 |
| Revision | 1.0 |
| Baseline date | 2026-11-21 |
| Classification | PUBLIC / SANITIZED |
| Scope | Home laboratory network; not a production enterprise deployment |
| Verification basis | My notes from the November 2026 network recovery |

## Purpose

I use this network as a place to learn how to build, secure, operate and recover a segmented environment. The aim is not just to make a configuration work once. I want to be able to explain the design, identify what I have changed, test what I rely on, and get back to a known state after a failure.

This is a **public-safe architectural baseline**, not a complete diagram of my live environment. The real addressing plan, switch port assignments, firewall rules, management paths and backup files are stored separately.

## Scope and roles

- **Edge and routing:** MikroTik hAP ax², used for the routing, security-policy and recovery work documented here.
- **Managed switching:** TP-Link switch, used for VLAN-aware switching and planned monitoring handoff.
- **Virtualization:** SOC Core and Service Proxmox hosts, providing separate service environments.
- **Daily endpoint:** A work system kept separate from risky experiments by design.
- **Monitoring:** Wazuh-related services and a planned dedicated Security Onion deployment.
- **Testing:** Dedicated nodes for controlled attack, defensive and wireless experiments.
- **Operations and recovery:** Restricted management, recovery procedures, backups and monitoring utilities.

See [the public hardware inventory](../hardware/README.md) for general node descriptions.

## Engineering objectives

1. Establish distinct trust zones instead of treating every device as equally trusted.
2. Permit traffic deliberately and deny anything not covered by an explicit requirement.
3. Keep administrative access controlled and independent of untrusted experiments.
4. Make potentially destructive network changes recoverable.
5. Record expected results, actual observations and unresolved gaps.
6. Separate the **current state (As-Is)** from the **target state (To-Be)**.

## Current baseline

During the November recovery, I restored routing and management reachability, reviewed selected firewall drop counters and reached both Proxmox management interfaces from an authorized context. I also created a router configuration export and backup. These observations do not amount to a complete security review or a tested bare-metal restore.

Parts of the switch configuration, full inter-zone testing and Security Onion traffic visibility still need confirmation. Details and evidence limitations are tracked in [As-Is vs To-Be](as-is-vs-to-be.md) and the [validation register](../../evidence/sanitized/network-validation.md).

## Reference material

- [CIS Controls v8.1 — Control 4 and Control 12](https://www.cisecurity.org/controls/cis-controls-navigator): configuration management and managed network infrastructure.
- [NIST SP 800-41 Rev. 1](https://csrc.nist.gov/pubs/sp/800/41/r1/final): firewall policy design and maintenance.
- [RFC 5737](https://www.rfc-editor.org/rfc/rfc5737): non-routable example IPv4 addressing for public documentation.

I use these references as design guidance. This document does **not** claim a CIS certification, formal compliance assessment or completed control implementation.
