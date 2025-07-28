# 🕵️ Research Spike: Automated OSINT Collection & Credential Enrichment Tool

**Goal:**  
Design and prototype an automated tool that performs open-source intelligence (OSINT) to collect employee emails, usernames, and contextual data that can assist with password guessing. The tool should also generate potential credential pairs based on patterns, breaches, and company-specific intel.

**Why It Matters:**  
OSINT-based credential harvesting is a crucial part of initial access and credential stuffing scenarios. Automating this step boosts red team efficiency and realism — and helps blue teams understand how much sensitive data is already exposed publicly.

---

### 🔍 Scope
- Public OSINT sources: LinkedIn, GitHub, Twitter, paste sites, company blogs, ZoomInfo, Shodan
- Scraping or API-based collection of:
  - Employee names, emails, and usernames
  - Email formats (e.g., `first.last@company.com`)
  - Public mentions of password policies
  - Common company themes (mascots, locations, products)
- Password guess generation based on:
  - Name patterns + common suffixes (e.g., `2023`, `!`)
  - Breach wordlists + company-specific patterns
  - Custom rules for tools like `cewl`, `crunch`, or `wordsmith`

---

### ✅ Tasks
- [ ] Build email and name harvester:
  - LinkedIn scraping (e.g., `linkedin2username`)
  - GitHub user commits (`git-hound`)
  - Search engines (`Google Dorks`, `hunter.io`)
- [ ] Identify common email formatting pattern
- [ ] Feed names into password generator using:
  - Common suffixes: `123`, `!`, year, season
  - Company lingo, mascot, tools
- [ ] Optionally:
  - Check emails against HaveIBeenPwned or public dumps
  - Store in searchable format (SQLite, CSV, or simple web interface)
- [ ] Evaluate existing tools like:
  - `recon-ng`, `theHarvester`, `GHunt`, `Holehe`, `Maigret`

---

### 🎯 Deliverables
- Working prototype or script to:
  - Harvest emails and usernames
  - Generate password guesses based on company themes
  - Store credential pairs in clean export format
- Sample output for a test target (internal or lab)
- Internal wiki page documenting:
  - Tool architecture
  - OSINT sources used
  - Patterns leveraged for password generation
- Optional: Web UI or CLI wrapper

---

### 📚 Reference Materials
- recon-ng: https://github.com/lanmaster53/recon-ng  
- theHarvester: https://github.com/laramies/theHarvester  
- LinkedIn2Username: https://github.com/initstring/linkedin2username  
- HaveIBeenPwned API: https://haveibeenpwned.com/API/v3  
- CeWL: https://github.com/digininja/CeWL  
- Crunch: https://tools.kali.org/password-attacks/crunch  

---

### 🏷️ Tags / Labels
`junior-friendly` `osint` `initial-access` `password-guessing` `tooling` `automation`

---

### 📈 Effort Level
**Medium (M)** — multiple tool integrations and contextual analysis required.

---

### ✅ Acceptance Criteria
- [ ] Script/tool can harvest at least 25 valid email addresses from OSINT
- [ ] Generates a wordlist of at least 100 plausible passwords
- [ ] Captures formatting patterns and supports export
- [ ] Deliverables shared internally for feedback and tuning
