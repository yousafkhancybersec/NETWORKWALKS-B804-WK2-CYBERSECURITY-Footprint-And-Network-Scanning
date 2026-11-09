# Week 02 Technical Report — Footprinting & Network Scanning

**Pentester:** Yousaf Shafi ullah Khan  
**Program / Batch:** B804-Networkwalks  
**Date:** 09 November 2026  
**Modules:** W2-PM1 (Multiple Kali Tools), W2-PM5 (Zenmap Scanning)  
**Instructor / source-report credit:** Waqas Karim CCIE

## 1. Scope and purpose

This Week 02 practical documents two activities: footprinting and reconnaissance of the `networkwalks.com` domain using Kali Linux tools, and network discovery using Zenmap in a local-network practical. The goal is to understand the types of information that can be collected during reconnaissance and host discovery, and how to document their security relevance.

The supplied report states that permission was secured for the target activity. All testing must remain within the authorized scope.

## 2. Tools and purpose

| Tool | Purpose |
|---|---|
| Kali Linux / Windows | Operating systems used in the practical |
| WHOIS | Review publicly available domain registration information |
| WhatWeb | Identify web technologies and exposed technology details |
| Nslookup | Resolve a domain name through DNS |
| Curl `-I` | Inspect HTTP response headers |
| Wafw00f | Identify whether a web application firewall is detectable |
| DNSRecon | Enumerate DNS records, including NS, MX, SPF/TXT and service records |
| Zenmap / Nmap | Discover live hosts and review network topology |
| Windows CMD | Identify local IP and MAC information during the lab |

## 3. Activities and observations

### 3.1 Footprinting and reconnaissance

The supplied practical report records the following observations from the six Kali Linux tools:

1. **WHOIS:** Public domain registration information and name-server details were reviewed.
2. **WhatWeb:** The report records WordPress 7.0.4 and WP Download Manager 3.3.58 among the identified technologies.
3. **Nslookup:** The report records the public IP address `192.232.216.135` for the domain.
4. **Curl:** HTTP response headers were inspected; the report notes the WordPress REST API endpoint `/wp-json/`.
5. **Wafw00f:** The report records detection of ModSecurity (SpiderLabs).
6. **DNSRecon:** DNS, mail, SPF/TXT and service-related records were enumerated.

These are observations recorded in the supplied practical report. They are not a live re-check of the domain and do not establish that the identified software is vulnerable or that the WAF blocks particular attacks.

### 3.2 Network scanning with Zenmap

The practical used Windows network configuration information to identify a local subnet, then used Zenmap's Ping Scan profile to discover active hosts. The supplied example reports four live hosts and a topology view.

Private subnet values, host IP addresses and MAC addresses are omitted from this public report. The screenshots in the source report represent practical-example evidence. Re-run the scan in your own authorized lab and replace example values before presenting them as independently verified results.

## 4. Risk analysis

| Observation | Potential security relevance | Indicative level |
|---|---|---|
| Web technology and version information was identifiable | Could help an attacker select technologies for further research; requires version and patch validation | Medium |
| Public service IP address was resolvable | Provides infrastructure context, but is not a vulnerability by itself | Low |
| HTTP headers and `/wp-json/` endpoint were observable | May assist further technology fingerprinting and enumeration | Low |
| WAF technology was identifiable | Reveals a detail of the web security architecture; detection does not prove effectiveness or weakness | Low |
| DNS, mail and service records were discoverable | Can help build an infrastructure profile | Medium |
| Multiple live hosts appeared in the Zenmap example | Unknown devices should be inventoried and checked against the approved asset list | Medium |

**Important:** Risk levels are preliminary indicators based on the observations recorded in the supplied practical. They are not CVSS scores or confirmed vulnerability ratings.

## 5. Recommendations

1. Review publicly exposed CMS, plugin and web-technology information.
2. Keep CMS platforms, plugins and supporting components updated; check current vendor advisories before drawing conclusions about versions.
3. Review HTTP response headers and remove unnecessary disclosures where appropriate.
4. Review DNS records periodically and remove obsolete or unnecessary records.
5. Review WAF configuration, logging and monitoring. The practical identified ModSecurity but did not test its blocking effectiveness.
6. Perform routine asset discovery on owned or explicitly authorized networks.
7. Investigate unknown devices and reconcile discoveries with the approved asset inventory.
8. Maintain current network topology and asset documentation.
9. Preserve written authorization and stay within the agreed testing scope.

## 6. Limitations

- The work covered information gathering and host discovery.
- No exploitation, vulnerability validation or intrusive testing was performed in these modules.
- A software version, public IP, DNS record, HTTP header or detected WAF does not independently prove a vulnerability.
- The local-network output is presented as example evidence in the supplied report; private identifiers are redacted.
- Findings should be revalidated through authorized testing before being used for remediation or risk decisions.

## 7. Conclusion

The Week 02 practical introduced a structured reconnaissance workflow using WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon, followed by local host discovery and topology review with Zenmap. The exercises reinforced the importance of distinguishing observable information from confirmed security weaknesses, documenting evidence, assigning proportionate risk, and keeping all testing within an authorized scope.

## Credits

Training program: NetworkWalks  
Instructor / source-report author credit: **Waqas Karim CCIE**
