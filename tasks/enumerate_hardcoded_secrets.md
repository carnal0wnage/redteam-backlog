
# 🔐 Research Spike: Enumerate Hardcoded Secrets in Source Repos

**Goal:**  
Use tools like TruffleHog, Gitleaks, and GitRob to identify hardcoded secrets such as API keys, credentials, and tokens in corporate source code repositories (GitHub, GitLab, Bitbucket). Evaluate both internal and public codebases.

**Why It Matters:**  
Hardcoded secrets are a major vector for credential theft, privilege escalation, and lateral movement. Secrets in repos often go undetected and can persist for years — especially in legacy branches or commit history.

---

### 🔍 Scope
- Internal GitHub Enterprise or GitLab instance
- Public and private repos tied to the organization
- CI/CD repos, legacy projects, and developer forks

---

### ✅ Tasks
- [ ] Select scanning tool(s):
  - TruffleHog: https://github.com/trufflesecurity/trufflehog
  - Gitleaks: https://github.com/gitleaks/gitleaks
  - GitRob: https://github.com/michenriksen/gitrob
- [ ] Configure with company-specific patterns:
  - Internal domains, API keys, cloud tokens, repo structure
- [ ] Scan commit histories, not just working trees:
  - Use deep scan or entropy-based matching
- [ ] Log all matches by:
  - File path
  - Commit ID
  - Author (if relevant)
- [ ] Triage results:
  - Remove false positives (e.g., test data)
  - Flag high-risk secrets (live AWS keys, DB creds, JWTs)
- [ ] Optional:
  - Write custom regex rules for internal secret formats
  - Integrate with pre-commit hooks or CI/CD secrets scanning

---

### 🎯 Deliverables
- Secrets scan report:
  - Total findings
  - Breakdown by severity
  - Affected repositories and commit history
- Markdown or Confluence page documenting:
  - Tool used and configuration
  - Examples of real vs false positives
  - Recommendations (e.g., commit rewriting, Vault migration)
- Optional: internal dashboard to track recurring secret patterns or scanning over time

---

### 📚 Reference Materials
- TruffleHog: https://github.com/trufflesecurity/trufflehog  
- Gitleaks: https://github.com/gitleaks/gitleaks  
- OWASP Secrets Management: https://owasp.org/www-project-secrets-management/  
- GitHub Secret Scanning: https://docs.github.com/en/code-security  
- GitLeaks Rule Examples: https://github.com/zricethezav/gitleaks/blob/main/config/gitleaks.toml  

---

### 🏷️ Tags / Labels
`secrets` `git` `source-code-audit` `gitleaks` `trufflehog` `t1552.001` `junior-friendly`

---

### 📈 Effort Level
**Medium (M)** — effective tools exist, but triaging noise and mapping impact can be time-consuming.

---

### ✅ Acceptance Criteria
- [ ] At least 5 high-risk repos scanned
- [ ] Tool config tailored to org’s secrets formats
- [ ] Report of findings with risk ratings
- [ ] Recommendations written for remediation and prevention
