# Network zones

**Document:** NET-ARCH-003  
**Baseline:** 2026-11-21

I don't want every system in the lab to trust every other system. A machine used for everyday work has a different risk profile from one used to analyse potentially hostile files. The zones below describe how I divide the responsibilities. They are a design overview, not a list of real VLAN numbers or network connections.

| Logical zone | Typical function | Security design expectation |
| --- | --- | --- |
| Management | Network and infrastructure administration | Explicitly authorized identities, limited exposure, audited changes |
| Daily work | Personal productivity and development | No unrestricted trust toward experiment systems |
| Virtualization/services | Hypervisors and service workloads | Constrained service-specific access |
| SOC/monitoring | Security events and selected traffic observations | Independent monitoring and protected management |
| AI compute | Offline inference and experimental workloads | Isolation appropriate to model and workload risk |
| Controlled testing | Authorized offensive and purple-team testing | Tight egress and cross-zone controls |
| High-risk analysis | Potentially hostile material | No ordinary path into trusted systems; stronger isolation required |
| Backup/recovery | Preservation and restoration | Separated administration, limited access and restore testing |
| Rescue | Recovery from configuration or access failures | Small, controlled attack surface; not a general user network |
| Wireless clients/sensors | Wireless access and defensive observation | Explicit policy; passive capture is not equivalent to routed reachability |

## How I check separation

A VLAN by itself doesn't guarantee isolation. The switch has to tag and handle traffic correctly, and the router and endpoint firewalls have to enforce the intended rules. I also have to check that there isn't another path around those controls.

For each zone, I want a clear record of which machines belong there, which connections are needed and why. I then test at least one allowed path and one blocked path from the relevant endpoints. I keep the real addresses and rules privately and publish only reviewed results.

A SPAN port helps me observe selected traffic; it doesn't block traffic or guarantee that I can see everything. Complete end-to-end segmentation testing and the Security Onion monitoring checks are still open work.
