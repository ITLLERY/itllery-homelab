# ITLLERY | Physical Hardware Inventory

**Reviewed:** 2026-11-22  
**Updated:** 2026-11-22  
**Scope:** My physical machines and their roles, without private network details.

## How many machines I have

My wider inventory currently contains **13 physical compute devices**. I document **11 of them** in this public register and keep **2 reserve machines** out of the detailed list. Being in my inventory does not mean a device is deployed or online.

| Category | Publicly documented physical devices |
| --- | ---: |
| Linux daily workstation | 1 |
| Laptop / portable test platform | 1 |
| Proxmox virtualization hosts | 2 |
| Dedicated network security sensor host | 1 |
| Local AI compute nodes | 2 |
| HP ProDesk security test / sensor minis | 2 |
| Primary backup host | 1 |
| Raspberry Pi utility / jump host | 1 |
| **Total publicly documented compute devices** | **11** |
| Other reserve machines (details not public) | **2** |
| **Total physical compute inventory** | **13** |

I count my MikroTik hAP ax² router and managed TP-Link switch as separate **network appliances**, not among the 13 compute devices. VMs, containers and services are **not additional physical machines**.

## Machines and specifications

| ID / role | Platform / processor | System RAM | Graphics / accelerators | Use and status |
| --- | --- | --- | --- | --- |
| **Daily workstation** | **AMD Ryzen 9 9950X**, Ubuntu desktop | **64 GB DDR5** | **ASUS ROG Astral GeForce RTX 5090, 32 GB** | Primary working system, video production and GPU work; operating |
| **SOC Core** | **Intel Core i9-13900K**, Proxmox | **128 GB DDR5** | **RTX A2000, 12 GB** | Virtualized security services and Wazuh-related workloads; operating |
| **Service Proxmox** | **Intel Core i7-13700K**, Proxmox | **64 GB DDR5** | Not specified | General infrastructure services and VMs; operating |
| **Security Onion host** | **Intel Core i9-13900K**, dedicated bare-metal platform | **64 GB DDR5** | No GPU requirement | Security Onion network analysis / packet capture; **deployment planned, not verified complete** |
| **AI Node 01** | **Intel Core i9-9900K**, **ASUS ROG Maximus XI Z390** | **64 GB DDR4** | **ASUS ROG Strix RTX 3090, 24 GB** | Local model inference and experiments; I have not rechecked workloads for this inventory update |
| **AI Node 02** | **Intel Core i9-9900K**, **ASUS TUF Z390** | **64 GB DDR4** | **Gigabyte GeForce RTX 3060, 12 GB (triple-fan)** + **ASUS ROG Strix GeForce RTX 2080 Ti, 11 GB** | Secondary local AI compute; I have not rechecked workloads for this inventory update |
| **Wi-Fi sensor mini** | **HP ProDesk 400 G6 Mini**, **Intel Core i5-10500T** | **16 GB DDR4 (2 × 8 GB)** | Integrated graphics | **Samsung 970 EVO M.2 NVMe SSD**; **Alfa AWUS036AXML USB Wi-Fi adapter**; **I have not completed the documented OS / monitoring checks yet** |
| **Isolated test mini** | **HP ProDesk 400 G6 Mini**, **Intel Core i5-10500T** | **64 GB DDR4 (2 × 32 GB)** | Integrated graphics | Controlled purple-team experiments and isolated high-risk analysis; **hardware ready**, isolation and exercise validation tracked separately |
| **Primary PBS** | **Intel Core i7-8700**, Proxmox Backup Server | **32 GB DDR4** | Not specified | On-demand backup system; **2 × 6 TB WD Red HDDs in RAID1**; backup transfer rate intentionally limited to **~60 MiB/s** |
| **Jump / utility node** | **Raspberry Pi 4** | **8 GB LPDDR4** | Integrated graphics | Network utilities and approved administration; I use this node for lab services |
| **HP Victus laptop** | **AMD Ryzen 7 7840HS** | **32 GB DDR5** | **RTX 4070 Laptop, 8 GB** | Windows offline-AI project; Kali-based follow-up planned |

**How I track progress:** If I leave a specification unspecified, it means I have not added a confirmed value to this register—not that the part is missing. I track hardware, OS installation, isolation and completed security tests separately.

## Notes on the machines

### Workstation and virtualized services

