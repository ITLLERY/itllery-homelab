# Network Zones and Trust Model

**Document ID:** NET-ARCH-003 | **Revision:** 1.0 | **Baseline:** 2026-11-21 | **Classification:** PUBLIC

## Design intent

Each zone has a reason to exist and an explicit risk profile. This is a conceptual model; it intentionally omits actual VLAN IDs, subnets, hosts, ports and firewall exceptions.

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

## Trust boundaries

I do not assume that VLAN membership alone provides a complete security boundary. Effective separation depends on correct switch tagging, routing, firewall behavior, host policy and the absence of unintended alternate paths. A monitoring mirror copies selected packets; it is not itself a firewall control.

No trust relationship listed above is automatically a statement of current production reachability. Each intended exception must be justified, implemented and tested separately.

## Acceptance criteria for each zone

- The purpose and asset membership are written down privately.
- Required flows are approved and documented privately.
- Positive tests prove required access is functional.
- Negative tests prove explicitly prohibited paths fail.
- Administrative and recovery dependencies are understood.
- Results are dated, reproducible and linked to a sanitized evidence record.

**Open item:** Complete end-to-end segmentation validation for all active zones; avoid claiming the isolated-test environment is fully ready before its boundaries are measured.
