# Nmap Lab Notes

Educational write-ups from networking and vulnerability-assessment labs. Scans were run in controlled virtual environments only — not against production systems.

## What this repo shows

- How I plan a scan (host discovery → ports → service/version → scripts)
- How I record findings with severity and remediation notes
- How I turn raw Nmap output into a short, readable report

## Lab summary

| Lab | Goal | Outcome |
| --- | --- | --- |
| Host discovery | Identify live hosts on a lab subnet | Mapped reachable hosts before deeper scans |
| Port and service scan | Enumerate open ports and services | Documented likely attack surface and service versions |
| Script scan (safe) | Gather extra context with NSE scripts | Flagged misconfigurations for follow-up |

## Example findings (lab only)

See [`labs/01-host-and-port-scan.md`](labs/01-host-and-port-scan.md) for a full sample report.

High-level themes from the labs:

1. Unnecessary open services increased exposure — recommend closing unused ports.
2. Outdated banners helped identify likely software versions for patch review.
3. Clear documentation of evidence made remediation discussions easier.

## Tools

- Nmap
- Virtual machines (isolated lab network)
- Markdown notes for reporting

## Disclaimer

These notes are for learning and portfolio demonstration. Do not run scans against systems you do not own or do not have permission to test.
