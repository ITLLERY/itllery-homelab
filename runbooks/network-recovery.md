# Runbook | Network Recovery and Safe Rollback

**Runbook ID:** RB-NET-002  
**Version:** 1.0 (framework; full restore drill pending)  
**Review date:** 2026-11-21  
**Classification:** PUBLIC / SANITIZED

## Incident classes

| Symptom | Initial question | Recovery priority |
| --- | --- | --- |
| Management UI unavailable | Is this an access-policy issue or a device fault? | Preserve existing working sessions |
| Endpoint loses its zone | Did switching, tagging or PVID change? | Recheck both sides offline |
| Allowed service unreachable | Was routing, DNS, endpoint policy or firewall modified? | Compare to pre-change state |
| Unexpected inter-zone reachability | Did a rule, route, trunk or alternate path change? | Contain exposure before re-enabling services |
| Network appliance reset | Is the known-good configuration still recoverable? | Avoid unreviewed broad restoration |

## Controlled workflow

1. **Stop changes** and record the symptoms and earliest known failure time.
2. Preserve any remaining administrative session; do not log out reflexively.
3. Confirm whether the fault affects one endpoint, one zone, or multiple functions.
4. Consult the **private** as-built diagrams and last-known-good change record.
5. Use the already authorized independent recovery approach if normal management is unavailable.
6. Restore only the intended known-good state, taking version and configuration compatibility into account.
7. Recheck administrative access, required services, zone isolation and unexpected open paths.
8. Record the incident, root cause when known, and corrective action; redact before public sharing.

## Backup is not restore evidence

A configuration export may help review settings; a device backup may support restoration under compatible conditions. Their presence does **not** prove recovery will succeed. An actual restore exercise needs a suitable noncritical environment, known-good backup, documented compatibility and a full post-restore acceptance test.

## Rollback stop conditions

Do not continue an automated or manual rollback if the target firmware/model is incompatible, the backup source is untrusted, the current state is not understood or the operation threatens a still-working recovery route. Escalate to a controlled offline procedure instead.

## Acceptance for a future rehearsal

- Administrative connection restored using the planned method.
- Required operational traffic functional.
- Prohibited access paths still blocked.
- Private backups and change records reconciled.
- No unreviewed credentials, identifiers or configurations posted publicly.

**Current state:** Recovery capability has been used during the November rebuild, but an independently documented full restore rehearsal remains open.
