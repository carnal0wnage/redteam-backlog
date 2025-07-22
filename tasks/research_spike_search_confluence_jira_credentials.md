# 📄 Research Spike: Confluence & Jira Credential Discovery Tool

**Goal:**  
Build a script or tool to search Confluence and Jira (internal or cloud-hosted) for exposed credentials, secrets, and access tokens. Focus on misused documentation, configuration pages, or hidden field leaks across the organization.

**Why It Matters:**  
Documentation platforms are often treated as knowledge dumps — including how-to guides, test accounts, configs, and access instructions. Many users unknowingly paste secrets into pages that lack proper access control or redaction.

---

### ✅ Tasks

- [ ] Enumerate accessible Confluence spaces and Jira projects:
  - Use API tokens or cookies to search authenticated content
  - Crawl page titles, comments, and attachments
- [ ] Search for sensitive patterns:
  - Regexes for `password`, `token`, `apikey`, `client_secret`
  - Common file names: `config.yml`, `.env`, `secrets.txt`, `aws_credentials`
- [ ] Implement:
  - Authenticated session or token login
  - Rate-limited API calls or HTML scraping
  - Context capture: page title, link, author, space/project, snippet
- [ ] Optional:
  - Entropy scoring or wordlist match
  - Jira: search tickets/comments with keywords
  - Confluence: search attachments or macros for embedded secrets

---

### 🎯 Deliverables

- Script/tool: `conflu-leaks.py`, `jira-sniff.sh`, or combined scanner
- Output format: CSV or JSON with path, preview, timestamp, owner
- Redacted example hits
- Detection regex library
- Recommendations:
  - Auto-flag sensitive terms in doc workflows
  - Tag "credential paste" pages for review
  - Train users on doc hygiene and redaction

---

### 📚 References

- Confluence REST API: https://developer.atlassian.com/cloud/confluence/rest/  
- Jira REST API: https://developer.atlassian.com/cloud/jira/platform/rest/v3/  
- MITRE ATT&CK T1552.001 (Credentials in Files)  
- Related: GitHub secret scanning regexes (can be reused)

---

### 🏷️ Tags

`atlassian` `confluence` `jira` `secrets` `credential-leakage` `internal-docs` `token-hunting` `t1552.001` `knowledge-base-risk`

---

### 📈 Effort Level

**Medium (M)** — API scripting or browser automation required; can be scaled into a recurring audit tool.

---

### ✅ Acceptance Criteria

- [ ] Script built and tested on one Confluence/Jira instance  
- [ ] At least 5 redacted matches found (test or real)  
- [ ] Page-level metadata included in results (title, link, user)  
- [ ] Output saved in a clean, shareable format  
- [ ] Added to internal recon toolkit or SOAR workflow