# Remote administration

**Document:** NET-SEC-002  
**Baseline:** 2026-11-21

I need to reach the router and servers for administration without exposing those interfaces to every machine in the lab. I therefore keep management access restricted and use WireGuard for approved remote connections.

During the November recovery I confirmed authorized router and WireGuard access. I also reached the web interfaces of both Proxmox hosts. That tells me the approved access worked at the time; it doesn't prove that access is blocked from every other possible source.

## What I want to maintain

I use individual credentials, restrict management services to the intended contexts and keep track of which VPN peers should still have access. A lost or retired peer needs to be revocable. I also want an independent recovery method in case a routing or firewall mistake removes the normal management path.

Testing both sides matters. A management interface should work from an approved source and fail from a source that isn't allowed. I also need to test peer revocation and the rescue procedure separately rather than assuming they work.

## Tests I still want to document

| ID | Acceptance question | Required evidence |
| --- | --- | --- |
| ADM-01 | Can an authorized administrator reach the required management interface? | Successful authorized access and exact test date |
| ADM-02 | Is the same service inaccessible from a disallowed context? | Negative connection test and filtering observation |
| ADM-03 | Can a revoked or disabled VPN peer no longer connect? | Controlled revocation drill |
| ADM-04 | Is the approved rescue method available when normal management fails? | Controlled recovery exercise |

The real endpoints, peer keys, SSH destinations, rescue paths and management rules stay in my private documentation. The examples here explain the approach; they aren't instructions for connecting to my live systems.
