
## 🔐 Research Spike: Password Spraying Internal Login Portals

**Goal:**  
Simulate password spraying attacks against internal login portals (VPN, OWA, SSO) using low-and-slow techniques to identify weak credentials and test blue team detection and lockout thresholds.

**Why It Matters:**  
Password spraying is one of the most common initial access vectors in real-world breaches. Understanding how exposed your portals are, how account lockouts behave, and what logs are generated builds both offensive and defensive maturity.

---

### 🔍 Scope
- Internal login portals (VPN gateways, Outlook Web Access, SSO login pages)
- Test creds: known test accounts, common usernames, expired employees
- Rate-limited to avoid triggering lockouts

---

### ✅ Tasks
- [ ] Identify login endpoints (VPN, OWA, SSO, Citrix, etc.)
- [ ] Generate a user list:
  - Pull from email naming conventions, past breaches, LinkedIn scraping
- [ ] Choose tools:
  - `Kerbrute` for Kerberos-based login spraying
  - `MSOLSpray` for O365/Azure environments
  - Custom curl/bash tools for internal logins
- [ ] Perform low-and-slow spraying:
  - E.g., 1 password every 30 minutes across users
- [ ] Monitor outcomes:
  - Successful login
  - Account lockout
  - Detection alerts
- [ ] Optional: correlate with SIEM logs or alert dashboards

---

### 🎯 Deliverables
- Password spraying plan with:
  - Target systems
  - User/password lists used
  - Rate and timing logic
- Table of results:
  - Which accounts responded (login/lockout)
  - Systems most vulnerable
- Risk assessment:
  - Is MFA enabled?
  - Lockout thresholds documented?
  - Detection/logging verified?
- Recommendations:
  - Improve lockout policy or alerting
  - Enforce MFA
  - Rotate old/weak creds

---

### 📚 Reference Materials
- Kerbrute: https://github.com/ropnop/kerbrute  
- MSOLSpray: https://github.com/dafthack/MSOLSpray  
- Password spraying writeups: https://posts.specterops.io/  
- OWASP Authentication Cheat Sheet: https://cheatsheetseries.owasp.org/  
- MITRE ATT&CK T1110.003 – Password Spraying: https://attack.mitre.org/techniques/T1110/003/

---

### 🏷️ Tags / Labels
`junior-friendly` `password-spray` `t1110.003` `auth-bypass` `blue-team-awareness` `identity` `sso`

---

### 📈 Effort Level
**Medium (M)** — requires caution, planning, and safe test creds.

---

### ✅ Acceptance Criteria
- [ ] At least 2 internal login portals targeted
- [ ] Password spray performed using rate-limiting logic
- [ ] Results documented clearly (success, lockout, alert)
- [ ] Detection visibility evaluated and recommendations shared
