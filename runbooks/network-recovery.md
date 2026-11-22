# Recovering the network

**Runbook:** RB-NET-002  
**Reviewed:** 2026-11-21  
**State:** Recovery notes; a complete restore rehearsal is still open

I use this procedure when routing, switching or management access stops working as expected. The first thing I try to avoid is making the problem worse with more unplanned changes.

## Where I start

| Symptom | Initial question | Recovery priority |
| --- | --- | --- |
| Management UI unavailable | Is this an access-policy issue or a device fault? | Preserve existing working sessions |
| Endpoint loses its zone | Did switching, tagging or PVID change? | Recheck both sides offline |
| Allowed service unreachable | Was routing, DNS, endpoint policy or firewall modified? | Compare to pre-change state |
| Unexpected inter-zone reachability | Did a rule, route, trunk or alternate path change? | Contain exposure before re-enabling services |
| Network appliance reset | Is the known-good configuration still recoverable? | Avoid unreviewed broad restoration |

## My recovery steps

1. I stop changing settings and record what stopped working and when I first noticed it.
2. If an administrative session still works, I keep it open.
3. I check whether the problem affects one device, one network zone or several parts of the lab.
4. I compare the current behaviour with the last working configuration and my private connection map.
5. If normal management no longer works, I use the recovery method already set up for that purpose.
6. I restore only the known-good settings I need, and I check compatibility before using a backup.
7. I test management access, required services and the paths that must remain blocked.
8. I record the cause when I find it and note what I changed to prevent a repeat.

## Backups need testing

Creating a router export or backup is useful, but it doesn't prove that restoring it will work. I still need a controlled restore exercise on suitable hardware or a noncritical setup, followed by the same access and isolation checks I would perform after a real recovery.

I won't attempt a rollback with an untrusted backup or one that may not match the device or firmware. I also won't risk destroying the only working recovery connection.

During the November rebuild I used recovery access to get the network working again. I haven't yet documented a separate, complete backup-restore rehearsal.
