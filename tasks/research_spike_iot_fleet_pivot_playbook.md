# 📡 Research Spike: IoT Fleet Pivot Playbook (Printers, Cameras, AV Gear)

**Goal:**  
Enumerate enterprise IoT and smart device management stacks (e.g., printers, conference room cameras, badge readers), then demonstrate potential pivot paths from those lower-privilege VLANs into production networks using credential reuse, exposed APIs, or misconfigurations.

**Why It Matters:**  
IoT devices often live on "isolated" networks but have weak default credentials, shared cloud management platforms, or poorly segmented trust relationships. Understanding this soft underbelly can help red teams and defenders close high-impact lateral movement paths.

---

### 🔍 Scope
- Printers (e.g., HP, Canon, Ricoh)
- Smart cameras / AV gear (e.g., Zoom Rooms, Poly, Logitech)
- Badge systems, projectors, digital signage
- IoT VLAN or restricted network zones (lab or staging environment)

---

### ✅ Tasks
- [ ] Identify and scan IoT targets using:
  - `nmap`, `masscan`, `shodan` (internal), `Naabu`, `Amass`
  - Ports: 80, 443, 515, 631, 9100, 8000–9000, 49152, etc.
- [ ] Build a device matrix:
  - Device type, IP, model/vendor, exposed ports, mgmt interface
- [ ] Attempt access using:
  - Default creds (admin:admin, root:1234, etc.)
  - Unauthenticated web interfaces
  - SNMP v1/2 or printer control protocols
- [ ] Explore pivot opportunities:
  - Shared SSO or cloud auth (e.g., Okta, Azure)
  - Internal DNS, routing, or hardcoded internal IPs
  - Credential reuse across printer → admin UI → prod app
- [ ] If lateral movement seems possible:
  - Attempt to relay auth (e.g., responder, mitmproxy)
  - Test outbound request support (proxy via device)
  - Check if device accepts firmware or script upload (safe test only)
- [ ] Write segmentation validation script:
  - Ping sweep or route trace from IoT VLAN to production IPs
  - Check ACLs and firewalls for segmentation bypass

---

### 🎯 Deliverables
- 📋 IoT Device Matrix:
  - IP, model, ports, auth method, risk level
- 🧪 Pivot Paths:
  - Example chains (e.g., Printer Admin → Shared SSO Token → Prod App)
- 🧰 Tooling Used:
  - nmap, dirsearch, hydra, SNMPWalk, browser-based testing
- 📄 Segmentation Test Script (bash or Python)
- 📸 Screenshots of UI access, creds reused, or management portals
- 🔐 Recommendations:
  - Device isolation
  - Default password rotation
  - Disable unused services (e.g., FTP, SNMP)
  - Firmware upgrade hardening

---

### 📚 Reference Materials
- Red Siege "Hacking Printers" Guide: https://redsiege.com/blog/hacking-printers-for-fun-and-profit/  
- Shodan IoT Hunting: https://www.shodan.io  
- Nmap Default Script Library: https://nmap.org/nsedoc/scripts/  
- OWASP IoT Top 10: https://owasp.org/www-project-internet-of-things/  
- MITRE ATT&CK T1200 (Hardware Additions): https://attack.mitre.org/techniques/T1200/  
- SNMP Testing Tools: `snmpwalk`, `snmp-check`, `onesixtyone`

---

### 🏷️ Tags / Labels
`junior-friendly` `iot` `pivoting` `lateral-movement` `segmentation` `printers` `cameras` `snmp`

---

### 📈 Effort Level
**Large (L)** — multi-phase project involving scanning, enumeration, potential lateral movement, and tooling/script creation.

---

### ✅ Acceptance Criteria
- [ ] At least 3 types of IoT devices scanned and documented
- [ ] Device matrix created with ports, interfaces, and access level
- [ ] One or more pivot scenarios documented (real or theoretical)
- [ ] Segmentation validation script created and tested
- [ ] Internal wiki or report created with screenshots, tool output, and remediation suggestions