# Network work: current state and next steps

**Document:** NET-ARCH-004  
**Baseline:** 2026-11-21

After rebuilding the network, I wanted one place to record what was working and what still needed attention. I use **Session-observed** for something I saw during the recovery without keeping public raw evidence. **Partial** means I tested only part of a feature. **Planned** means the work isn't finished.

| Capability | As-Is on 2026-11-21 | To-Be / acceptance criterion |
| --- | --- | --- |
| Core routing and access | Session-observed: recovery completed and routine access restored | Re-run a repeatable reachability suite after every material change |
| MikroTik policy controls | Session-observed: selected drop rules, established/related behavior and a final deny counter reviewed | Document a reviewed rule policy and test each critical allow/deny boundary |
| VLAN-aware switching | Partially verified: active paths work | Finish outstanding switch management and access-port checks |
| Administrative access | Session-observed: authorized remote/management access available | Record reproducible positive/negative management-access tests |
| Proxmox management | Session-observed: both hosts available in browser | Retain redacted evidence after a planned network validation |
| Router backup | Session-observed: I created an export and a backup | Check retention, integrity and perform a controlled restore exercise |
| Rescue path | Implemented, recheck needed | Demonstrate an isolated, controlled recovery drill without risking live access |
| Segmentation coverage | Partially verified; selected drops observed | Verify all intended zone-pair outcomes from actual source endpoints |
| Security Onion monitoring | Planned | Complete bare-metal setup, mirror design and packet/alert validation |
| Switch mirror / SPAN | Design work in progress | Confirm mirror source selection, direction, packet loss and sensor visibility |
| High-risk isolated testing | Planned / incomplete | Prove no unintended routes or management dependencies exist |

## What I still need to check

The next job is to review the remaining TP-Link settings against my private port and VLAN plan. After that, I'll test the permitted and blocked connections between the zones from real endpoints. I also want to check the rescue procedure and perform a proper backup-restore exercise rather than relying on the presence of backup files alone.

Security Onion will need its own tests after installation. I'll check the mirrored traffic, look for missing paths and verify that the capture and detection pipeline actually sees the events I expect.

These are my notes from the November recovery, not a fresh test report. The [validation register](../../evidence/sanitized/network-validation.md) keeps the observations separate from work that still needs evidence.
