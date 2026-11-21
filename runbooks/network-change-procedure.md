# Runbook | Controlled Network Change

**Runbook ID:** RB-NET-001  
**Version:** 1.0 (procedure template; full rehearsal pending)  
**Review date:** 2026-11-21  
**Classification:** PUBLIC / SANITIZED

## Goal and scope

Safely change a network rule, route, VLAN or management setting without treating trial-and-error as a change process. This runbook is a reusable framework, **not** a transcript of a successfully completed end-to-end rehearsal.

## Before the change

1. Open a private change record: objective, owner, impacted systems, approved maintenance window and rollback trigger.
2. Record the current private configuration and state. Keep exports and backups away from GitHub.
3. Establish a known-good authorized administrative connection and an independent recovery option.
4. Enumerate the exact expected traffic outcomes and at least one failure case.
5. Check proposed changes against the private as-built mapping **twice**, preferably from two independent views (router/switch or configuration/endpoint).
6. Define a maximum observation period and explicit abort conditions; never depend on memory to restore connectivity.

## Execution

1. Change **one** component or policy domain at a time.
2. Avoid altering both ends of a critical VLAN or management path in one unprotected step.
3. Preserve a working way to undo the last operation.
4. Record the time and change identifier privately.
5. Test allowed access, prohibited access, DNS/services if affected, and required management connectivity.
6. Examine logs and counters **for this test window**; distinguish them from old hits.

## Decision gate

**Pass:** Required paths work, denied paths remain denied, management/recovery remain available, and observed behavior matches the change record.  
**Fail / ambiguous:** Stop, revert using the pre-agreed path, and document deviations before trying again.

## After the change

- Capture a new approved private baseline if the change is accepted.
- Update private addressing, zone, rule and port records.
- Post a sanitized change summary and test outcome to GitHub.
- Add unresolved issues to the To-Be register.

## Record template

| Field | Required entry |
| --- | --- |
| Change ID | `CHG-YYYY-NNN` |
| Requested outcome | What and why |
| Risk | What can fail or become reachable |
| Pre-change evidence | Private reference only |
| Rollback trigger and method | Private operational detail |
| Positive/negative tests | Expected vs observed |
| Outcome | Passed / failed / reverted / inconclusive |
| Follow-up | Owner and action |

**Safety rule:** Do not attempt a simulated lockout on a live router merely to generate portfolio evidence.
