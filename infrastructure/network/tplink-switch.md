# TP-Link switch

**Document:** NET-PLAT-002  
**Baseline:** 2026-11-21

I use a managed TP-Link switch for VLAN-aware connections between the lab systems. It also has a role in the planned packet-monitoring setup. The real port assignments and management address are not included here.

## What worked and what still needs checking

After the November network recovery, the switch was carrying traffic over the paths I needed at the time. I still had to review some VLAN membership, PVID and management settings, along with the final access-port assignments and mirror configuration. A working connection on one port isn't enough to say that the whole switch is configured correctly.

| Area | Required inspection | Public status |
| --- | --- | --- |
| 802.1Q membership | Expected tagged/untagged membership on every relevant logical link | Partially verified |
| PVID behavior | Untagged ingress placed in the intended zone | Pending full review |
| Trunk behavior | Necessary VLANs only, no unintended untagged acceptance | Active path observed; full audit pending |
| Management exposure | Administration reachable only from authorized context | Migration/review pending |
| Access-port roles | Endpoint placement matches the private as-built plan | Pending final review |
| Mirror/SPAN | Correct source, direction, destination and capture behavior | Planned; not verified |

## About the mirror port

I want Security Onion to receive selected network traffic through a mirror. But a mirror only copies the traffic chosen on the switch; it can't automatically see everything routed elsewhere. There can also be dropped frames or capture loss if more traffic is mirrored than the destination can handle.

For that reason, I won't call the sensor coverage complete just because a SPAN setting appears in the interface. Once Security Onion is installed, I'll check the packets arriving at the sensor and whether the expected events show up in its detection pipeline.

## How I plan to finish the review

I'll make sure I can still administer the switch before changing its management settings. Then I'll review the intended tagged and untagged membership and test endpoints on both allowed and blocked paths. I'll keep the real port map and rollback details private.

The remaining work is to finish the switch audit and check the mirror with actual traffic.
