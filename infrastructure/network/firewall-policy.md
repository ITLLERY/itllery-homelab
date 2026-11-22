# Firewall rules and checks

**Document:** NET-SEC-001  
**Baseline:** 2026-11-21

I use a default-deny approach for traffic between different network zones. If two systems need to communicate, I want a clear reason for allowing that connection. Return traffic for established connections is handled as part of the stateful rules, but I still have to consider the endpoint firewall and switch configuration.

During the November rebuild I checked selected drop-rule counters and the final deny behaviour. That told me some unwanted traffic was being blocked. It wasn't a complete review of every rule or every possible network path.

## The access rules I aim for

The examples below describe my intended policy. They aren't the actual firewall entries from my router.

| Example source category | Example destination category | Design outcome | Reason |
| --- | --- | --- | --- |
| Approved administrator | Managed service | Restricted allow | Named administrative task only |
| General work endpoint | Risky test environment | Deny by default | Avoid unnecessary trust |
| Untrusted analysis environment | Private work systems | Deny | Protect higher-trust systems |
| Authorized service | Required dependency | Restricted allow | Explicit functionality |
| Other/undocumented traffic | Any protected zone | Deny | No implicit access |

This table is illustrative and **must not be interpreted as current access paths**. The actual source/destination pairs and protocols are kept offline.

## What I check when changing a rule

I first decide whether the traffic is meant for the router itself (**input**) or is passing through it (**forward**). Then I look at the rule order, connection states, interface or address-list scope and any exceptions. IPv4 and IPv6 need separate attention where both are available.

After a change, I test from the relevant endpoint. One connection should be allowed because it is needed; another should fail because the policy denies it. I check counters and logs for that particular test period rather than relying on old hits. I also consider fast-path behaviour, especially when I'm trying to observe traffic.

A successful browser connection doesn't prove that every other management path is closed. Likewise, a non-zero drop counter doesn't tell me that all unwanted traffic is blocked. I still need complete positive and negative tests for the intended zone boundaries.

I use [NIST SP 800-41 Rev. 1](https://csrc.nist.gov/pubs/sp/800/41/r1/final) as a reference for firewall policy. I keep the results in my [network validation notes](../../evidence/sanitized/network-validation.md).
