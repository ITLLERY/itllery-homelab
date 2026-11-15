# ITLLERY — Public Hardware Overview

**Reviewed:** 2026-11-15  
**This is a public-safe inventory, not the private asset register.**

I have **13 physical compute devices** in the wider inventory. **11 are documented below** as the main public lab systems. Two additional machines are left out of the public inventory: one reserved for a future backup role and one unassigned spare. A laptop and Raspberry Pi count as physical devices; VMs do not. Router and switch are separate network appliances.

## Workstations and virtualized services

| Physical device | Public hardware summary | Role / deployment note |
| --- | --- | --- |
| Daily workstation | Ubuntu, 64 GB RAM, NVIDIA RTX 5090 (32 GB) | Everyday work, video production, GPU experiments |
| SOC Core | Intel Core i9-13900K, 128 GB RAM, NVIDIA RTX A2000, Proxmox | SOC virtualization and Wazuh environment |
| Service Proxmox | Intel Core i7-13700K, 64 GB RAM | Supporting VMs and services |
| HP Victus laptop | Ryzen 7 7840HS, 32 GB RAM, RTX 4070 Laptop (8 GB) | Windows offline AI build; Kali follow-up planned |

## Specialized security and AI systems

| Physical device | Public hardware summary | Role / deployment note |
| --- | --- | --- |
| Security Onion host | Intel Core i9-13900K, 64 GB RAM | Dedicated bare-metal network monitoring **planned** |
| AI Node 01 | Intel Core i9-9900K, 64 GB RAM, NVIDIA RTX 3090 (24 GB) | Local LLM inference and experiments |
| AI Node 02 | Intel Core i9-9900K, 64 GB RAM, NVIDIA RTX 3060 (12 GB) + RTX 2080 Ti (11 GB) | Local AI compute and experiments |
| Wi-Fi sensor | HP ProDesk 400 G6 Mini, Intel Core i5-10500T | Defensive wireless monitoring and tests |
| Isolated test node | HP ProDesk 400 G6 Mini, Intel Core i5-10500T | Controlled security experiments and isolated analysis; setup evolves |

## Backup and utilities

| Physical device | Public hardware summary | Role / deployment note |
| --- | --- | --- |
| Primary PBS | Intel Core i7-8700 | Backup and restore workflows |
| Jump Pi | Raspberry Pi 4 | Network utilities, DNS and monitoring |

## Network equipment (not included in the compute-node count)

- MikroTik hAP ax² — routing and segmentation work.
- Managed TP-Link switch — switching and monitoring design.

The lab changes over time, so exact GPU, RAM and platform details may change. A listed component is **not** proof that its planned service has been deployed or that any experiment has succeeded.

I deliberately keep drive inventory, backup capacity and placement, serial numbers, MAC addresses, live hostnames, real IPs, VLAN IDs, management ports, exact physical connections and sensitive security policy out of this page.
