# 🕵️‍♂️ Research Spike: Exposed Version Control Artifacts Recon

**Goal:**  
Identify and extract source code, secrets, credentials, and sensitive metadata from exposed or misconfigured version control artifacts (e.g., `.git`, `.hg`, `.svn`, `.bzr`) on internal or internet-facing web applications.

**Why It Matters:**  
Dev teams often leave behind full repo histories, credentials, or API keys in old commits, forgotten `.git` folders, or obsolete VCS endpoints. These exposures can lead to code theft, authentication bypass, or lateral movement opportunities for attackers.

---

### 🔍 Scope
- Internal or external web apps and dev systems
- Artifact directories:
  - `.git/`
  - `.svn/`
  - `.hg/`
  - `.bzr/`
- Old or unmaintained source control endpoints or UIs
- Misconfigured or forgotten CI/CD tools

---

### ✅ Tasks
- [ ] Use tools like `git-dumper`, `GitTools`, `svn-extractor`, `hg-dump` to detect and download exposed VCS content
- [ ] Brute-force check known artifact URLs:
  - `/.git/HEAD`
  - `/.svn/entries`
  - `/.hg/store/00changelog.i`
- [ ] Rebuild and analyze any discovered repositories
- [ ] Extract `.gitmodules`, remotes, config files, and internal paths
- [ ] Grep for secrets: API keys, JWTs, creds in `.env`, `.aws`, `.npmrc`, etc.
- [ ] Review commit logs for leaked credentials or business logic
- [ ] Identify CI/CD secrets or access tokens in history

---

### 🎯 Deliverables
- Internal wiki page or Confluence writeup with:
  - List of identified exposed repos/systems
  - Screenshots or exported trees of extracted repos
  - Redacted examples of discovered secrets
  - Assessment of potential impact
  - Remediation checklist for dev teams
- Sample detection query for WAF, SIEM, or alerting (e.g., `.git` access)
- Tooling/scripts used for repeatability

---

### 📚 Reference Materials
- GitTools: https://github.com/internetwache/GitTools  
- git-dumper: https://github.com/arthaud/git-dumper  
- svn-extractor: https://github.com/ilmila/svn-extractor  
- Assetnote blog (great writeups): https://blog.assetnote.io  
- HackerOne report: https://hackerone.com/reports/775055  
- ProjectDiscovery Nuclei templates: https://github.com/projectdiscovery/nuclei-templates

---

### 🏷️ Tags / Labels
`junior-friendly` `version-control` `vuln-recon` `devops` `secrets-detection`

---

### 📈 Effort Level
**Small to Medium (S–M)** — depends on breadth of scan and findings.

---

### ✅ Acceptance Criteria
- [ ] Minimum 2 systems tested (internal or public-facing)
- [ ] At least 1 exposed repo recovered or verified clean
- [ ] Secrets or sensitive paths identified (if present)
- [ ] Internal writeup shared with team
- [ ] Detection/alerting suggestions documented