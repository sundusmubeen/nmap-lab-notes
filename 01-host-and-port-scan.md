# Lab 01 — Host discovery and port scan

**Environment:** Isolated virtual lab  
**Tool:** Nmap  
**Goal:** Identify live hosts, open ports and services, then document remediation ideas

## Scope

- Targets: lab VMs on a private virtual network
- Authorisation: own lab environment only

## Method

1. Host discovery to find live systems
2. TCP port scan on discovered hosts
3. Service/version detection on open ports
4. Light NSE scripts where safe for the lab
5. Write findings with severity and next steps

### Commands used (examples)

```bash
# Host discovery
nmap -sn 192.168.56.0/24

# Port and service scan (lab host example)
nmap -sS -sV -O -T4 192.168.56.10

# Safer script category for extra context
nmap -sV --script=default 192.168.56.10
```

## Findings

| ID | Finding | Severity | Evidence | Recommendation |
| --- | --- | --- | --- | --- |
| F1 | Multiple unused services listening | Medium | Open ports beyond required lab roles | Disable unused services; restrict with host firewall |
| F2 | Service banners expose version info | Low | `-sV` output showed product/version strings | Keep software patched; reduce banner detail where practical |
| F3 | Management ports reachable on lab LAN | Medium | SSH/HTTP open to whole subnet | Limit access with firewall rules and stronger auth |

## Risk notes

- Findings are from a training lab, not a production assessment.
- Severity is indicative and used to practice prioritisation.

## What I learned

- Start wide (discovery), then go deep (ports/services).
- Raw scan output is not enough — a short table with remediation is more useful to stakeholders.
- Documenting method and scope matters as much as the technical result.
