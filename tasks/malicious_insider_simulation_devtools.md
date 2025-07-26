# 🧑‍💻 Research Spike: Simulate a Malicious Insider with Dev Tool Access

**Goal:**  
Simulate a low-priv insider with access to internal dev tools (Jenkins, GitHub, Jira) and attempt escalation to code execution or secret access.

**Why It Matters:**  
Many orgs treat dev tools as low-risk, but insiders often exploit loose permission models. Simulating this helps defend against real-world insider threats and 3rd-party supply chain abuse.

---

### 🔍 Scope
- Jenkins, GitHub, GitLab, Bitbucket, Jira
- User: “Read-only” repo access, or access to issue tracking

---

### ✅ Tasks
- [ ] Map access scope of target identity
- [ ] Enumerate exposed endpoints:
  - Jenkins build scripts
  - GitHub Actions
  - Secrets in issues
- [ ] Chain:
  - Repo access ➝ Code execution
  - Issue access ➝ Token reuse
- [ ] Document findings + replay path

---

### 🎯 Deliverables
- Report of findings
- Replay steps for blue team
- Screenshots or token grabs
- Remediation plan (secrets rotation, RBAC hardening)

---

### 📚 Reference Materials
- GitHub security best practices  
- Jenkins script console docs  
- Project Zero blog on CI/CD issues

---

### 🏷️ Tags / Labels
`insider-threat` `devtools` `github` `jenkins` `ci-cd` `supply-chain`

---

### 📈 Effort Level
**Medium (M)** — relevant and often overlooked attack vector.

---

### ✅ Acceptance Criteria
- [ ] At least one path from low-priv dev tool access to data/code/secrets
- [ ] Playbook-style documentation of the replay
