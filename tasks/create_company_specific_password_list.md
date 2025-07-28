# 🔐 Research Spike: Create a Company-Specific Password List

**Goal:**  
Generate a tailored password list based on internal patterns, terminology, and behavior. This will improve the success rate of password spraying and brute force attempts during red team operations.

**Why It Matters:**  
Generic password lists often miss patterns specific to an organization. Custom lists — based on internal lingo, projects, exec names, seasonal events, etc. — are far more effective in real-world attacks.

---

### 🔍 Scope
- Internal naming conventions (e.g., project names, mascots, acronyms)
- Executive/employee names and birth years
- Seasonal passwords and common variants (e.g., Spring2025!, FY25Budget)
- Services or tools commonly used (e.g., JIRA2025!, JenkinsAdmin)

---

### ✅ Tasks
- [ ] Scrape internal wiki, email lingo, Slack/Teams slang, conference names
- [ ] Review previously cracked hashes from internal assessments
- [ ] Add variations: capitalization, year, number suffix, special chars
- [ ] Create multiple tiers:
  - High-confidence spray list (short and slow)
  - Full brute list (longer and lower-priority)
- [ ] Deconflict with public leaks (ensure uniqueness if needed)
- [ ] Document assumptions, sources, and pattern rationale

---

### 🎯 Deliverables
- `company-passwords-tier1.txt`
- `company-passwords-tier2.txt`
- Internal wiki or markdown doc describing:
  - Logic behind word choice
  - Patterns used
  - Sources scraped
- Optional: Integration into password spraying tools or C2 profiles

---

### 📚 Reference Materials
- CUPP: https://github.com/Mebus/cupp
- JPCERT Wordlist Creation Guide: https://jpcertcc.github.io/ToolAnalysisResultSheet/PasswordList_Creation_en.pdf
- CrackMapExec: https://github.com/Porchetta-Industries/CrackMapExec

---

### 🏷️ Tags / Labels
`password-list` `company-specific` `spray-list` `brute-force` `cred-abuse`

---

### 📈 Effort Level
**Medium (M)** — requires some time digging through internal language, but highly reusable.

---

### ✅ Acceptance Criteria
- [ ] Wordlist created with internal context
- [ ] Spray-ready list built and staged
- [ ] Markdown doc with logic & sources
