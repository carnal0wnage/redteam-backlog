
# 🔍 Research Spike: Search CI/CD Build Logs for Leaked Credentials

**Goal:**  
Create a tool or script to automatically scan CI/CD build logs (e.g., Jenkins, GitHub Actions, GitLab CI) for secrets such as tokens, passwords, session IDs, API keys, and environment variable dumps.

**Why It Matters:**  
Build pipelines often inadvertently expose secrets during job execution. Logs may include `echo $TOKEN`, failed command dumps, or verbose debugging outputs. Automating this analysis helps red teams find initial access or lateral movement vectors and supports blue teams in detection and hardening.

---

### 🔍 Scope
- CI/CD environments: Jenkins, GitHub Actions, GitLab, CircleCI, Azure DevOps
- Accessible logs (public, exposed, or internal)
- Target strings:
  - API tokens, OAuth secrets
  - Session cookies
  - Passwords or cleartext secrets
  - `.env` dump patterns
  - JSON auth blobs
  - AWS_ACCESS_KEY, `gcloud auth`, etc.

---

### ✅ Tasks
- [ ] Build a script or CLI tool (Python/Go preferred) that:
  - Ingests local or remote CI log files
  - Parses line-by-line and applies regex for common secret patterns
  - Flags lines with entropy score > threshold (for potential secrets)
  - Outputs matches with filename, line number, and matched pattern
- [ ] Test against:
  - Public repos with GitHub Actions logs
  - Internal Jenkins/GitLab logs with dummy secrets
- [ ] Add ability to:
  - Match known cloud key formats (AWS, GCP, Azure)
  - Detect base64-encoded secrets
  - Follow redirect URLs from webhook dumps
- [ ] Optional: Slack/Teams webhook output for detected secrets

---

### 🎯 Deliverables
- Working script or binary to scan CI/CD build logs
- Sample scan results with redacted output
- Write-up of log types most likely to expose secrets
- Integration option for weekly pipeline log scans
- Optional: Create internal detections or dashboards for blue team

---

### 📚 Reference Materials
- [Infosec Writeup – CI/CD Webhook Leak to Root](https://infosecwriteups.com/leaks-on-repeat-how-a-ci-cd-webhook-gave-me-root-logs-tokens-tears-072dfeef9629)  
- TruffleHog: https://github.com/trufflesecurity/trufflehog  
- GitLeaks: https://github.com/gitleaks/gitleaks  
- Common regexes: https://github.com/dxa4481/truffleHog/blob/main/truffleHog/regexes.json  
- GitHub Actions logs: https://docs.github.com/en/actions/monitoring-and-troubleshooting-workflows/viewing-logs-to-diagnose-failures

---

### 🏷️ Tags / Labels
`senior` `ci/cd` `log-analysis` `secrets-scanning` `token-theft` `automation` `gitleaks` `t1552`

---

### 📈 Effort Level
**Medium (M)** — regex tuning and noise reduction can be tricky; integrating with multiple platforms adds complexity.

---

### ✅ Acceptance Criteria
- [ ] Script parses and scans logs for at least 3 CI systems
- [ ] At least 5 types of secrets detected with example output
- [ ] README or doc describing how to run and extend the tool
- [ ] Optional detection logic or Slack alerting built in
