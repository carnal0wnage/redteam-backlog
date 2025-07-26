# 🎣 Research Spike: Phishing Pretext Template Pack (Internal Tools)

**Goal:**  
Build a library of realistic phishing lures tailored to your company’s internal tools and workflows (e.g., HR portals, expense systems, dev platforms). Clone internal login pages, mimic real email formatting, and prepare test campaigns for awareness or red team simulation.

**Why It Matters:**  
Most users spot generic phishing attempts. But well-crafted, internal-looking emails and portals dramatically increase realism and click-through rates. This project helps junior red teamers develop social engineering instincts and prepares material for internal simulations.

---

### 🔍 Scope
- Only for approved red team or phishing simulation purposes
- Internal tools only: HR, expense, IT support, ticketing, dev tools (e.g., Jira, Jenkins, GitLab, Okta, Duo, Workday, SAP, etc.)
- No real credentials captured — use fake login endpoints or tracking pixels only

---

### ✅ Tasks
- [ ] Identify 3–5 commonly used internal tools
- [ ] Analyze legitimate communications:
  - Review real internal emails (format, subject lines, sender names)
  - Screenshot login pages, copy logos, buttons, favicon, fonts
- [ ] Build phishing lures for each tool:
  - [ ] Fake login page (HTML + CSS clone)
  - [ ] Phishing email template (.eml or HTML body)
  - [ ] Suggested subject lines and pretexts (e.g., “Quarterly Bonus Report”, “Action Required: MFA Timeout”)
- [ ] Host fake login pages safely:
  - Use a domain like `example-support[.]com`
  - Ensure no data is saved (only redirects or logging)
- [ ] Send test emails via GoPhish or mail relay (lab only):
  - Confirm email formatting renders correctly
  - Track clicks or credential input on dummy login pages
- [ ] Optional: Add link to Canarytoken, webhook, or test tracking pixel

---

### 🎯 Deliverables
- Internal “Phishing Pretext Pack” with:
  - Email templates (HTML + .eml)
  - Screenshots of real vs fake logins
  - Cloned HTML/CSS login pages (sanitized)
  - Subject lines + body copy for each pretext
- Risk writeup:
  - Which tools were most believable
  - Which pretexts got test users to click
  - How to defend (DKIM, DMARC, warning banners, user education)

---

### 📚 Reference Materials
- GoPhish: https://github.com/gophish/gophish  
- Evilginx2: https://github.com/kgretzky/evilginx2  
- MITRE T1566 – Phishing: https://attack.mitre.org/techniques/T1566/  
- Microsoft 365 Phishing Templates: https://github.com/0xZDH/o365-phish  
- HTML Email Rendering Tips: https://htmlemail.io/  
- Social Engineering Pretexts (Red Team Toolkit): https://redteam.guide

---

### 🏷️ Tags / Labels
`junior-friendly` `phishing` `social-engineering` `pretexting` `email` `internal-tools` `t1566`

---

### 📈 Effort Level
**Small (S)** — great for creative red teamers with an eye for UI and copywriting.

---

### ✅ Acceptance Criteria
- [ ] 3+ phishing lures created for internal tools
- [ ] Each includes an email template and a cloned login page
- [ ] Templates tested in safe environment (GoPhish, Canarytokens, etc.)
- [ ] Internal doc or wiki created with screenshots, source files, and pretext descriptions
- [ ] Recommendations documented for training or blue team countermeasures