# Networking

This is where I keep my MikroTik and TP-Link notes. I wanted the lab to have separate networks for normal work, administration, monitoring and security experiments, but getting those boundaries right takes more than just creating VLANs.

I write down why I changed something, what worked and what I still need to test. The real addressing plan, port assignments and full configurations stay in my private notes.

## Devices and settings

- [MikroTik routing and recovery](mikrotik.md)
- [TP-Link switch](tplink-switch.md)
- [Firewall rules and tests](firewall-policy.md)
- [Remote administration](remote-management.md)

## Design and results

- [Network overview](../../docs/architecture/network-overview.md)
- [Role diagram](../../docs/architecture/network-topology.md)
- [Network zones](../../docs/architecture/network-zones.md)
- [Current and planned checks](../../docs/architecture/as-is-vs-to-be.md)
- [How I prepare a network change](../../runbooks/network-change-procedure.md)
- [How I recover after a problem](../../runbooks/network-recovery.md)
- [Test notes](../../evidence/sanitized/network-validation.md)

During the November 2026 rebuild, I restored routing and several management paths. I still have work to do on the full switch review, zone isolation, the Security Onion mirror and a proper backup-restore test.
