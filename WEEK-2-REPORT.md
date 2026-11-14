# PENETRATION TESTING REPORT
## FOOTPRINTING & NETWORK SCANNING PHASES
**W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS**

| | |
|---|---|
| **Pentester Name (Cybersecurity Professional)** | Blen Kesete |
| **Program/Batch** | B084 – NetworkWalks |
| **Date** | |
| **Modules completed** | W2-PM1 (Multiple Kali Tools)<br>W2-PM2 (GHDB Footprinting)<br>W2-PM3 (Maltego Footprinting)<br>W2-PM4 (theHarvester Footprinting)<br>W2-PM5 (Zenmap Scanning) |
| **Client/Target** | 1. NetworkWalks course domain<br>2. My own local LAN network<br>3. Public-source results reviewed in PM2 and PM4 |
| **Permission secured from client?** | PM1 repository includes a sample permission letter. Written approval is unverified. PM5 used my own local network. |
| **Phases covered** | Phase 1: Reconnaissance & Footprinting<br>Phase 2: Scanning & Network Discovery |

## 1. Liability Disclaimer

This report documents educational cybersecurity exercises. Active testing requires permission from the system owner and an agreed scope. The report records observations from footprinting and host discovery.

## 2. Introduction

This report covers my Week 2 NetworkWalks labs. I used Kali Linux for domain footprinting and search-source comparison, Maltego on Windows to map a relationship, and Zenmap on Windows to discover live hosts on my local Wi-Fi network. The screenshots in Section 8 show the evidence available from the module repositories.

## 3. Tools Used

| Tool | Purpose |
|---|---|
| Kali Linux & Windows | Operating systems used for the labs |
| WHOIS | Review domain registration and name servers |
| WhatWeb | Identify web technologies |
| nslookup | Resolve a domain name using DNS |
| curl | Inspect HTTP responses and redirects |
| WAFW00F | Identify signs of a web application firewall |
| DNSRecon | Review DNS and mail records |
| Google Hacking Database | Review indexed web-interface evidence |
| Maltego Graph Desktop | Visualize the relationship between a domain and a public contact |
| theHarvester | Compare search-source output |
| Zenmap (Nmap GUI) | Discover live hosts and view topology |
| Windows CMD | Check local IP and MAC information |

## 4. Activities Performed

### 4.1 Footprinting & Reconnaissance

**W2-PM1 — Multiple Kali Tools.** I used WHOIS to review domain registration and name servers. WhatWeb reported Apache and WordPress. I resolved the domain with nslookup, and DNSRecon returned the same address while also showing DNS and mail information. Curl showed an HTTP-to-HTTPS redirect. WAFW00F reported ModSecurity.

