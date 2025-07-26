# 🧬 Research Spike: Evaluate First Party Software Deployment Tools for Persistence or Privilege Escalation Opportunities

**Goal:**  
Analyze internal or enterprise-sanctioned software deployment tools (e.g., SCCM, Jamf, Intune, Munki, PDQ Deploy) for opportunities to achieve persistence or escalate privileges by abusing trusted deployment mechanisms, scripts, or configuration drift.

**Why It Matters:**  
Deployment tools often run with elevated permissions and are trusted by endpoint defense tools. This makes them attractive targets for red teamers seeking stealthy persistence or lateral movement across fleets.

---

### 🔍 Scope
- Enterprise software deployment platforms (SCCM, Intune, Jamf, Munki, PDQ Deploy, etc.)
- Both Windows and macOS environments
- Focus on non-destructive testing and simulation of persistence or privilege abuse

---

### ✅ Tasks
- [ ] Identify first-party or third-party software deployment tools in use
- [ ] Enumerate their install paths, scheduled jobs, update intervals, and trust models
- [ ] Examine:
  - [ ] Scriptable install/update flows (e.g., PowerShell, bash)
  - [ ] Custom app deployment profiles or triggers
  - [ ] Shared folders, credentials, or agent binaries
- [ ] Attempt persistence or escalation via:
  - [ ] Dropping payloads into trusted install paths
  - [ ] Overwriting install scripts or postflight actions
  - [ ] Creating fake update packages signed by internal CA
- [ ] Cross-reference with MITRE ATT&CK:
  - T1546 – Event Triggered Execution
  - T1053 – Scheduled Task/Job
  - T1055 – Process Injection
  - T1574 – Hijack Execution Flow

---

### 🎯 Deliverables
- Internal wiki or markdown doc with:
  - Tool-specific abuse paths and PoCs (if any)
  - Persistence technique matrix per tool
  - Risk assessment and visibility assumptions
- Screenshots or logs of successful exploitation (if non-destructive)
- Recommendations for monitoring or hardening those deployment flows

---

### 📚 Reference Materials
- SCCM Attack Surface: https://posts.specterops.io/
- Jamf Custom Triggers: https://learn.jamf.com/
- PDQ Deploy Docs: https://www.pdq.com/
- MITRE ATT&CK: https://attack.mitre.org/
- Intune Deployment Behavior: https://learn.microsoft.com/en-us/mem/intune/

---

### 🏷️ Tags / Labels
`persistence` `privilege-escalation` `sccm` `jamf` `intune` `deployment-tools` `t1053` `t1546`

---

### 📈 Effort Level
**Medium (M)** — requires access to test environments and admin tooling visibility.

---

### ✅ Acceptance Criteria
- [ ] At least 2 deployment tools evaluated for abuse opportunities
- [ ] One or more persistence or privilege escalation methods identified or disproved
- [ ] Documentation shared with internal red/blue/IT teams
