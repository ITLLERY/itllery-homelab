# ADR-0001: Why I separated the network

**Decision:** Segmented network, restricted administration and a recovery path  
**Recorded:** 2026-11-21  
**Status:** Design decision; individual controls still need separate tests

## Why I made this choice

My lab contains normal workstations, servers, security tools and machines for controlled attack simulations. A flat network would be easier to set up, but it would also give those systems more access to each other than they need.

I also learned how disruptive a wrong network change can be. When routing or VLAN settings are wrong, management access can disappear along with the service I was trying to fix. I therefore want to check changes carefully and keep a separate way to recover.

## Decision

I'll divide the lab into zones based on function and risk. Access between them should be allowed only where there is a reason for it. Management services should be restricted, and changes to the router or switch should have a known rollback.

I check important changes twice before applying them and verify both allowed and blocked traffic afterwards. The real addressing, VLANs, firewall rules and rescue details stay in my private documentation.

## Other options I considered

| Option | Trade-off |
| --- | --- |
| Flat, unrestricted LAN | Easy initially, but poor isolation and harder-to-explain security boundaries |
| VLANs without policy validation | Helpful organization but not sufficient proof of isolation |
| Fully disconnected testing for every workload | Strong isolation for selected risks, but may prevent realistic monitoring exercises |
| Segmented network with strictly controlled exceptions | More configuration and testing effort; supports both learning and controlled telemetry |

## Trade-offs

The segmented design takes more work. I have to maintain access exceptions, keep private network records up to date and test the rules after changing them. Some higher-risk experiments may need stronger isolation than normal VLAN separation.

The same applies to monitoring: a mirror can only show the traffic it receives. I can't assume Security Onion sees every network without checking the packets and possible blind spots.

I track the actual progress in [current vs planned](../as-is-vs-to-be.md) and the [network validation register](../../../evidence/sanitized/network-validation.md). This decision record explains the approach; it isn't proof that everything has been implemented.
