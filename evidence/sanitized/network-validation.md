# Network Validation Register | Sanitized

**Document ID:** NET-EVID-001 | **Baseline:** 2026-11-21 | **Classification:** PUBLIC  
**Evidence policy:** No raw router/switch exports, real IPs, device-specific access paths or unreviewed screenshots.

## What these labels mean

- **Session-observed:** A result was seen or operator-confirmed during the recovery work, but raw capture has not been retained here.
- **Partial:** A relevant observation exists, but it does not establish complete coverage.
- **Pending:** No completed acceptance test is available for the stated scope.

These records document historical progress, not tests performed by this repository or by a CI system. **No current network scan or automated test was executed to create this page.**

| Test ID | Check | Outcome as of baseline | Evidence limitation / next action |
| --- | --- | --- | --- |
| NET-001 | Selected firewall deny behavior | Session-observed | Drop counters observed; re-run with identifiable test window and permitted source contexts |
| NET-002 | Authorized reachability of two Proxmox web interfaces | Session-observed | Operator confirmed both available; archive redacted screenshots of fresh validation |
| NET-003 | Restricted administrative / WireGuard access | Session-observed | Functioning authorized access reported; test negative cases independently |
| NET-004 | Active router-to-switch service path | Partial | Operational traffic observed; no full VLAN membership/PVID audit attached |
| NET-005 | Router configuration export and backup exist | Session-observed | Creation reported; checksum, retention and recovery exercise not publicly evidenced |
| NET-006 | Rescue operation after management failure | Partial | Rescue procedure exists / used in recovery context; controlled drill pending |
| NET-007 | Full end-to-end inter-zone isolation matrix | Pending | Needs source-endpoint testing for all intended zones and alternate paths |
| NET-008 | Complete switch management and access-port review | Pending | Outstanding management migration/review and selected port roles |
| NET-009 | Security Onion sensor and SPAN visibility | Pending | Bare-metal sensor deployment and capture validation not complete |
| NET-010 | Full restore from last-known-good router backup | Pending | Never infer restore success from backup creation |

## Required evidence structure for a future test

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

## Minimum future verification suite

1. One positive and one negative test for every approved zone-policy boundary.
2. Administrative reachability from allowed and disallowed origins.
3. VLAN/PVID behavior from representative endpoints rather than only GUI configuration.
4. Backup integrity and a non-disruptive restore rehearsal.
5. Mirror traffic matching the intended monitored flow and checks for capture loss.

**Publication check:** Remove addresses, VLAN numbers, interface names that reveal live wiring, identities, tokens, timestamps that expose access patterns, serials and metadata before committing evidence.
