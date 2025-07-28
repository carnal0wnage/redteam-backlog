# 🌐 Research Spike: Manual OSINT Workflow & Checklist for Red Team Operations

**Goal:**  
Perform manual OSINT activities to gather target organization intelligence (emails, employee names, infrastructure, exposed assets) and produce a minimum viable checklist for red team engagements.

**Why It Matters:**  
Manual OSINT provides high-context, targeted recon that automated tools can miss. By developing a repeatable checklist, red teamers can increase signal quality and reduce wasted effort in pre-engagement recon.

---

### 🔍 Scope
- Public-facing company assets (websites, social media, press)
- Employee exposure (names, roles, emails, photos)
- Technology stack, domains, dev tools, cloud presence
- Data leaks and password reuse potential

---

### ✅ Tasks
- [ ] Identify all public-facing domains and subdomains
- [ ] Search for public breach data associated with company emails (HaveIBeenPwned, DeHashed)
- [ ] Enumerate corporate email formats (e.g., first.last@, firstinitiallast@)
- [ ] Gather employee names, titles, and teams from:
  - LinkedIn, ZoomInfo, RocketReach
  - Company blogs, press releases
  - GitHub, StackOverflow, Reddit
- [ ] Identify tech stack from public sites using:
  - Wappalyzer, BuiltWith, Netcraft
- [ ] Review SSL/TLS certs, DNS records, WHOIS info
- [ ] Search paste sites and breach forums for leaks
- [ ] Build a list of likely email/password combos based on findings

---

### 🧰 Output Checklist (MVP)
- [ ] List of all identified email addresses
- [ ] Username format(s) (validated or inferred)
- [ ] Employee name/title/org chart inference
- [ ] Breach status for any emails (with dates)
- [ ] Top candidate passwords based on recon
- [ ] List of tech assets + vendors (SSO, cloud, payroll, etc.)
- [ ] Summary of exposed repos, credentials, or public S3 buckets

---

### 📚 Reference Materials
- OSINT Framework: https://osintframework.com/
- HaveIBeenPwned: https://haveibeenpwned.com/
- SpiderFoot: https://www.spiderfoot.net/
- LinkedIn scraping tools: GitHub search
- Domain recon: https://crt.sh, https://dnsdumpster.com

---

### 🏷️ Tags / Labels
`manual-osint` `recon` `email-discovery` `initial-access` `pretexting`

---

### 📈 Effort Level
**Medium (M)** — Requires creativity, patience, and cross-source correlation.

---

### ✅ Acceptance Criteria
- [ ] Manual OSINT completed on at least one internal or simulated target
- [ ] Checklist validated with real data output
- [ ] Findings shared with red team or used to support phishing pretexts