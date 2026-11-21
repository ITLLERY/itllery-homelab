# Remote Administration | Access and Recovery Design

**Document ID:** NET-SEC-002 | **Revision:** 1.0 | **Baseline:** 2026-11-21 | **Classification:** PUBLIC

## Objective

Administration should be possible for authorized operations without creating an unnecessary general-purpose entry point into the lab. The lab uses controlled management and WireGuard-based administration. The real topology, peer definitions and reachable interfaces remain private.

## Session observations

During the November restoration, authorized router-management access and WireGuard administration were reported functional. The two Proxmox management web interfaces were accessible from the approved working context. Command-line administration of infrastructure systems is expected to use a controlled administrative path rather than unrestricted access.

These observations are limited to the methods and circumstances tested; they are not proof that all alternative management paths are closed.

## Control objectives

- Use individual administrative credentials and avoid shared or publicly documented secrets.
- Limit exposure of SSH, HTTPS/management services and remote administration to approved contexts.
- Maintain a record of authorized VPN peers and promptly remove lost or obsolete peers.
- Review the device and endpoint sides of access policy; a router allowlist alone is not enough.
- Maintain an independent recovery approach that does not depend on the same failing network path.
- Record administrative changes and periodically validate access restrictions.

## Validation cases

| ID | Acceptance question | Required evidence |
| --- | --- | --- |
| ADM-01 | Can an authorized administrator reach the required management interface? | Successful authorized access and exact test date |
| ADM-02 | Is the same service inaccessible from a disallowed context? | Negative connection test and filtering observation |
| ADM-03 | Can a revoked or disabled VPN peer no longer connect? | Controlled revocation drill |
| ADM-04 | Is the approved rescue method available when normal management fails? | Controlled recovery exercise |

## Public documentation boundary

I do not publish peer keys, real endpoint addresses, SSH destinations, recovery access paths, authentication methods tied to my devices or detailed management ACLs. Examples in this repository are schematic, not copy-and-paste live access instructions.
