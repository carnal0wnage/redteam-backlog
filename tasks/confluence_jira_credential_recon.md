# 🧠 Research Spike: Tool – Confluence/Jira Credential Recon

**Goal:**  
Develop or adapt a tool that scans Confluence and Jira pages for embedded credentials, API tokens, SSH keys, or secrets. Automate the identification of sensitive information exposed in internal documentation, macros, or configuration pages. If needed, create a team API key or separate account that can be used to scan that is indicative a normal employee access.

**Why It Matters:**  
Confluence and Jira are often used to store internal knowledge, deployment procedures, and troubleshooting documentation. These platforms frequently contain sensitive data that can be leveraged for lateral movement, privilege escalation, or initial access when misconfigured or improperly secured.

---

### 🔍 Scope
- Internal Confluence and Jira instances
- Authenticated user access level required (no need for admin access)
- Focus on:
  - Plaintext secrets
  - Misconfigured macros or integrations
  - Accidental information disclosure in archived projects or closed tickets

---

### ✅ Tasks
- [ ] Identify internal Confluence and Jira endpoints
- [ ] Enumerate readable pages using existing credentials
- [ ] Search for keywords and patterns:
  - `password=`, `AWS_SECRET_ACCESS_KEY`, `-----BEGIN PRIVATE KEY-----`, `.env`
  - API keys, webhook URLs, access tokens
- [ ] Look in:
  - Page text
  - Macros (e.g., code snippets, attachments)
  - Comments or change history
- [ ] Log hits and classify by severity:
  - API key → medium
  - Cloud credential or private key → high
- [ ] Optional: Build custom regex library or integrate with existing tools (e.g., TruffleHog, regexr, or YARA)
- [ ] Output format:
  - Page URL
  - Type of credential
  - Snippet with redacted preview
  - Severity rating

---

### 🎯 Deliverables
- Tool or script that runs against Jira/Confluence and logs matches
- Example run output (JSON or CSV)
- Optional: dashboards for red/blue team use
- Suggested improvements to Jira/Confluence info-sharing hygiene
- Wiki doc with common keyword patterns and best practices

---

### 📚 Reference Materials
- TruffleHog: https://github.com/trufflesecurity/trufflehog  
- Gitleaks: https://github.com/gitleaks/gitleaks  
- Regex Lists for Secrets: https://github.com/dxa4481/truffleHog/blob/main/config/config.json  
- Atlassian API Docs: https://developer.atlassian.com/  

---

### 🏷️ Tags / Labels
`jira` `confluence` `internal-tools` `secrets-discovery` `mid-level` `documentation-leak`

---

### 📈 Effort Level
**Medium (M)** — tooling can be reused, but regex tuning and access enumeration require effort.

---

### ✅ Acceptance Criteria
- [ ] Tool built or adapted and tested on live data
- [ ] At least 5 sensitive findings recorded from valid pages
- [ ] Output includes categorization and redacted preview
- [ ] Document includes usage instructions and remediations