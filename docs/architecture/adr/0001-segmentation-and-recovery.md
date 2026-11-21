# ADR-0001 | Segmentation, Restricted Management and Recoverability

**Status:** Accepted as design direction; individual controls are verified separately  
**Date:** 2026-11-21  
**Classification:** PUBLIC / SANITIZED

## Context

The laboratory combines routine work, virtualized services, detection tools and controlled security experiments. A flat network would create unnecessary paths between systems with different risk levels. An error in routing or switch configuration can also make the environment difficult to administer.

## Decision

I will organize systems by trust and function, apply explicit cross-zone access policy, restrict administrative services, and preserve a recoverable management path when making network changes. Changes should be planned, checked twice before application, validated from more than one vantage point and have a defined rollback.

The exact subnets, VLANs, interfaces, firewall rules, exceptions and recovery entry points remain in the private as-built documentation.

## Alternatives considered

| Option | Trade-off |
| --- | --- |
| Flat, unrestricted LAN | Easy initially, but poor isolation and harder-to-explain security boundaries |
| VLANs without policy validation | Helpful organization but not sufficient proof of isolation |
| Fully disconnected testing for every workload | Strong isolation for selected risks, but may prevent realistic monitoring exercises |
| Segmented network with strictly controlled exceptions | More configuration and testing effort; supports both learning and controlled telemetry |

## Consequences

- Requires continuous maintenance of zone intent, access exceptions and test coverage.
- A failure in switching or routing can impact management; recovery must be independently considered.
- High-risk experiments may require stronger physical or logical disconnection than ordinary segmented testing.
- Mirrored traffic offers observation only for paths it actually sees; routing, switch fabric and endpoint traffic can create blind spots.

## Verification

Implementation and test claims are tracked in [the baseline register](../as-is-vs-to-be.md) and [validation log](../../../evidence/sanitized/network-validation.md). This ADR records the decision, **not** a claim that all related safeguards are complete.
