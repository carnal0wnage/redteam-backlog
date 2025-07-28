# 🧠 Research Spike: Public Password Dump Archive & Query Tool

**Goal:**  
Collect, sort, and maintain a database or indexed archive of public password dumps for use in credential stuffing, password reuse analysis, and spray testing.

**Why It Matters:**  
Many passwords used internally are reused from public leaks. A local archive makes it easier to match credentials during red team operations and track trends in reuse behavior.

---

### 🔍 Scope
- Popular dumps: RockYou, CrackStation, Pwned Passwords, ComboLists
- Targeted dumps: Pastebin, raidforums mirrors, special corp dumps
- Sorting, deduplication, filtering of low-signal junk

---

### ✅ Tasks
- [ ] Identify and download top public password dumps
- [ ] Normalize line endings, character encodings, and remove noise
- [ ] Create an indexed archive (e.g., with SQLite, grep-ready flat files)
- [ ] Sort by:
  - Password length
  - Number of occurrences (if available)
  - Date of breach
- [ ] Add search tooling:
  - `grep`, `ripgrep`, or simple CLI frontend
  - Optional: lightweight web interface
- [ ] Optional: Map patterns to specific leaks or geos

---

### 🎯 Deliverables
- `/dumps/` folder of normalized password files
- `index.db` or flat index of searchable terms
- `search.sh` or CLI interface to query archive
- README with usage, update instructions, and source links

---

### 📚 Reference Materials
- Dehashed DB (with subscription): https://www.dehashed.com/
- CrackStation: https://crackstation.net/
- Pwned Passwords: https://haveibeenpwned.com/Passwords
- SecLists: https://github.com/danielmiessler/SecLists
- Breach Compilation dumps

---

### 🏷️ Tags / Labels
`public-dumps` `password-reuse` `cred-stuffing` `tooling` `archive`

---

### 📈 Effort Level
**Medium (M)** — requires initial time investment to collect and sort, but low maintenance afterward.

---

### ✅ Acceptance Criteria
- [ ] Archive with at least 3 major dumps
- [ ] Tool created to search for passwords or emails
- [ ] Documentation or README written and shared
