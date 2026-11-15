# ITLLERY Homelab

This is where I document my cybersecurity home lab: the machines I use, what each one does, how I think about security and what I learn by building and testing things.

The lab keeps changing. **Some parts are running, others are still planned.** A folder doesn't mean I've finished or tested that project.

## The lab

My wider inventory has **13 physical compute devices**. **11 are shown in this public overview**, including my laptop and Raspberry Pi. Two other machines are kept out of the detailed public inventory: one reserved for future backup work and one unassigned spare. Virtual machines don't count as separate physical nodes.

I use dedicated systems for daily work, SOC monitoring, virtualization, local AI, controlled testing, network utilities and backup/recovery. I also use MikroTik and managed switching.

## Start here

- [Public architecture and role map](docs/architecture/README.md)
- [Hardware and node roles](docs/hardware/README.md)
- [What I share and what stays private](docs/security/README.md)
- [Network notes](infrastructure/network/README.md)
- [SOC monitoring](infrastructure/soc/README.md)
- [Runbooks](runbooks/README.md)
- [Sanitized evidence](evidence/sanitized/README.md)

## What comes next

I'll add commands, screenshots, detection rules, results and fixes as I complete and verify individual projects. The first priority is building and documenting an offline AI setup on a Windows laptop; Kali comes in a separate follow-up.

I won't upload live network configuration, private access details, passwords, recovery secrets or malware binaries.

**Build. Break. Detect. Defend. Prove.**
