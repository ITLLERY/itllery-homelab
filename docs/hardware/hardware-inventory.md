# ITLLERY | Physical Hardware Inventory

**Reviewed:** 2026-11-22  
**Document type:** Public hardware overview  
**Evidence basis:** Owner-supplied specifications and deployment notes from November 2026  
**Scope:** Physical compute devices only; this is not a network asset map.

## Device count

My wider inventory currently contains **13 physical compute devices**. This public register documents **11 physical devices** in detail. I deliberately keep the remaining **2 reserve devices** out of the detailed public register. Their presence in the total is not a statement that they are installed or online.

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

The MikroTik hAP ax² router and managed TP-Link switch are **network appliances**, not part of these 13 compute devices. VMs, containers, and services are **not additional physical machines**.

## Hardware by role

| ID / role | Platform / processor | System RAM | Graphics / accelerators | Use and status |
| --- | --- | --- | --- | --- |
| **Daily workstation** | Ubuntu desktop; CPU model not re-verified for public documentation | **64 GB DDR5** | **ASUS ROG Astral GeForce RTX 5090, 32 GB** | Primary working system, video production and GPU work; operating |
| **SOC Core** | Lenovo P3, **Intel Core i9-13900K**, Proxmox | **128 GB DDR5** | **RTX A2000, 12 GB** | Virtualized security services and Wazuh-related workloads; operating |
| **Service Proxmox** | **Intel Core i7-13700K**, Proxmox | **64 GB DDR5** | Not specified | General infrastructure services and VMs; operating |
| **Security Onion host** | **Intel Core i9-13900K**, dedicated bare-metal platform | **64 GB DDR5** | No GPU requirement documented | Security Onion network analysis / packet capture; **deployment planned, not verified complete** |
| **AI Node 01** | **Intel Core i9-9900K**, **ASUS ROG Maximus XI (Z390)** | **64 GB DDR4** | **ASUS ROG Strix RTX 3090, 24 GB** | Local model inference and experiments; hardware reported, latest workload status not independently checked |
| **AI Node 02** | **Intel Core i9-9900K**, ASUS TUF Z390 platform | **64 GB DDR4** | **RTX 3060, 12 GB** + **RTX 2080 Ti, 11 GB** | Secondary local AI compute; hardware reported, latest workload status not independently checked |
| **Wi-Fi sensor mini** | **HP ProDesk 400 G6 Mini**, **Intel Core i5-10500T** | **16 GB DDR4 (2 × 8 GB)** | Integrated graphics | Planned wireless monitoring; **OS / deployment not complete** |
| **Isolated test mini** | **HP ProDesk 400 G6 Mini**, **Intel Core i5-10500T** | **64 GB DDR4 (2 × 32 GB installed)** | Integrated graphics | Controlled purple-team experiments and isolated high-risk analysis; **hardware ready**, isolation and exercise validation tracked separately |
| **Primary PBS** | **Intel Core i7-8700**, Proxmox Backup Server | **32 GB DDR4** | Not specified | On-demand backup system; **2 × 6 TB drives in RAID1** |
| **Jump / utility node** | **Raspberry Pi 4** | **8 GB LPDDR4** | Integrated graphics | Network utility and approved administration role; services reported operating |
| **HP Victus laptop** | **AMD Ryzen 7 7840HS** | **32 GB DDR5** | **RTX 4070 Laptop, 8 GB** | Windows offline-AI project; Kali-based follow-up planned |

**Accuracy rules:** “Not specified” and “not reconfirmed” do **not** mean the hardware has no RAM, GPU or storage. They mean I am not publishing an unverified number. Installed hardware does not by itself prove an operating system, firewall/isolation policy or a security exercise has passed acceptance testing.

## Hardware detail notes

### Workstation and virtualized services

