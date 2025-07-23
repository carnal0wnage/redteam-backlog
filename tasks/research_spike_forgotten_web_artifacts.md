# 🕳️ Research Spike: Forgotten Web Artifacts

**Goal:**  
Identify and test forgotten or unintended web-accessible artifacts (e.g., `.git`, `.env`, `.DS_Store`, `.htaccess`, backup files, temp files) that can leak sensitive data or enable attackers to pivot further into the environment. Create a reusable checklist or scanner template for future use.

**Why It Matters:**  
These files are often left behind by developers, IDEs, backup systems, or version control. They're rarely monitored, usually exposed in dev/staging environments, and can directly reveal passwords, source code, internal endpoints, or the full structure of a web app.

---

### 🔍 Scope
- Internal and dev/staging web apps
- Public apps only if in scope
- Target file types and patterns:
  - `.git/`, `.env`, `.DS_Store`, `.htaccess`, `.gitignore`
  - `backup.zip`, `wp-config.bak`, `db.sql`, `site.tar.gz`
  - IDE/project files: `.idea/`, `.vscode/`, `package-lock.json`, `composer.lock`
  - `config.old`, `index.php~`, `*.bak`, `*.swp`, `*.log`

---

### ✅ Tasks
- [ ] Use `ffuf`, `feroxbuster`, or `dirsearch` with custom wordlists to scan known targets
  - Wordlists: SecLists `Discovery/Web-Content` + `Fuzzing` folders
- [ ] Attempt to download and extract file contents
  - `curl`, `wget`, or browser download
- [ ] For each found file:
  - Determine what kind of data it leaks (creds, internal paths, source code, API keys, etc.)
  - Identify potential next steps (auth bypass, SSRF, lateral move)
- [ ] Confirm if version control data can be reconstructed (e.g., `.git/HEAD` + GitTools)
- [ ] Create a "Top 10 Forgotten Web Files" list with risk levels
- [ ] Write or modify a Nuclei template or bash script to scan for these automatically

---

### 🎯 Deliverables
- Internal markdown or wiki page with:
  - Table of discovered files (URL, file type, what was exposed)
  - Screenshots or redacted output from exposed files
  - Top 10 Forgotten Web Files list + what each can lead to
  - Detection tool (Nuclei template, bash script, ffuf config)
  - Dev and blue team remediation advice (block extensions, web server configs)

---

### 📚 Reference Materials
- HackTricks: https://book.hacktricks.xyz/pentesting-web/file-disclosure  
- GitTools: https://github.com/internetwache/GitTools  
- Nuclei Templates: https://github.com/projectdiscovery/nuclei-templates  
- PayloadsAllTheThings: https://github.com/swisskyrepo/PayloadsAllTheThings  
- SecLists: https://github.com/danielmiessler/SecLists  
- OWASP Top 10: https://owasp.org/www-project-top-ten/

---

### 🏷️ Tags / Labels
`junior-friendly` `web` `file-disclosure` `infoleak` `forgotten-files` `owasp`

---

### 📈 Effort Level
**Small to Medium (S–M)** — scanning is easy; high-value findings come with attention to detail.

---

### ✅ Acceptance Criteria
- [ ] At least 5 forgotten files discovered and documented
- [ ] For at least 2 files, clear impact explained (e.g., creds, source path, RCE potential)
- [ ] Top 10 Forgotten Web Files list written with descriptions
- [ ] Nuclei or ffuf config created and tested
- [ ] Wiki or markdown doc shared with team and tagged for future scans
