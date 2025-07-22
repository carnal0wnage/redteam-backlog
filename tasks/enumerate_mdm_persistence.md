
# 🧬 Research Spike: Enumerate Persistence Opportunities in Corporate Managed Devices

**Goal:**  
Analyze corporate managed macOS and Windows devices to identify opportunities for achieving persistence via whitelisted paths, misconfigured profiles, or trusted software channels.

**Why It Matters:**  
Corporate Managed devices often have tight controls, but those same trusted mechanisms can be abused for long-term persistence. Red teams should understand how to emulate post-compromise persistence techniques in Corporate Managed environments without triggering detections prematurely.

---

### 🔍 Scope
- macOS and Windows endpoints under Corporate Management
- User and device profiles, enforced scripts, login items, LaunchAgents, software management
- Non-destructive testing only

---

### ✅ Tasks
- [ ] Identify Managed System Behavior:
  - Installed paths
  - Update frequency
  - Script and profile delivery mechanisms
- [ ] Enumerate allowed or auto-deployed persistence mechanisms:
  - LoginItems (macOS)
  - Scheduled Tasks or Services (Windows)
  - Whitelisted paths for apps and scripts
- [ ] Analyze profile trust models:
  - Which system agents are signed/trusted by default?
  - Are non-Apple signed apps deployed?
- [ ] Attempt the following:
  - [ ] Abuse of Jamf custom triggers or policies for post-exploitation tasks
  - [ ] Payload injection via allowed application paths (e.g., `/Applications`, `/Library`)
  - [ ] Persistence via modified plist files or pre-approved LaunchAgents
  - [ ] Schedule tasks that mimic valid management behavior
- [ ] Cross-reference with MITRE ATT&CK:
  - T1547 – Boot or Logon Autostart Execution
  - T1053 – Scheduled Task/Job
  - T1055 – Process Injection

---

### 🎯 Deliverables
- Table of corporate policies and bypass opportunities
- Proof-of-concept persistence techniques (safely demonstrated)
- Screenshots or logs confirming payload execution
- Recommendations for hardening and monitoring MDM-enrolled devices

---

### 📚 Reference Materials
- Jamf Scripting: https://learn.jamf.com/
- Microsoft Intune Docs: https://learn.microsoft.com/en-us/mem/intune/
- MITRE ATT&CK T1547: https://attack.mitre.org/techniques/T1547/
- Objective-See Tools (macOS): https://objective-see.org/
- Intune Persistence (Red Canary): https://redcanary.com/blog/

---

### 🏷️ Tags / Labels
`mdm` `macos` `windows` `persistence` `jamf` `intune` `t1547` `t1053`

---

### 📈 Effort Level
**Medium (M)** — requires access to a test MDM environment and some OS-specific knowledge.

---

### ✅ Acceptance Criteria
- [ ] MDM platform behavior mapped for at least 1 macOS and 1 Windows device
- [ ] At least 2 potential persistence vectors identified and validated
- [ ] Documentation shared with dev/IT security teams
