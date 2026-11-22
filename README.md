# ITLLERY Homelab

I started building this lab because I wanted to understand cybersecurity by working with real machines. I use it to practise networking, virtualization, monitoring, backups and controlled security tests. When something breaks, I try to find the cause, fix it and write down what happened.

The setup changes as I learn. Some systems are running, while others are still being prepared. I keep that distinction in the documentation so the repository shows where each project actually stands.

## My lab

I have **13 physical compute devices** in the inventory. I describe **11 of them** in my [hardware inventory](docs/hardware/hardware-inventory.md), including the laptop and Raspberry Pi. I keep two reserve machines out of the detailed public overview. The MikroTik router and TP-Link switch are separate network devices; virtual machines do not count as extra physical machines.

The machines have different jobs. I use Proxmox for virtualized services, separate GPUs for local AI and dedicated hardware for security monitoring and testing. I also have a daily Linux workstation, a backup server and a small utility node.

## Documentation

- [Architecture and roles](docs/architecture/README.md)
- [Hardware inventory](docs/hardware/hardware-inventory.md)
- [Network baseline from November 2026](docs/architecture/network-overview.md)
- [What is working and what still needs testing](docs/architecture/as-is-vs-to-be.md)
- [MikroTik, TP-Link and firewall notes](infrastructure/network/README.md)
- [SOC monitoring](infrastructure/soc/README.md)
- [Runbooks](runbooks/README.md)
- [Test notes and evidence](evidence/sanitized/README.md)
- [What I keep private](docs/security/README.md)
- [Changes to this documentation](CHANGELOG.md)

## What I'm working on now

In November 2026 I rebuilt parts of the network after problems with the router and switch. Routing and access to both Proxmox interfaces are working again. I still need to complete several switch checks, test the isolation between zones more thoroughly and validate the monitoring path for the planned Security Onion sensor. I keep those open items in the [network validation register](evidence/sanitized/network-validation.md).

I'm also preparing an offline-AI project on a Windows laptop. I'll document the steps and test results as I complete them, with Kali Linux planned for a separate follow-up.

I use AI tools when researching, troubleshooting and writing notes. The hardware, decisions and test results described here relate to my own lab. I don't upload credentials, live network configuration or sensitive recovery information.
