# Week 02 — Footprinting & Network Scanning

**Author:** Yousaf Shafi ullah Khan  
**Program / Batch:** NetworkWalks — B804  
**Report date:** 09 November 2026  
**Instructor credit:** Waqas Karim CCIE

## Project overview

This repository documents the Week 02 cybersecurity practical covering:

- **W2-PM1 — Footprinting & Reconnaissance:** WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon.
- **W2-PM5 — Network Scanning:** Zenmap/Nmap host discovery, local network identification and topology review.

The activities demonstrate how public domain information and authorized host-discovery techniques can support an initial understanding of an environment.

## Repository contents

- [Technical report (Markdown)](reports/WK2-Footprinting-and-Network-Scanning.md) — methodology, supplied observations, risk considerations, recommendations and limitations.

## Key observations recorded in the supplied practical

- WhatWeb identified WordPress 7.0.4 and WP Download Manager 3.3.58.
- Nslookup returned the public address 192.232.216.135 for the target domain.
- Curl inspection showed HTTP response headers and the `/wp-json/` endpoint.
- Wafw00f identified ModSecurity (SpiderLabs).
- DNSRecon returned DNS, mail and service-related records.
- The supplied Zenmap example showed four live hosts; private LAN identifiers are intentionally redacted in the public documentation.

These are observations from the supplied practical report, not claims that the target currently has a vulnerability. No exploitation or vulnerability validation was performed in these modules.

## Authorization and responsible use

All testing must remain within an explicitly authorized scope or systems owned by the tester. Do not scan third-party systems without permission. Findings in this repository are educational observations and should not be treated as confirmed vulnerabilities without further authorized validation.

## Evidence and privacy

Private LAN IP addresses, MAC addresses and other internal identifiers are redacted from public documentation. The Zenmap screenshots in the supplied report are practical-example evidence; re-run the activity in your own authorized lab before presenting example values as independently verified results.

## Credits

Training program: NetworkWalks  
Instructor / source-report author credit: **Waqas Karim CCIE**

This repository documents learning activities and does not imply endorsement by NetworkWalks or any third party.
