# 🔍 Research Spike: GitHub/GitLab Secret Search Tool

**Goal:**  
Create or adapt a script/tool to search GitHub and GitLab (public or internal instances) for exposed secrets such as passwords, API keys, tokens, and cloud credentials — scoped to organization projects or user contributions.

**Why It Matters:**  
Secrets frequently leak into source control via `.env` files, hardcoded test keys, or CI/CD configs. Public and internal repos alike represent a high-value attack surface — and detection usually lags behind the leak.

---

### ✅ Tasks

- [ ] Define search targets:
  - Org GitHub repos (public + private via API)
  - GitLab groups or user namespaces
  - Keyword searches: `password`, `token`, `api_key`, `aws_secret`, `PRIVATE_KEY`, etc.
  - Filenames of interest: `.env`, `config.yml`, `settings.py`, `.npmrc`, `.git-credentials`
- [ ] Choose tooling:
  - GitHub API + `gh` CLI or PyGitHub
  - GitLab API + `python-gitlab`
  - Consider Gitleaks, TruffleHog, Gitrob, or custom regex engine
- [ ] Script should:
  - Search recent commits and indexed content
  - Flag high-entropy strings
  - Save context (repo, filename, line number, timestamp)
- [ ] Optional: build exclusion logic for false positives
- [ ] Test against known test repos with intentional leaks

---

### 🎯 Deliverables

- Search script (`git-secret-sniper.py` or similar)
- Report output (JSON or CSV): matches with repo URL, file path, context snippet
- Demo screenshots or terminal logs
- Detection regexes or entropy scoring model
- Recommendations:
  - Add secret scanning to all CI/CD pipelines
  - Block secrets via commit hooks
  - Rotate any found credentials immediately

---

### 📚 References

- [Gitleaks](https://github.com/gitleaks/gitleaks)  
- [TruffleHog](https://github.com/trufflesecurity/trufflehog)  
- [Gitrob](https://github.com/michenriksen/gitrob)  
- GitHub Search API: https://docs.github.com/en/rest/search  
- MITRE ATT&CK T1552.001 (Credentials in Files)

---

### 🏷️ Tags

`git` `github` `gitlab` `secrets` `tokens` `api-keys` `t1552.001` `gitleaks` `ossint` `devsec` `source-control`

---

### 📈 Effort Level

**Medium (M)** — scripting required; can be extended into a persistent scanner or CI/CD hook.

---

### ✅ Acceptance Criteria

- [ ] Tool/script built and functional on at least one platform (GitHub or GitLab)  
- [ ] At least 5+ secrets or simulated hits identified  
- [ ] Regex or detection logic documented  
- [ ] Output includes timestamp, path, and preview  
- [ ] Shared with internal red team repo or integrated into recon workflow