# Network overview

**Document:** NET-ARCH-001  
**Baseline:** 2026-11-21  
**Scope:** Public notes on my home lab network

I use a MikroTik hAP ax² for routing and network policy, with a managed TP-Link switch for VLAN-aware connections. The network has to support normal work, Proxmox services, backups, monitoring and isolated testing. Those jobs don't all need the same access, so I've been separating them rather than relying on one flat LAN.

The important part is being able to explain why traffic is allowed or blocked. I also want to be able to change a rule without losing the only way back into the router. That became especially relevant during the November network recovery.

## Systems involved

The two Proxmox hosts provide different virtualized workloads, while my daily workstation stays separate from risky tests. Wazuh-related services are part of the SOC environment. I have dedicated hardware for Security Onion, but the bare-metal installation and packet-capture checks are still on my to-do list. The AI nodes, wireless sensor, isolated test node and backup system are documented in the [hardware inventory](../hardware/hardware-inventory.md).

## What I checked in November

I recovered routing and normal management access, reviewed selected firewall drop counters and reached the management interfaces of both Proxmox hosts. I also created a MikroTik configuration export and backup. Those results were useful, but they don't tell me that every VLAN is isolated or that a backup will restore successfully.

The TP-Link port review, complete zone-by-zone tests and SPAN visibility still need more work. I track the details in [current vs planned](as-is-vs-to-be.md) and the [validation notes](../../evidence/sanitized/network-validation.md).

## How I document changes

I keep the exact network plan, access rules and backup files privately. Here I explain what I wanted to achieve, what I tested and where the limits of the test are. This is a lab project, not a claim of formal security certification.

I refer to [CIS Controls v8.1](https://www.cisecurity.org/controls/cis-controls-navigator) for configuration and network-management practices, [NIST SP 800-41 Rev. 1](https://csrc.nist.gov/pubs/sp/800/41/r1/final) for firewall policy and [RFC 5737](https://www.rfc-editor.org/rfc/rfc5737) when I need example IP addresses in public documents.
