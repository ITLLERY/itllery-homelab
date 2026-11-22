# Network validation notes

**Document:** NET-EVID-001  
**Baseline:** 2026-11-21

I started this list after the November network recovery so I could distinguish what I had seen working from what still needed a proper test. **Session-observed** means I confirmed something during the work but don't have public raw evidence attached. **Partial** means the check covered only part of the requirement. **Pending** means I haven't completed the acceptance test.

This is a record of that work, not a fresh scan or automated test run. I haven't run new tests just to create this document.

## Results recorded so far

| Test ID | Check | Outcome as of baseline | Evidence limitation / next action |
| --- | --- | --- | --- |
| NET-001 | Selected firewall deny behavior | Session-observed | Drop counters observed; re-run with identifiable test window and permitted source contexts |
| NET-002 | Authorized reachability of two Proxmox web interfaces | Session-observed | I reached both web interfaces; redacted screenshots from a fresh check are still needed |
| NET-003 | Restricted administrative / WireGuard access | Session-observed | I confirmed authorized access; separate negative tests are still needed |
| NET-004 | Active router-to-switch service path | Partial | Operational traffic observed; no full VLAN membership/PVID audit attached |
| NET-005 | Router configuration export and backup exist | Session-observed | I created both; I have not published checksum, retention or recovery-test evidence |
| NET-006 | Rescue operation after management failure | Partial | Rescue procedure exists / used in recovery context; controlled drill pending |
| NET-007 | Full end-to-end inter-zone isolation matrix | Pending | Needs source-endpoint testing for all intended zones and alternate paths |
| NET-008 | Complete switch management and access-port review | Pending | Outstanding management migration/review and selected port roles |
| NET-009 | Security Onion sensor and SPAN visibility | Pending | Bare-metal sensor deployment and capture validation not complete |
| NET-010 | Full restore from last-known-good router backup | Pending | Never infer restore success from backup creation |

## How I'll record future tests

When I repeat a check, I want to know the date, the source and destination, the expected behaviour and the actual result. I'll keep the full details privately and use safe aliases in any public evidence.

| Field | Example (fictional, not a real test) |
| --- | --- |
| Test ID | `NET-XXX` |
| UTC timestamp | `YYYY-MM-DDThh:mm:ssZ` |
| Source / destination | `TEST-CLIENT` → `TEST-SERVICE` (public aliases) |
| Expected behavior | Allowed / blocked |
| Method | Network command, firewall counter, capture or GUI check |
| Actual observation | Exact observed result, not interpretation alone |
| Decision | Pass / fail / inconclusive |
| Evidence reference | Reviewed screenshot or redacted excerpt |
| Reviewer | Self-review or named reviewer, if applicable |

## What I'll check next

I still need positive and negative tests for each important zone boundary, including management access from allowed and disallowed endpoints. I'll check VLAN tagging and PVID behaviour from real connected systems, rehearse restoration in a safe environment and verify which mirrored packets arrive at the Security Onion sensor.

Before I publish any evidence, I'll check it for real IPs, VLAN IDs, interface names that reveal cabling, credentials, serial numbers and metadata that shouldn't be public.
