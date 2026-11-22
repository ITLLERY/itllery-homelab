# Network roles

**Document:** NET-ARCH-002  
**Baseline:** 2026-11-21

I made this diagram to show which parts of the lab serve which purpose. It groups the router, switch, workstations, servers and security systems without showing how they are actually connected.

```mermaid
%%{init: {"theme":"base","themeVariables":{"background":"#080C14","primaryColor":"#14233F","primaryTextColor":"#F5F8FF","primaryBorderColor":"#2375FF","lineColor":"#3380FF","secondaryColor":"#0D1627","tertiaryColor":"#0D1627","clusterBkg":"#0C1525","clusterBorder":"#2872E8","fontFamily":"Arial, Helvetica, sans-serif","fontSize":"14px"},"flowchart":{"htmlLabels":false,"nodeSpacing":20,"rankSpacing":22,"padding":18}}}%%
flowchart TB
    subgraph Network["NETWORK"]
        direction LR
        Router["MikroTik router"]
        Switch["TP-Link switch"]
    end

    subgraph Work["COMPUTE"]
        direction LR
        Daily["Daily workstation"]
        Virtual["Proxmox services"]
        AI["AI workloads"]
    end

    subgraph Security["TESTING"]
        direction LR
        Tests["Isolated tests"]
        Wireless["Wireless sensor"]
    end

    subgraph Operations["OPERATIONS"]
        direction LR
        Admin["Admin access"]
        Backup["Backup / recovery"]
    end

    subgraph Monitoring["MONITORING"]
        direction LR
        Host["Host monitoring"]
        Onion["Security Onion (planned)"]
    end

    %% Invisible links control the vertical layout; they are NOT network connections.
    Network ~~~ Work
    Work ~~~ Security
    Security ~~~ Operations
    Operations ~~~ Monitoring

    classDef regular fill:#12233F,stroke:#2777FF,color:#F5F8FF,stroke-width:1.7px;
    classDef accent fill:#174284,stroke:#57A0FF,color:#FFFFFF,stroke-width:2px;
    classDef planned fill:#111827,stroke:#64A5FF,color:#E8F1FF,stroke-width:2px,stroke-dasharray:6 4;
    class Router,Switch,Daily,Virtual,AI,Tests,Wireless,Admin,Backup,Host regular;
    class Onion planned;
    class Router,Switch accent;
    style Network fill:#0C1525,stroke:#2569DB,stroke-width:1.5px,color:#EAF2FF
    style Work fill:#0C1525,stroke:#2569DB,stroke-width:1.5px,color:#EAF2FF
    style Security fill:#0C1525,stroke:#2569DB,stroke-width:1.5px,color:#EAF2FF
    style Operations fill:#0C1525,stroke:#2569DB,stroke-width:1.5px,color:#EAF2FF
    style Monitoring fill:#0C1525,stroke:#2569DB,stroke-width:1.5px,color:#EAF2FF
```

The dark background, blue outlines and white labels follow my ITLLERY colours. I shortened the headings and switched to SVG text labels to avoid the clipped titles in GitHub. Dashed blue borders indicate a planned component. The invisible connections in the Mermaid source only keep the layout compact; they are **not** network links.

The diagram isn't a wiring map. It doesn't show real VLANs, trunk ports, access rules, management routes or the Security Onion mirror source. A box appearing beside another box doesn't mean the two systems can reach each other.

The monitoring role is also still being developed. I haven't verified full Security Onion packet visibility, and a drawing can't demonstrate isolation or successful recovery from a backup.

I keep the real Layer 1/2 connections, IP addressing, firewall exceptions and monitoring paths in private documentation. The reasoning behind the separation is in [ADR-0001](adr/0001-segmentation-and-recovery.md).
