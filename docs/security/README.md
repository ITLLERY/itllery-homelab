# Public vs Private Lab Documentation

I want my work to be useful to viewers and recruiters without turning GitHub into a map of my real network.

## What I share

- High-level lab roles and public-safe hardware summaries
- Logical zone concepts, not actual connectivity
- Reviewed examples with documentation IP ranges and placeholder hostnames
- Tested setup steps and version information when needed to reproduce a project
- Sanitized screenshots, synthetic example data clearly labeled as synthetic, or reviewed real test evidence
- Detection rules, monitored data sources, false-positive notes and investigations
- Hardening, remediation, verification and lessons learned

## What stays private

- Real IP address plans, VLAN IDs, port-by-port cabling, switch SPAN ports and complete trust paths
- Full router, switch, firewall, Proxmox or WireGuard configuration exports
- Credentials, API tokens, passwords, keys, recovery codes and backup encryption details
- Exact management access methods, reachable endpoints, security exceptions and known unpatched weaknesses
- Actual malware payloads, exploitable live credentials, private packet captures and unreviewed forensic data
- Serial numbers, MAC addresses, private hostnames, backup placement, physical location or identifying metadata
- Spare equipment and internal asset tracking that do not help explain a project

## Before I publish a change

1. Check the code, config, Markdown, screenshots and metadata.
2. Replace real values with clear placeholders; use RFC 5737 example IP ranges where appropriate.
3. Make sure evidence is from my test and is labeled accurately. Never claim a planned lab is completed.
4. Check the staged diff and scan for secrets. Git ignore rules are not enough.
5. For a secret accidentally committed, revoke or rotate it; removing it from the latest file is not sufficient.

A full private inventory and live topology belong in secure local documentation, **not** in a public repository. I also avoid putting unredacted infrastructure secrets into my private GitHub repositories.

This repository documents what I can show safely, not every configuration detail of my lab.