- **Daily workstation:** Linux/Ubuntu-based desktop with an AMD Ryzen 9 9950X CPU, 64 GB DDR5 RAM, an ASUS ROG Astral GeForce RTX 5090 (32 GB VRAM), and a **Samsung 9100 PRO 4 TB M.2 NVMe SSD**. I have not added the workstation motherboard model to this inventory.
- **SOC Core:** Intel Core i9-13900K, 128 GB DDR5, RTX A2000 12 GB and Proxmox. Runs the primary virtualized security environment. The separate Security Onion bare-metal system is **not** counted as a VM of this host.
- **Service Proxmox:** Intel Core i7-13700K and 64 GB DDR5. During the November network recovery, I reached the management interfaces of both Proxmox hosts.
- **HP Victus laptop:** Ryzen 7 7840HS, 32 GB DDR5 RAM and RTX 4070 Laptop GPU (8 GB). The Windows offline-AI build and benchmarks are a separate project; I will add the results once I finish testing.

### Local AI

- **AI Node 01:** Intel Core i9-9900K on an ASUS ROG Maximus XI (Z390) motherboard, 64 GB DDR4 and an ASUS ROG Strix GeForce RTX 3090 (24 GB VRAM).
- **AI Node 02:** Intel Core i9-9900K on an ASUS TUF Z390 board, 64 GB DDR4, one Gigabyte GeForce RTX 3060 (12 GB VRAM, three-fan cooler; exact Gigabyte variant not yet recorded) and one ASUS ROG Strix GeForce RTX 2080 Ti (11 GB VRAM). The two GPUs are separate devices: **VRAM does not automatically combine into one contiguous pool**.

### Security monitoring and test nodes

- **Dedicated Security Onion host:** Intel Core i9-13900K, 64 GB DDR5 RAM, with separate high-performance storage planned for the operating system and packet capture and an Intel I350-class network adapter in my build plan. I still need to document bare-metal installation and validate mirror/capture coverage.
- **Wi-Fi sensor:** HP ProDesk 400 G6 Mini with i5-10500T, 16 GB DDR4 (2 × 8 GB), a **Samsung 970 EVO M.2 NVMe SSD** and an **Alfa AWUS036AXML USB Wi-Fi adapter** for wireless monitoring experiments. I have not yet completed and documented the OS, monitor-mode and monitoring checks for this node.
- **Isolated test system:** Second HP ProDesk 400 G6 Mini with i5-10500T. **64 GB RAM (2 × 32 GB) and a 2 TB M.2 SSD are installed**; the hardware build is ready for controlled experiments. I will verify the operating system, isolation boundaries and handling procedures separately before high-risk testing.

### Recovery and utilities

- **Primary PBS:** Intel Core i7-8700, 32 GB DDR4 RAM and **2 × 6 TB WD Red HDDs in RAID1** (12 TB raw, approximately 6 TB usable before filesystem overhead). Used on demand rather than counted as a continuously active production server. I intentionally **limit routine backup transfer throughput to approximately 60 MiB/s** to reduce sustained workload on the HDDs. This is an operational rate limit, **not the disks' rated or measured maximum speed**, and does not by itself guarantee longer drive life. I keep backup placement, encryption and retention details private.
- **Jump / utility Pi:** Raspberry Pi 4 with 8 GB LPDDR4 RAM, supporting selected network utilities and controlled infrastructure administration; AdGuard Home and SmokePing have been used in the lab.

## Graphics cards

| GPU model | Count | Published VRAM per GPU |
| --- | ---: | --- |
| ASUS ROG Astral GeForce RTX 5090 | 1 | 32 GB |
| NVIDIA RTX A2000 | 1 | 12 GB |
| ASUS ROG Strix GeForce RTX 3090 | 1 | 24 GB |
| Gigabyte GeForce RTX 3060 (triple-fan) | 1 | 12 GB |
| ASUS ROG Strix GeForce RTX 2080 Ti | 1 | 11 GB |
| NVIDIA GeForce RTX 4070 Laptop GPU | 1 | 8 GB |
| **Total discrete NVIDIA GPUs in this public register** | **6** | **Not a shared VRAM pool** |

My six discrete NVIDIA GPUs are distributed across five machines in this register. I do not count integrated graphics.

## What I leave out

I deliberately leave real IP addresses, VLAN IDs, MAC addresses, serials, cabling, the complete storage register, backup placement, encryption and retention settings, management endpoints, firewall exceptions, credentials and live configuration exports out of GitHub. I keep those details privately.

For my lab's **logical roles**, see [the public architecture](../architecture/README.md). I track **network state and verification** in [As-Is vs To-Be](../architecture/as-is-vs-to-be.md) and [network validation](../../evidence/sanitized/network-validation.md).

I update this inventory when I confirm hardware changes. **I treat hardware ownership, installation, bootability and completed tests as different states.**
