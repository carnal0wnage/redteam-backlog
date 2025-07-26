# 🧩 Research Spike: Create a Malicious IDE Plugin for Red Team Use

**Goal:**  
Build a proof-of-concept plugin for a commonly used IDE (e.g., Visual Studio Code, IntelliJ, Eclipse) that performs malicious actions when installed — such as credential theft, environment variable dumping, or staged payload execution.

**Why It Matters:**  
Developers are high-value targets and IDE plugins are trusted components. A malicious plugin can persist across reboots, exfiltrate secrets, or even be inserted in open-source dependency chains. This emulates realistic APT tactics for developer workstation compromise.

---

### 🔍 Scope
- Internal developer IDE of choice (e.g., VS Code, JetBrains IntelliJ)
- Plugin must be installable via standard marketplace or side-load method
- Payload: benign for demo (e.g., logging env vars or beaconing to localhost)

---

### ✅ Tasks
- [ ] Research plugin architecture and extension points
- [ ] Set up dev environment for chosen IDE
- [ ] Create minimal plugin skeleton with manifest
- [ ] Add malicious behavior:
  - [ ] Dump `process.env` to file
  - [ ] Log credentials from known files (`.npmrc`, `.aws/credentials`, `.git-credentials`)
  - [ ] Beacon host/user info to remote server (safe/localhost for PoC)
- [ ] Package and test install flow
- [ ] Document persistence mechanisms and trigger paths
- [ ] Optional: Add obfuscation or masquerading as a common tool

---

### 🎯 Deliverables
- PoC plugin source code and packaged extension file
- Plugin manifest with metadata and permissions
- Screenshot or logs of plugin execution
- Write-up on:
  - How plugin bypasses trust assumptions
  - Which IDE security features (if any) are triggered
- Developer awareness recommendations

---

### 📚 Reference Materials
- VS Code Extension API: https://code.visualstudio.com/api  
- JetBrains Plugin Dev Guide: https://plugins.jetbrains.com/docs/intellij/plugin-structure.html  
- MITRE ATT&CK:
  - T1059 – Command and Scripting Interpreter  
  - T1053.005 – Scheduled Task/Job: Scheduled Task  
  - T1546.008 – Implant via IDE Extension

---

### 🏷️ Tags / Labels
`ide-security` `developer-workstations` `malicious-plugins` `intellij` `vscode` `t1546.008`

---

### 📈 Effort Level
**Medium–High (M–L)** — requires plugin development skills and IDE internals familiarity.

---

### ✅ Acceptance Criteria
- [ ] Plugin installs and triggers on common IDE action (e.g., open, save)
- [ ] At least one data collection or execution behavior built in
- [ ] Plugin packaged and documented for red team use
- [ ] Report includes plugin metadata, code, and detection considerations