**W2-PM2 — GHDB.** I explored Google search operators (`intitle:`, `inurl:`, `site:`, and `filetype:`), documented ten Insecam camera listing references and ten mathematics PDF resources or collections, and organized the exercise into three parts: GHDB methodology, camera footprinting, and mathematics PDF footprinting. I reported viewing camera feeds through the listing pages; their current availability and access configuration were not independently verified. The mathematics results include university notes, open textbook pages, and catalogs. My [GHDB lab report](https://github.com/Blen-Kesete-IT/GHDB-Footprinting-lab) contains the clickable finding tables and explanations.

**W2-PM3 — Maltego.** The graph showed two entities and one link connecting the course domain to its publicly listed organization contact.

**W2-PM4 — theHarvester.** DuckDuckGo returned 27 raw host entries, zero IP addresses, and zero email addresses. Some entries appeared duplicated or malformed. The Baidu run reported server disconnections, and the multi-source run showed missing API-key warnings and source errors.

### 4.2 Network Scanning with Zenmap

I used Windows IP configuration to identify my local subnet. The selected Zenmap **Quick Scan** checked 256 addresses on my local Wi-Fi subnet and reported **3 hosts up**. The hosts were the gateway, my Windows computer, and one other device. Zenmap showed MAC addresses for the two remote devices. Windows IP configuration supplied my computer’s MAC address.

The topology view showed an additional address from a different subnet. I used the selected scan summary to confirm the count for this lab.

### 4.3 GHDB Footprinting — Three-Part Lab Findings

| Part | Activity | Findings and learning |
|---|---|---|
| 1 — GHDB methodology | Reviewed search operators and GHDB screenshot evidence | Learned how public indexing can help with passive reconnaissance without proving a vulnerability |
| 2 — Camera listings | Recorded ten clickable Insecam references; reviewed the existing webcam interface screenshot | Student-reported access to listing feeds highlights possible privacy risks; device addresses and credentials were not collected |
| 3 — Mathematics PDFs | Recorded ten entries for public PDF directories, lecture notes, and open textbooks | Learned to distinguish directory indexes from intentionally published educational resources; some textbook entries share a catalog page |

[View the complete GHDB footprinting findings, hyperlinks, and existing screenshots](https://github.com/Blen-Kesete-IT/GHDB-Footprinting-lab#part-1--ghdb-and-footprinting-method)

## 5. Risk Analysis / Impact

| # | Risk / Finding | Evidence / Observation | Potential Impact | Risk Level |
|---|---|---|---|---|
| 1 | Web technology information visible | WhatWeb reported Apache and WordPress | Reveals technologies for security review | ● Low |
| 2 | DNS infrastructure visible | WHOIS, nslookup, and DNSRecon returned public records | Reveals service and hosting relationships | ● Low |
| 3 | WAF technology identifiable | WAFW00F reported ModSecurity | Reveals part of the web security architecture | ● Low |
| 4 | Camera images visible while signed out | Supplied interface screenshot | Unintended access could expose imagery | ● Medium |
| 5 | Search-source data quality issues | Apparent duplicates, malformed entries, and source errors | Raw counts can overstate inventory coverage | ● Low |
| 6 | Live hosts visible on the local network | Zenmap reported three hosts up | Unfamiliar devices warrant inventory review | ● Low |

**Risk level key** ● Critical ● Medium ● Low

The table records potential impacts. Exploitation and vulnerability validation were outside the scope of these exercises.

## 6. Recommendations

- **Review public web and DNS information.** Keep software current and review which technical details and records need to be public.
- **Check camera access controls.** Confirm that the intended audience can access each view.
- **Validate search results.** Remove duplicate and malformed entries before using tool output in an inventory.
- **Maintain a local device inventory.** Compare discovery results with expected devices and document unfamiliar entries.

## 7. Conclusion

During Week 2, I completed five labs covering footprinting, reconnaissance, and network discovery. I compared DNS and web observations, reviewed indexed interfaces, mapped a public contact in Maltego, and documented how search-source errors affected theHarvester’s output. I used the selected Zenmap scan to confirm three live hosts on my local subnet and the topology view to understand how they were displayed.

## 8. Evidence Collected

### PM1 · Kali reconnaissance

![DNS lookup screenshot](evidence/03-nslookup.png)

![HTTP response screenshot](evidence/04-curl.png)

### PM2 · GHDB

The original screenshots below are preserved. The updated [three-part GHDB report](https://github.com/Blen-Kesete-IT/GHDB-Footprinting-lab) includes the camera and mathematics PDF findings tables with clickable links.

![Cropped GHDB entry metadata](https://github.com/Blen-Kesete-IT/GHDB-Footprinting-lab/raw/main/evidence/ghdb-entry.jpg)

![Cropped camera interface showing signed-out status](https://github.com/Blen-Kesete-IT/GHDB-Footprinting-lab/raw/main/evidence/webcam-interface.jpg)

### PM3 · Maltego

![Maltego graph with the course domain and organization contact entity](https://github.com/Blen-Kesete-IT/Maltego-Footprinting-lab/raw/main/screenshots/mantigo.jpg)

### PM4 · theHarvester

![DuckDuckGo result totals](https://github.com/Blen-Kesete-IT/TheHarvester-footprinting-lab/raw/main/evidence/results.jpg)

![API-key warnings and source connection errors](https://github.com/Blen-Kesete-IT/TheHarvester-footprinting-lab/raw/main/evidence/source-errors.jpg)

### PM5 · Zenmap

The [Zenmap evidence summary](https://github.com/Blen-Kesete-IT/zenmap-network-discovery-lab/blob/main/README.md#evidence) records 256 addresses checked and 3 hosts up. It also explains the additional address in the topology view.

**-End-**

## 👤 Author

Blen Kesete · NetworkWalks Cybersecurity, B084

## 📌 Project Information

**Program Name** · Cybersecurity program at NetworkWalks  
**Week** · 02  
**Repository** · [GitHub](https://github.com/Blen-Kesete-IT/networkwalks-week-2-recon)  
**Course Credit** · NetworkWalks  
**Mentor** · Waqas Karim CCIE

