# ITLLERY — Public Hardware Overview

**Reviewed:** 2026-11-22  
**This is a public-safe inventory, not the private asset register.**

The wider lab inventory contains **13 physical compute devices**. **11 are documented publicly**, including a laptop and Raspberry Pi; **2 reserve machines** stay out of the detailed public inventory. MikroTik routing and TP-Link managed switching are separate network appliances. Virtual machines are not physical devices.

## Detailed hardware register

**[View the full hardware inventory (CPU, RAM, GPU, role and deployment status)](hardware-inventory.md)**

| Physical role | Quantity |
| --- | ---: |
| Daily workstation | 1 |
| Proxmox hosts (SOC Core + Service) | 2 |
| Dedicated Security Onion hardware (deployment planned) | 1 |
| AI compute nodes | 2 |
| HP ProDesk security minis (sensor + isolated test node) | 2 |
| Primary PBS | 1 |
| Raspberry Pi utility / jump host | 1 |
| HP Victus laptop | 1 |
| **Publicly documented compute devices** | **11** |

## Quick specifications

| Device | Processor | RAM | Main accelerator | Status |
| --- | --- | --- | --- | --- |
| Daily workstation | CPU pending re-verification | 64 GB | ASUS ROG Astral RTX 5090 32 GB | Operating |
| SOC Core Proxmox | i9-13900K | 128 GB | RTX A2000 12 GB | Operating |
| Service Proxmox | i7-13700K | 64 GB | — | Operating |
| Security Onion bare metal | i9-13900K | 64 GB | — | Deployment planned |
| AI Node 01 | i9-9900K | 64 GB | RTX 3090 24 GB | Hardware documented |
| AI Node 02 | i9-9900K | 64 GB | RTX 3060 12 GB + RTX 2080 Ti 11 GB | Hardware documented |
| Wi-Fi sensor ProDesk | i5-10500T | 16 GB | Integrated | Not deployed |
| Isolated test ProDesk | i5-10500T | 64 GB installed | Integrated | Hardware ready, 2 TB SSD |
| Primary PBS | i7-8700 | 32 GB | — | On-demand, 2 × 6 TB RAID1 |
| Raspberry Pi 4 | Broadcom ARM platform | 8 GB | Integrated | Utility / jump role |
| HP Victus laptop | Ryzen 7 7840HS | 32 GB | RTX 4070 Laptop 8 GB | Windows offline-AI build |

**Deployment note:** Specs are based on owner-reported hardware. A hardware entry does not imply an installed operating system or completed security validation. For full notes and limitations, follow the detailed inventory link above.

No live addresses, real VLANs, port maps, serial/MAC identifiers, credentials, raw configurations or backup placement, secrets, encryption or retention details are published.
