# ITLLERY Homelab

This is where I document my cybersecurity home lab: the machines I use, what each one does, how I think about security and what I learn by building and testing things.

The lab keeps changing. **Some parts are running, others are still planned.** A folder doesn't mean I've finished or tested that project.

## The lab

My wider inventory has **13 physical compute devices**. **11 are documented in the [public hardware inventory](docs/hardware/hardware-inventory.md)**, including my laptop and Raspberry Pi. Two other machines remain out of the detailed public inventory. Virtual machines don't count as separate physical nodes.

I use dedicated systems for daily work, SOC monitoring, virtualization, local AI, controlled testing, network utilities and backup/recovery. I also use MikroTik and managed switching.

## Start here

- [Public architecture and role map](docs/architecture/README.md)
- [Network infrastructure baseline (2026-11-21)](docs/architecture/network-overview.md)
- [As-Is / To-Be network status](docs/architecture/as-is-vs-to-be.md)
- [Hardware inventory: 13 physical devices, 11 publicly documented](docs/hardware/README.md)
- [Detailed CPU / RAM / GPU specifications](docs/hardware/hardware-inventory.md)
- [What I share and what stays private](docs/security/README.md)
- [Network platform notes](infrastructure/network/README.md)
- [SOC monitoring](infrastructure/soc/README.md)
- [Runbooks](runbooks/README.md)
- [Sanitized evidence](evidence/sanitized/README.md)
- [Documentation changelog](CHANGELOG.md)

## Current work

The November 2026 priority is restoring and documenting a controlled, segmented network. Some management and routing paths have been recovered, while full switching, isolation, monitoring coverage and restore validation are still in progress. The [network validation register](evidence/sanitized/network-validation.md) separates session observations from pending evidence.

I also plan a Windows laptop offline-AI build, with Kali in a separate follow-up. I'll add tested commands, detection rules, screenshots, results and fixes when each project is actually completed.

I won't upload live network configuration, private access details, passwords, recovery secrets or malware binaries.

