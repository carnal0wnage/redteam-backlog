
## 🖥️ Research Spike: Create VMs for Each Corporate-Supported Operating System

**Goal:**  
Build virtual machines for each corporate-supported OS (Windows, macOS, Ubuntu, etc.) with standard security tooling installed. These VMs will serve as controlled testbeds for red team payload testing, detection validation, and behavioral analysis.

**Why It Matters:**  
Having clean, standardized VM environments that match the enterprise’s real-world OS deployments enables more realistic red team testing and speeds up validation workflows. Preloading with corporate EDR and endpoint tooling increases detection signal fidelity.

---

### 🔍 Scope
- Supported operating systems:
  - Windows 10/11 Enterprise
  - macOS (latest version used in corp)
  - Ubuntu (or preferred Linux distro)
- Include all default corporate security tools:
  - EDR/AV agents (e.g., CrowdStrike, Defender, SentinelOne)
  - VPN clients, monitoring agents, DLP software
- Optional: Join to test domain or simulate SSO setup

---

### ✅ Tasks
- [ ] Collect requirements:
  - Corporate image or base ISO for each OS
  - List of mandatory security/monitoring tools
- [ ] Provision VMs using:
  - VirtualBox, VMware, Parallels, or cloud-based sandbox
- [ ] Install:
  - OS updates and packages
  - Corporate EDR + logging agents
  - Email, browsers, and productivity apps as needed
- [ ] Validate:
  - Tools are operational and report to central console
  - VMs boot cleanly and are snapshot-ready
- [ ] Create backup snapshot for easy reset

---

### 🎯 Deliverables
- VMs for each supported OS:
  - .ova or VMX/VMware files
  - Documented setup scripts or install checklist
- Snapshot image labeled "clean baseline"
- Readme with:
  - Login creds
  - Installed tools
  - Known issues or limitations
- Optional: Join to test AD or local DNS for more realism

---

### 📚 Reference Materials
- Windows Virtualization Docs: https://learn.microsoft.com/en-us/virtualization/  
- macOS VM Setup (UTM/Parallels): https://mac.getutm.app/  
- Ubuntu VM Installation: https://ubuntu.com/tutorials  
- VirtualBox: https://www.virtualbox.org/  
- EDR product guides for silent installs and verification

---

### 🏷️ Tags / Labels
`vm-lab` `windows` `macos` `linux` `edr-testing` `test-env` `junior-friendly`

---

### 📈 Effort Level
**Medium (M)** — setup is straightforward but tooling installation can be time-consuming.

---

### ✅ Acceptance Criteria
- [ ] VMs created for each OS used by the org
- [ ] All corporate security tools installed and reporting
- [ ] Snapshot created of clean baseline
- [ ] Internal guide/checklist uploaded to wiki or repo
