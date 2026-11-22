# Making a network change

**Runbook:** RB-NET-001  
**Reviewed:** 2026-11-21  
**State:** Working procedure; full rehearsal not yet documented

I use this checklist when I change a firewall rule, route, VLAN or management setting. The goal is to avoid guessing my way through several changes and then not knowing which one caused a problem.

## Before I start

1. I write down what I want to change, which systems might be affected and what would make me stop.
2. I save the current configuration in private storage. I don't push router and switch exports to GitHub.
3. I check that the normal management connection works and that I have a separate recovery option.
4. I note which connections should work afterwards and which should remain blocked.
5. I compare the planned settings with my private network map **twice**. I try to check them from two different angles, such as the router and the affected endpoint.
6. I decide how to undo the change before applying it.

## While making the change

I change one thing at a time, particularly when routing or VLAN settings could affect management access. I avoid changing both ends of an important link at once unless I have a safe way to roll back.

Afterwards I test a permitted connection and a prohibited one. If the change affects DNS or another service, I check that too. I also make sure I can still reach the management interface. Firewall counters and logs only help if I can relate them to the test I just performed.

If the results aren't what I expected, I stop and restore the previous working state instead of adding more changes on top.

## After the change

Once the expected behaviour is confirmed, I update the private rule, port or addressing records and keep the new baseline. I can then publish a short, redacted note describing what changed and what I tested. If something remains uncertain, I add it to the open work list.

## Change record

| Field | Required entry |
| --- | --- |
| Change ID | `CHG-YYYY-NNN` |
| Requested outcome | What and why |
| Risk | What can fail or become reachable |
| Pre-change evidence | Private reference only |
| Rollback trigger and method | Private operational detail |
| Positive/negative tests | Expected vs observed |
| Outcome | Passed / failed / reverted / inconclusive |
| Follow-up | Owner and action |

I don't deliberately lock myself out of a live router just to produce a screenshot or a demonstration.
