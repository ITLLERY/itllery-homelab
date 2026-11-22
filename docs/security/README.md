# What I publish and what I keep private

I want the repository to show how the lab works without giving away the details someone would need to connect to it. The aim is to share useful setup notes, decisions and test results, not a full map of my home network.

## What I share

I publish the roles of the machines, the reasoning behind the network design and the commands or settings that I have tested and can explain safely. When I have relevant screenshots or logs, I review them first. For examples that need an IP address, I use documentation ranges rather than my actual network.

I also share mistakes and fixes. A failed test can be useful if I explain what happened and how I checked the result.

## What stays private

I don't publish real IP and VLAN plans, switch ports, cabling, management paths, firewall exceptions or full MikroTik, TP-Link, Proxmox and WireGuard exports. Credentials, API tokens, encryption keys, recovery codes, backup placement and exact internal host identifiers also stay out of GitHub.

I don't upload real malware samples, unreviewed packet captures, private forensic data or screenshots showing sensitive information. The full asset register and working topology belong in secure local documentation.

## Before I push

I read the Markdown, commands, configuration examples and screenshots again for anything private. I check the Git diff and look for secrets; `.gitignore` doesn't catch every mistake. I also make sure the page doesn't describe a planned feature as a completed test.

If I ever expose a real secret, removing it from the latest file isn't enough. I have to revoke or rotate it and deal with the Git history as needed.

This approach lets me document the work without publishing details that would put the lab at risk.
