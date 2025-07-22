
# 🔍 Research Spike: Internal GitHub/GitLab Dorking for First-Party Secrets and Configurations

**Goal:**  
Create an internal list of GitHub/GitLab dorks tailored to your company’s CI/CD tools, naming conventions, domains, and service identifiers. Use this list to discover exposed internal secrets, webhook URLs, tokens, or misconfigured pipeline files.

**Why It Matters:**  
Search dorks that reflect your company's architecture and culture are far more effective than generic ones. By customizing searches for secrets and sensitive configs, red teams can proactively identify exposures — while blue teams can better tune secrets detection pipelines.

---

### 🔍 Scope
- GitHub (public + internal GitHub Enterprise)
- GitLab (public + self-hosted instances)
- Relevant repositories tied to:
  - CI/CD workflows
  - Dev environments
  - Infrastructure-as-code (IaC)
  - Secrets-in-code incidents

---

### ✅ Tasks
- [ ] Identify internal patterns of interest:
  - Internal domains (e.g., `internal.corp.net`)
  - Common repo names (e.g., `infra-tools`, `jenkins-pipelines`)
  - Known leaked secrets (e.g., `corp_token`, `service_password`)
- [ ] Write and test dorks such as:
  - `filename:.gitlab-ci.yml`
  - `path:.github/workflows`
  - `"secrets.GITHUB_TOKEN"`
  - `"AWS_ACCESS_KEY_ID" AND "AWS_SECRET_ACCESS_KEY"`
  - `"webhook.site"` OR known red team callback domains
  - `filename:.env` + `"corp_"` prefix matches
- [ ] Run against:
  - Public GitHub (web UI, GitHub CLI)
  - Internal GitHub Enterprise (API or UI)
  - GitLab web and internal GitLab APIs
- [ ] Categorize results:
  - Config exposure (e.g., pipelines, service descriptors)
  - Credential exposure (tokens, keys, passwords)
  - Secrets in test data
- [ ] Optional:
  - Build a CLI or scheduled job to monitor and diff dork hits over time
  - Create Slack alerts or summary dashboards for new results

---

### 🎯 Deliverables
- `dorks.md` or CSV with 20–50 tailored GitHub/GitLab dorks
- Annotated results showing hits, sources, and severity
- Sample regex patterns and match logic
- Optional: cronable scan script or `gh` CLI automation
- Internal wiki or SOP for expanding the dork library

---

### 📚 Reference Materials
- [GitHub Code Search](https://docs.github.com/en/search-github/searching-on-github/searching-code)  
- [GitHub CLI `gh search`](https://cli.github.com/manual/gh_search_code)  
- [GitLeaks](https://github.com/gitleaks/gitleaks)  
- [GitHub Dork Examples](https://github.com/techgaun/github-dorks)  
- [Infosec Writeup on CI/CD Leak](https://infosecwriteups.com/leaks-on-repeat-how-a-ci-cd-webhook-gave-me-root-logs-tokens-tears-072dfeef9629)

---

### 🏷️ Tags / Labels  
`mid-level` `github` `gitlab` `dorking` `secrets-detection` `code-search` `t1552` `automation`

---

### 📈 Effort Level  
**Medium (M)** — requires institutional knowledge of internal tooling, CI/CD practices, and naming conventions.

---

### ✅ Acceptance Criteria
- [ ] Dork list contains at least 20 first-party tailored queries
- [ ] Run against at least one internal and one external platform
- [ ] Sample leaks or false positives captured and documented
- [ ] Tool or SOP to run dorks on a scheduled basis
- [ ] Wiki page or markdown doc published with results and recommendations
