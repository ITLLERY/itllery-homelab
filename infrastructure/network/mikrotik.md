# MikroTik | Routing, Policy and Recovery

**Document ID:** NET-PLAT-001 | **Revision:** 1.0 | **Baseline:** 2026-11-21 | **Classification:** PUBLIC

## Platform role

The MikroTik hAP ax² is the lab's routing and policy platform. I use it to study how switching, VLANs, inter-zone policy, administrative exposure and rollback behave together. Actual RouterOS configuration and management details are private.

## Recovery baseline

The November 2026 session involved recovery of the router and re-establishing routine network connectivity. Router management was reached, VLAN-filtering state was inspected, and selected firewall behavior was reviewed. The project record also confirms creation of a configuration export and a backup artifact.

**What this proves:** A functioning baseline was recovered and inspected. **What it does not prove:** Every rule is correct, every VLAN is isolated, and the stored backup can be restored on demand.

## Configuration domains to track privately

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

## Change-control requirements

1. Capture the current state into **private** storage before editing.
2. Identify the single planned change and its potential management impact.
3. Confirm recovery access and define a rollback before applying.
4. Apply in a bounded maintenance session; avoid simultaneous router and switch changes.
5. Test approved access **and** forbidden access, with negative test cases.
6. Record the result and private artifact identifiers; publish sanitized conclusions only.

## Security of exports

RouterOS exports and backups can expose private topology, identifiers and potentially sensitive values. No raw `.rsc` or `.backup` file belongs in this public repository. File mode and storage location, secret handling and restore credentials are documented privately. Simply removing a password line does not make a complete export safe to publish.

See [change runbook](../../runbooks/network-change-procedure.md) and [recovery runbook](../../runbooks/network-recovery.md).