- **Daily workstation:** Linux/Ubuntu-based desktop with 64 GB DDR5 RAM, an ASUS ROG Astral GeForce RTX 5090 (32 GB VRAM), and a **Samsung 9100 PRO 4 TB M.2 NVMe SSD**. The CPU and motherboard are intentionally left unasserted until I verify their current specifications.
- **SOC Core:** Intel Core i9-13900K, 128 GB DDR5, RTX A2000 12 GB and Proxmox. Runs the primary virtualized security environment. The separate Security Onion bare-metal system is **not** counted as a VM of this host.
- **Service Proxmox:** Intel Core i7-13700K and 64 GB DDR5. The November network recovery confirmed authorized browser access to this host and the SOC Core host.
- **HP Victus laptop:** Ryzen 7 7840HS, 32 GB DDR5 RAM and RTX 4070 Laptop GPU (8 GB). Windows-based offline-AI installation and benchmarking are separate projects; documentation does not imply those tests are finished.

### Local AI

- **AI Node 01:** Intel Core i9-9900K on an ASUS ROG Maximus XI Z390 motherboard (exact Maximus XI submodel not yet recorded), 64 GB DDR4 and an ASUS ROG Strix GeForce RTX 3090 (24 GB VRAM).
- **AI Node 02:** Intel Core i9-9900K on an ASUS TUF Z390 board, 64 GB DDR4, one RTX 3060 (12 GB VRAM) and one RTX 2080 Ti (11 GB VRAM). The two GPUs are separate devices: **VRAM does not automatically combine into one contiguous pool**.

### Security monitoring and test nodes

- **Dedicated Security Onion host:** Intel Core i9-13900K, 64 GB DDR5 RAM, with a separate high-performance storage plan for operating system and packet capture and an Intel I350-class network adapter reported in the build plan. Bare-metal installation and mirror/capture validation remain separate acceptance milestones.
- **Wi-Fi sensor:** HP ProDesk 400 G6 Mini with i5-10500T and 16 GB RAM (2 × 8 GB). A Samsung NVMe SSD was selected/tested for this node; OS installation and production monitoring have **not** been confirmed. The planned wireless workflow uses a compatible external adapter.
- **Isolated test system:** Second HP ProDesk 400 G6 Mini with i5-10500T. **64 GB RAM (2 × 32 GB) and a 2 TB SSD are installed**; the hardware build is ready for controlled experiments. The operating system, access isolation and safe-handling procedures require their own validation before any high-risk testing.

### Recovery and utilities

- **Primary PBS:** Intel Core i7-8700, 32 GB DDR4 RAM and two 6 TB disks configured as RAID1 (12 TB raw, approximately 6 TB usable before filesystem overhead). Used on demand rather than counted as a continuously active production server. Backup placement, encryption and retention details remain private.
- **Jump / utility Pi:** Raspberry Pi 4 with 8 GB LPDDR4 RAM, supporting selected network utilities and controlled infrastructure administration; AdGuard Home and SmokePing have been used in the lab.

## Accelerator overview

| GPU model | Count | Published VRAM per GPU |
| --- | ---: | --- |
| ASUS ROG Astral GeForce RTX 5090 | 1 | 32 GB |
| NVIDIA RTX A2000 | 1 | 12 GB |
| ASUS ROG Strix GeForce RTX 3090 | 1 | 24 GB |
| NVIDIA GeForce RTX 3060 | 1 | 12 GB |
| NVIDIA GeForce RTX 2080 Ti | 1 | 11 GB |
| NVIDIA GeForce RTX 4070 Laptop GPU | 1 | 8 GB |
| **Total discrete NVIDIA GPUs in this public register** | **6** | **Not a shared VRAM pool** |

The six discrete GPUs are distributed across five documented physical machines. Integrated GPUs are not included in this count.

## Public vs private inventory

This page deliberately does **not** include real addressing, VLAN identifiers, MAC addresses, serials, precise cabling, complete device-by-device storage inventories, backup placement, encryption or retention policy, management endpoints, firewall exceptions, credentials or live configuration exports. Those details belong in a secure local asset register, not a public GitHub repository.

For the lab's **logical roles** see [the public architecture](../architecture/README.md). For **network state and verification** see [As-Is vs To-Be](../architecture/as-is-vs-to-be.md) and [network validation](../../evidence/sanitized/network-validation.md).

I update this inventory when I confirm hardware changes. **Ownership, installation, bootability and completed tests are different states.**
