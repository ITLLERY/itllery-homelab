# MikroTik routing and recovery

**Document:** NET-PLAT-001  
**Baseline:** 2026-11-21

My MikroTik hAP ax² handles routing and firewall policy in the lab. It's also where I learned that a small change to a bridge, VLAN or management rule can affect much more than the port I was working on.

## November 2026 recovery

I had to recover the router and get normal network access working again. During that work I reached the management interface, inspected VLAN filtering, reviewed selected firewall behaviour and created both a configuration export and backup.

That gave me a working starting point. It didn't prove that every VLAN was isolated or that I could restore the backup without another test. I keep those checks open rather than counting them as finished.

## What I keep track of

| Domain | Control or review question |
| --- | --- |
| RouterOS lifecycle | Version, upgrade decision, release notes, rollback prerequisites |
| Interfaces/bridge | Which interfaces belong to the expected switching context? |
| VLAN filtering | Are tagged/untagged expectations and ingress behavior consistent? |
| Routing | Are routes intentional and absent from untrusted contexts where prohibited? |
| Firewall | Is input/forward policy explicit, ordered, observable and least-privilege? |
| Administration | Are interfaces limited to approved administrative contexts? |
| WireGuard | Are peers inventoried, authorized and independently revocable? |
| Recovery | Does a safe rescue procedure remain available during planned changes? |
| Backup | Is there an offline, access-controlled configuration archive and tested restore path? |

## How I handle later changes

Before editing the router, I save the current configuration privately and decide exactly what I want to change. I check whether the change could block the management path, and I make sure a recovery option is available. I also compare the proposed setting against my private network map twice.

I avoid changing the router and switch at the same time unless the rollback is already clear. After applying one change, I test the connections that should work and those that should be blocked. If something behaves differently, I stop and return to the known-good state before trying another adjustment.

RouterOS exports can reveal internal addresses, port relationships and other sensitive information. I don't put raw `.rsc` or `.backup` files in this repository, even if the obvious password fields have been removed.

I use the [change notes](../../runbooks/network-change-procedure.md) before making adjustments and the [recovery notes](../../runbooks/network-recovery.md) when something goes wrong.
