# Network Infrastructure

This section documents how I design, operate and validate the ITLLERY lab network. **All public pages are sanitized**: no live addresses, exact VLAN numbers, physical port maps, management entry points or raw configuration exports.

## Network platform

- [MikroTik: routing, policy and recovery](mikrotik.md)
- [TP-Link: switching and monitoring design](tplink-switch.md)
- [Firewall policy and validation](firewall-policy.md)
- [Remote administration](remote-management.md)

## Architecture and operations

- [Network infrastructure overview](../../docs/architecture/network-overview.md)
- [Conceptual network role map](../../docs/architecture/network-topology.md)
- [Trust zones](../../docs/architecture/network-zones.md)
- [Current vs target state](../../docs/architecture/as-is-vs-to-be.md)
- [Controlled change procedure](../../runbooks/network-change-procedure.md)
- [Network recovery procedure](../../runbooks/network-recovery.md)
- [Sanitized validation register](../../evidence/sanitized/network-validation.md)

**As of 2026-11-21:** Routing and selected administration were restored; the switch audit, full segmentation matrix, SPAN capture and complete backup-restore exercise still have open items.
