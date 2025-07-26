
# 📘 Research Spike: Assessing Jira & Confluence Security

**Goal:**  
Evaluate the security of internal Jira and Confluence instances using `J-PWN` or other JIRA/Confluence tools to identify misconfigurations, vulnerabilities, and over-permissioned access paths. This includes identifying accessible endpoints, exposed data, SSRF paths, and default credentials.

**Why It Matters:**  
Jira and Confluence are often deeply integrated into internal workflows and can expose a wealth of data and attack paths. Misconfigurations or old plugins can lead to SSRF, RCE, or credential leaks — all valuable to an attacker post-access or for privilege escalation.

---

### 🔍 Scope
- Internal Jira and Confluence instances (self-hosted, Atlassian-hosted optional)
- Authenticated and unauthenticated recon
- Versions in scope: Jira and Confluence Data Center / Server editions

---

### ✅ Tasks
- [ ] Clone and set up `J-PWN`:
  - https://github.com/carnal0wnage/J-PWN
- [ ] Use `Jira.py` to:
  - Identify project titles, users, and email addresses
  - Look for endpoint misconfigurations
- [ ] Use `Confluence.py` to:
  - Enumerate spaces, page titles, and authors
  - Identify indexed public documents
- [ ] Identify vulnerabilities or weaknesses such as:
  - Exposed user data or project metadata
  - SSRF via gadgets or webhooks
  - Default or misconfigured permissions
- [ ] Cross-reference findings with:
  - Known Jira/Confluence CVEs
  - MITRE techniques like T1210 (Exploitation of Remote Services)
- [ ] Optional:
  - Test for login page issues: weak auth, default creds
  - Analyze plugin exposure or vulnerability (especially ScriptRunner)

---

### 🎯 Deliverables
- Summary report or wiki page with:
  - Jira + Confluence version info
  - Output from J-PWN modules (screenshots, findings)
  - Table of misconfigurations or weak auth flows
  - Recommendations to:
    - Harden public pages and user visibility
    - Patch vulnerable versions
    - Enable tighter auth controls
- Optional: custom J-PWN modules or enhancements

---

### 📚 Reference Materials
- J-PWN GitHub: https://github.com/carnal0wnage/J-PWN  
- CVE archives for Atlassian Jira and Confluence  
- Atlassian Security Advisories: https://confluence.atlassian.com/security  
- MITRE ATT&CK: https://attack.mitre.org/techniques/T1210/

---

### 🏷️ Tags / Labels  
`jira` `confluence` `internal-recon` `webapps` `misconfig` `atlassian` `t1210`

---

### 📈 Effort Level  
**Medium (M)** — requires access to Jira/Confluence environments and tooling familiarity.

---

### ✅ Acceptance Criteria
- [ ] J-PWN executed successfully against both Jira and Confluence
- [ ] Version, project, and user enumeration complete
- [ ] At least 3 misconfigurations or overexposures identified
- [ ] Remediation recommendations documented and shared
