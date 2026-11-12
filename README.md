# Week 2: Footprinting & Network Scanning

**Author:** Takudzwanashe Musere
**Program:** Cybersecurity & Ethical Hacking, Networkwalks 
**Modules:** W2-PM1 (Multiple Kali Tools) and W2-PM5 (Zenmap Scanning)

> For educational purposes only. All activities were done only on
> systems I have written permission to test (the Networkwalks lab target)
> or devices I own (my home network).

## What this project covers

### Phase 1: Reconnaissance & Footprinting (W2-PM1)
Target: `networkwalks.com` (authorised lab target), from Kali Linux.

| Tool | Command | What it showed |
|---|---|---|
| WHOIS | `whois networkwalks.com` | Registrar, dates, name servers (HostGator) |
| WhatWeb | `whatweb networkwalks.com` | WordPress 7.1.4, WP Download Manager 3.3.76, Apache |
| Nslookup | `nslookup networkwalks.com` | IP address 192.232.216.135 |
| Curl | `curl -I https://networkwalks.com` | HTTP headers, `/wp-json/` endpoint |
| Wafw00f | `wafw00f networkwalks.com` | ModSecurity (SpiderLabs) WAF |
| DNSRecon | `dnsrecon -d networkwalks.com` | NS, MX, SPF/TXT and SRV records |

### Phase 2: Scanning & Network Discovery (W2-PM5)
Target: my own home LAN, from Windows with Zenmap.

- Local subnet identified with `ipconfig`: `192.168.1.0/24`
- Scan: `nmap -sn 192.168.1.0/24` (ping scan)
- Result: 15 live hosts, with IPs and MAC addresses recorded
- Network topology saved as a PDF

## Key learnings
- Public information alone reveals a lot about a target's technology and hosting.
- Exposed version and header information helps attackers fingerprint a system.
- Many modern phones use randomised MAC addresses, so Nmap shows the vendor as "Unknown".
- Findings here are observations, not confirmed vulnerabilities. No exploitation was performed.

## Repository contents
- `report/`: final penetration testing report
- `outputs/`: saved tool output (`1_whois.txt`, `2_whatweb.txt`, and so on)

## Disclaimer
These materials are for education and research only. Do not use anything
here to break the law. Unauthorised access is a crime in most countries.
