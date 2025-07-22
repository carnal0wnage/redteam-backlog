# ☁️ Research Spike: Living-Off-the-SaaS-Land (LOSL) TTP Library

**Goal:**  
Catalog how adversaries (or red teamers) can persist, move laterally, and exfiltrate data inside SaaS platforms using **native functionality** (no malware or implants). Platforms include Microsoft 365, Google Workspace, Slack, Atlassian, Notion, Zoom, and others.

**Why It Matters:**  
SaaS platforms are now core enterprise infrastructure — but often lack strong monitoring and centralized detection. LOSL techniques blend into normal user workflows, making them ideal for business email compromise (BEC), insider threat, or stealthy post-compromise access.

---

### 🔍 Scope

**Target SaaS Platforms:**
- M365 (Outlook, Power Automate, Teams, SharePoint, OneDrive)
- Google Workspace (Docs, Drive, Gmail, Apps Script)
- Slack, Zoom, Notion, Atlassian, GitHub, Box

**Abuse Categories:**
- Persistence: Auto-forward rules, webhook listeners, shared drive backdoors
- Lateral Movement: Shared calendar/phishing payloads, Slack token reuse
- Exfiltration: Auto-sync to personal cloud, export automations
- Covert Channels: Task comments, docs-as-chat, webhook relays

**LOSL Techniques Include:**
- Outlook inbox rules → exfil emails + forward OTPs (T1114.003)
- Power Automate → trigger on inbox event → write to OneDrive
- Google Apps Script → hidden Drive watchers or chat bots
- Slack workflows → auto forward DMs to attacker workspace
- GitHub Actions → credential leak via CI logs
- Notion integrations → data sync to attacker-owned Notion DB

---

### ✅ Tasks

- [ ] Inventory LOSL-capable features across key platforms
- [ ] Build demo payloads using:
  - Power Automate, Google Apps Script, Slack Workflow Builder, etc.
- [ ] Emulate realistic post-compromise scenarios:
  - Phished mailbox → persistence + silent data exfil
  - Insider w/ notion or Atlassian access → doc/comment exfil
- [ ] Map techniques to MITRE ATT&CK (enterprise SaaS / cloud)
- [ ] Develop blue team detections:
  - Defender / M365 audit logs, GWS Admin console, Okta, SIEM
- [ ] Document potential blind spots in each SaaS platform

---

### 🎯 Deliverables

- LOSL TTP Matrix:
  - Platform / Technique / MITRE Mapping / Risk / Detection / Status
- Demo Payloads:
  - Scripts, workflows, rule configs, tokenized API calls
- Detection Queries:
  - KQL (Defender), GWS log filter rules, Okta/Splunk examples
- Recommendations:
  - SaaS config hardening (disable risky features, enforce OAuth scopes)
  - User behavior baselines
  - Unified SaaS activity correlation (via CASB/XDR/SIEM)

---

### 📚 Reference Materials

- MITRE ATT&CK:  
  - [T1114.003 – Email Collection: Email Forwarding Rule](https://attack.mitre.org/techniques/T1114/003/)  
  - [T1059.005 – Command and Scripting Interpreter: Visual Basic for Applications]  
  - [T1098 – Account Manipulation]  
- Red Canary SaaS TTP Library  
- M365 Audit Logs: https://learn.microsoft.com/en-us/microsoft-365/compliance/search-the-audit-log  
- Google Workspace Admin Logs: https://support.google.com/a/answer/4580176  
- Slack Security Best Practices: https://slack.com/intl/en-gb/blog/security/slack-security-best-practices

---

### 🏷️ Tags / Labels
`saas-abuse` `losl` `m365` `google-workspace` `slack` `insider-threat` `exfiltration` `cloud-lateral-movement` `no-malware` `tt1114.003` `tt1098` `tt1059`

---

### 📈 Effort Level
**Large (L)** — wide surface area across multiple platforms; may need inter-team coordination for lab access.

---

### ✅ Acceptance Criteria

- [ ] At least 10 SaaS-native attack techniques cataloged across 3+ platforms  
- [ ] All TTPs mapped to MITRE and linked to relevant detection logic  
- [ ] Demo workflows/payloads created for at least 3 platforms  
- [ ] Sigma/KQL/Log queries developed for common abuse paths  
- [ ] Deliverables uploaded to shared threat repo or Confluence