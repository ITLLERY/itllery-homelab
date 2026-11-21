# Firewall Policy | Principles and Validation

**Document ID:** NET-SEC-001 | **Revision:** 1.0 | **Baseline:** 2026-11-21 | **Classification:** PUBLIC

## Policy model

I prefer an explicit allowlist model for cross-zone access: stateful return traffic is allowed where appropriate, approved communications receive narrowly scoped exceptions, and traffic without an approved reason is denied. Router-level rules are only one layer; endpoint firewalls and switch configuration also matter.

The project session showed selected drop-rule counters and review of the final deny behavior. This is **evidence of some effective blocking**, not a complete firewall audit.

## Illustrative intent (not the deployed rule set)

| Example source category | Example destination category | Design outcome | Reason |
| --- | --- | --- | --- |
| Approved administrator | Managed service | Restricted allow | Named administrative task only |
| General work endpoint | Risky test environment | Deny by default | Avoid unnecessary trust |
| Untrusted analysis environment | Private work systems | Deny | Protect higher-trust systems |
| Authorized service | Required dependency | Restricted allow | Explicit functionality |
| Other/undocumented traffic | Any protected zone | Deny | No implicit access |

This table is illustrative and **must not be interpreted as current access paths**. The actual source/destination pairs and protocols are kept offline.

## Firewall review checklist

1. Separate router-management (**input**) and transit (**forward**) policy assessment.
2. Inspect rule order, action, interface/address-list scope and connection-state handling.
3. Evaluate IPv4 and IPv6 independently where supported and enabled.
4. Review fast-path/acceleration behavior for consistency with filtering and observability goals.
5. Confirm that each approved exception has a real operational requirement.
6. Run endpoint-originated tests with time, expected result and observed result.
7. Check relevant counters/logs and ensure they correspond to the intended test traffic.
8. Test again after topology, route, firmware or peer changes.

## Evidence caveat

A nonzero drop counter does not prove the block applies to **every** source, protocol or alternative route. A successful GUI connection does not prove that other management exposure is absent. Both positive and negative tests are required.

Reference: [NIST SP 800-41 Rev. 1](https://csrc.nist.gov/pubs/sp/800/41/r1/final). See [the validation register](../../evidence/sanitized/network-validation.md).
