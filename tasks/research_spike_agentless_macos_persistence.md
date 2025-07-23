# 🍎 Research Spike: Agentless macOS Persistence

**Goal:**  
Catalog and test obscure macOS persistence mechanisms that do not rely on agents or noisy payloads — such as LaunchAgents quirks, LoginItems database injection, TCC.db tampering, and Apple Shortcuts automation misuse. Identify which ones bypass standard EDR or MDM controls.

**Why It Matters:**  
macOS fleets in the enterprise are growing, yet most red team and detection engineering efforts still prioritize Windows. These lesser-known persistence paths are frequently unmonitored and misunderstood, enabling stealthy access or long-term footholds on dev or exec endpoints.

---

### 🔍 Scope
- macOS native persistence vectors:
  - `~/Library/LaunchAgents/*.plist` (misconfigured or renamed)
  - `~/Library/Application Support/com.apple.backgroundtaskmanagementagent`
  - LoginItems database (`~/Library/Application Support/com.apple.backgroundtaskmanagementagent/backgrounditems.btm`)
  - Apple Shortcuts (trigger automation via network, time, or login)
  - TCC database tampering (`~/Library/Application Support/com.apple.TCC/TCC.db`)
- Exclusions:
  - Kernel extensions (requires root; noisy)
  - Known backdoor malware techniques already documented in AV signatures

---

### ✅ Tasks
- [ ] Set up clean macOS VM (Ventura or Sonoma recommended)
- [ ] Enumerate and test persistence via:
  - Custom LaunchAgents with nonstandard keys or plist obfuscation
  - Direct LoginItems DB manipulation (SQLite)
  - Shortcuts automation to re-launch apps or connect to C2
  - TCC privilege escalation (e.g., Terminal with Full Disk Access)
- [ ] Observe detection by:
  - macOS built-in logging (Unified Log, Console)
  - Commercial EDRs (if available)
- [ ] Package results into:
  - Red team setup scripts
  - YAML-based detection rules (for macOS log agents or Splunk configs)
  - Validation checklist (manual and scripted)

---

### 🎯 Deliverables
- Persistence technique catalog (description, path, detection notes)
- Setup PoC scripts (written in Bash, Swift, or Python)
- Example Apple Shortcuts with malicious behavior triggers
- YAML detection rules for:
  - Unusual LaunchAgent behavior
  - BackgroundItems DB anomalies
  - TCC.db modification attempts
- Red team runbook with opsec notes:
  - Noise level
  - Privilege requirements
  - AV/EDR detection history

---

### 📚 Reference Materials
- Patrick Wardle’s macOS Persistence Research: https://objective-see.org  
- LaunchAgent Reference: https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLaunchdJobs.html  
- TCC Database Primer: https://github.com/josephb/disable-tcc  
- Apple Shortcuts Automations: https://support.apple.com/guide/shortcuts/welcome/ios  
- MITRE ATT&CK T1547.013 (macOS Launch Agent): https://attack.mitre.org/techniques/T1547/013/  
- ATT&CK T1546.014 (Login Items): https://attack.mitre.org/techniques/T1546/014/  

---

### 🏷️ Tags / Labels
`macos` `persistence` `launchagents` `loginitems` `tcc` `shortcuts` `t1547.013` `t1546.014` `agentless` `low-noise` `mdm-evasion`

---

### 📈 Effort Level
**Medium (M)** — requires macOS access, scripting, and persistence knowledge.

---

### ✅ Acceptance Criteria
- [ ] At least 3 persistence methods tested on macOS (agentless)
- [ ] Detection coverage for each technique documented (EDR/no EDR)
- [ ] PoC scripts included in repo or wiki
- [ ] Red team notes and blue team detections written
- [ ] Final checklist and YAML rules added to toolkit