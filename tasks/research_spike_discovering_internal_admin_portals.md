# 🕵️‍♂️ Research Spike: Discovering Internal Admin Portals

**Goal:**  
Find internal admin interfaces, dashboards, dev tools, legacy panels, and exposed middleware UIs that are accessible on the internal network. Catalog their type, authentication model, versioning, and attack surface.

**Why It Matters:**  
Internal admin UIs often have poor access control, default creds, or known exploits. They're high-value targets for lateral movement, data access, or command execution, and are frequently overlooked during external-facing assessments.

---

### 🔍 Scope

**Target Portals:**
- Web-based interfaces on non-standard ports (`:8080`, `:8443`, `:8888`, etc.)
- Default dashboards (Tomcat Manager, Jenkins, Grafana, Kibana)
- Shadow apps (devtools, forgotten UIs)
- Router/switch interfaces, appliance panels
- IoT or camera admin UIs
- K8s dashboards, internal cloud consoles, admin APIs

---

### ✅ Tasks

- [ ] Internal network scan for HTTP(S) services:
  - Use `nmap`, `masscan`, `httpx`, `naabu`
- [ ] Passive DNS + SSL cert collection:
  - Grep for `admin`, `dashboard`, `internal`, `manage`, etc.
- [ ] Scan web content with:
  - `httpx`, `gowitness`, `aquatone`, `eyewitness`
- [ ] Detect known panels via:
  - `nuclei` templates, favicon hashing, and `whatweb`
- [ ] Build classification:
  - URL, tech stack, version, login method, authz level
- [ ] Cross-reference with asset inventory or CMDB

---

### 🎯 Deliverables

- Portal Inventory Spreadsheet:
  - URL/IP / Title / Auth Type / Risk / Screenshot
- List of default or unauthenticated UIs
- Screenshot pack (e.g., via `gowitness`)
- Recommendations:
  - Add auth or IP restrictions to exposed interfaces
  - Alert asset owners to orphaned dashboards
  - Register with asset inventory or monitoring system

---

### 📚 Reference Materials

- `httpx`, `gowitness`, `aquatone`, `nuclei`
- Favicon hash search: https://github.com/devanshbatham/FavFreak  
- Shodan-style local index: use favicon hash + `httpx`
- MITRE T1046: Network Service Scanning

---

### 🏷️ Tags

`internal-recon` `admin-panel` `shadow-ui` `dashboard` `httpx` `nmap` `nuclei` `t1046` `web-scan`

---

### 📈 Effort Level

**Medium (M)** — ideal for junior or mid-level red teamers building recon muscle and tool fluency.

---

### ✅ Acceptance Criteria

- [ ] At least 10 admin portals discovered on lab or internal net  
- [ ] Each portal documented with title, path, screenshot, version  
- [ ] Default or weak-auth interfaces highlighted  
- [ ] All output stored in central recon wiki or internal repo  
- [ ] Nuclei or detection rules added for repeat use