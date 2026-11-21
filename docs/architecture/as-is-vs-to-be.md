# Network Baseline | As-Is vs To-Be

**Document ID:** NET-ARCH-004  
**Baseline date:** 2026-11-21  
**Classification:** PUBLIC / SANITIZED

## Status vocabulary

- **Session-observed:** Seen or operator-confirmed during the November restoration; the raw evidence is not published.
- **Implemented, recheck needed:** Configuration appears present but the required acceptance test has not been fully retained.
- **Partially verified:** Some functionality was tested; full coverage is not established.
- **Planned:** Intentional future work, not a claim of deployment.

| Capability | As-Is on 2026-11-21 | To-Be / acceptance criterion |
| --- | --- | --- |
| Core routing and access | Session-observed: recovery completed and routine access restored | Re-run a repeatable reachability suite after every material change |
| MikroTik policy controls | Session-observed: selected drop rules, established/related behavior and a final deny counter reviewed | Document a reviewed rule policy and test each critical allow/deny boundary |
| VLAN-aware switching | Partially verified: active paths work | Finish outstanding switch management and access-port checks |
| Administrative access | Session-observed: authorized remote/management access available | Record reproducible positive/negative management-access tests |
| Proxmox management | Session-observed: both hosts available in browser | Retain redacted evidence after a planned network validation |
| Router backup | Operator-confirmed: export and backup created | Check retention, integrity and perform a controlled restore exercise |
| Rescue path | Implemented, recheck needed | Demonstrate an isolated, controlled recovery drill without risking live access |
| Segmentation coverage | Partially verified; selected drops observed | Verify all intended zone-pair outcomes from actual source endpoints |
| Security Onion monitoring | Planned | Complete bare-metal setup, mirror design and packet/alert validation |
| Switch mirror / SPAN | Design work in progress | Confirm mirror source selection, direction, packet loss and sensor visibility |
| High-risk isolated testing | Planned / incomplete | Prove no unintended routes or management dependencies exist |

## Known technical debt

1. Complete TP-Link configuration review without changing working paths blindly.
2. Reconcile private as-built documentation with the original conceptual zone plan.
3. Finish end-to-end allow/deny tests, including endpoint-level controls.
4. Validate the backup *restore*, not just the ability to create an archive.
5. Recheck rescue and rollback steps as a deliberate maintenance test.
6. Validate Security Onion monitoring **after** installation; do not infer coverage from the presence of a mirror.

## Publication rule

If a check was only described in a conversation and no sanitized artifact is attached, I state that plainly. Missing evidence is a follow-up task, not a reason to invent a pass.

Related: [Network validation register](../../evidence/sanitized/network-validation.md).
