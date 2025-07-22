# 🖨️ Research Spike: Printer Hacking & Fleet Lateral Movement

**Goal:**  
Identify and exploit network-connected printers and multifunction devices (MFDs) to extract credentials, pivot to internal assets, or gain persistent access through print job injection, misconfigured services, or firmware abuse.

**Why It Matters:**  
Printers are often:
- Over-permissioned
- Poorly segmented
- Running outdated firmware
- Integrated with LDAP, SMTP, and file shares  
This makes them ideal footholds for lateral movement, recon, and persistence — especially in segmented networks (e.g., guest → corp).

---

### 🔍 Scope
- Targets:
  - HP JetDirect, Canon, Xerox, Ricoh, Lexmark, Kyocera MFDs
  - Print servers (Windows or CUPS)
  - IPP, JetDirect (9100), SNMP, HTTP admin panels
- Attack categories:
  - 📤 Info exfil: Scan-to-email / SMB shares
  - 🎯 Auth: Embedded LDAP/SMTP creds
  - 🧠 Memory scraping: Print job remnants, cached data
  - 🔁 Pivot: SSRF from printer, scan internal services
  - 🪲 Exploit: CVEs, exposed admin APIs, outdated firmware
  - 🔌 Physical: USB/SD attacks on MFDs

---

### ✅ Tasks
- [ ] Scan internal IP ranges for common printer ports:
  - 9100 (JetDirect), 631 (IPP), 161/162 (SNMP), 80/443
- [ ] Use tools like:
  - `PRET` (Printer Exploitation Toolkit)
  - `nmap` + NSE print-related scripts
  - `snmpwalk` to enumerate device details and creds
- [ ] Enumerate:
  - Exposed web admin portals (unauth or default creds)
  - Embedded credentials (LDAP, email)
  - Scan-to-SMB/FTP destinations
- [ ] Exploit:
  - Inject jobs via raw port 9100 or IPP
  - Exploit known CVEs (e.g., HP firmware bugs)
  - Abuse SNMP to dump memory or crash devices
- [ ] Test lateral movement:
  - SSRF from printer to internal web apps
  - Scan-from-device to fingerprint restricted segments
  - Phishing via embedded scan-to-email spoofing

---

### 🎯 Deliverables
- Printer asset list (IP, model, firmware, exposed services)
- Screenshots or logs of successful access or credential leaks
- PCAP of print job injection / exfil attempt
- Exploit PoC (e.g., via PRET or crafted print job)
- Recommendations:
  - Segment printer VLANs
  - Remove embedded creds
  - Restrict management panel access
  - Upgrade firmware and enable SNMPv3

---

### 📚 Reference Materials
- PRET Toolkit: https://github.com/RUB-NDS/PRET  
- MITRE ATT&CK T1210 (Exploitation of Remote Services): https://attack.mitre.org/techniques/T1210/  
- HP Printer CVEs: https://support.hp.com/us-en/document/ish_6308357-6308381-16  
- SNMP Tools & Hardening: https://wiki.wireshark.org/SNMP  
- CUPS Admin Guide: https://www.cups.org/doc/admin.html  

---

### 🏷️ Tags / Labels
`printer-hacking` `snmp` `jetdirect` `ipp` `pret` `scan-to-email` `t1210` `pivoting` `firmware` `lateral-movement`

---

### 📈 Effort Level
**Medium (M)** — network access + basic SNMP/HTTP/print knowledge required.

---

### ✅ Acceptance Criteria
- [ ] At least 2 exploitation paths validated (e.g., job injection, creds found)
- [ ] One printer leveraged for lateral or recon access
- [ ] Asset list and findings documented in shared drive
- [ ] Countermeasures and segmentation notes delivered
- [ ] Screenshots and PCAPs captured for wiki or report