# TP-Link | VLAN-Aware Switching and Monitoring Design

**Document ID:** NET-PLAT-002 | **Revision:** 1.0 | **Baseline:** 2026-11-21 | **Classification:** PUBLIC

## Purpose

The managed TP-Link switch provides VLAN-aware access and trunking in the lab. It is also part of the future packet-monitoring design. This document intentionally omits the real model-specific port map and switch management location.

## State and open work

Selected active switch paths were operating after the recovery. That does not mean every intended access port, PVID, management setting or mirror was finished. The late-November work list still included management-plane migration/review, final assignment of some ports and the monitoring mirror.

## Configuration review matrix

| Area | Required inspection | Public status |
| --- | --- | --- |
| 802.1Q membership | Expected tagged/untagged membership on every relevant logical link | Partially verified |
| PVID behavior | Untagged ingress placed in the intended zone | Pending full review |
| Trunk behavior | Necessary VLANs only, no unintended untagged acceptance | Active path observed; full audit pending |
| Management exposure | Administration reachable only from authorized context | Migration/review pending |
| Access-port roles | Endpoint placement matches the private as-built plan | Pending final review |
| Mirror/SPAN | Correct source, direction, destination and capture behavior | Planned; not verified |

## Why a mirror alone is insufficient

A mirror destination receives only the traffic selected by the switch. Switch-local traffic, traffic routed elsewhere, dropped frames and high-throughput oversubscription can affect visibility. A mirror is a **sensor feed**, not a reliable claim to observe every VLAN or every packet. I will verify actual packets and any loss before calling monitoring complete.

## Safe acceptance workflow

- Confirm the switch can be administered through an approved context before changing management settings.
- Change one domain at a time; do not adjust router and switch VLAN settings together without rollback.
- For each tested endpoint, validate both a legitimate access path and a prohibited path.
- Capture private port/VLAN membership information for rollback; publish only a sanitized summary of outcomes.
- After the Security Onion deployment, confirm actual mirrored frames and corresponding detection pipeline events.

**Next milestone:** Complete the outstanding switch review and record endpoint-originated checks rather than inferring correctness from the management GUI alone.
