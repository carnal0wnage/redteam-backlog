# 🛠️ Research Spike: Password Dump Analysis & Credential Testing

**Goal:**  
Use known password dumps (e.g., COMB, RockYou2021, domain-specific leaks) to identify valid usernames and passwords for your organization, and test those credentials safely across exposed or internal services.

**Why It Matters:**  
Credential stuffing from breach reuse remains one of the top real-world initial access methods (MITRE T1110.003). This spike strengthens your organization’s credential hygiene visibility, especially for shadow accounts, shared creds, or reused personal logins.

---

### ✅ Tasks

- [ ] Download or query breach dumps (e.g., HaveIBeenPwned, Dehashed, public dumps)
- [ ] Extract email addresses / usernames & passwords for org domains
- [ ] Identify commonly reused passwords via frequency analysis
- [ ] Cross-reference:
  - Active directory usernames
  - Common service usernames (VPN, O365, Citrix, Okta, internal apps)
- [ ] Build a spray-friendly credential list
- [ ] Conduct safe tests using:
  - Low-and-slow spraying tools (O365Spray, MSOLSpray, domain login scripts)
  - Lockout-aware throttling
  - Monitor detection + logging
- [ ] Document any hits and escalation paths

---

### 🎯 Deliverables

- Credential exposure report:
  - Matching usernames
  - Password frequency graph
  - Spray results (success/fail/locked)
- Top 20 reused passwords within org
- Recommendations:
  - Forced password resets
  - Block high-risk passwords via Azure AD or PAM
  - User awareness campaign around breach reuse

---

### 📚 References

- MITRE ATT&CK T1110.003 (Credential Stuffing)  
- O365Spray: https://github.com/0xZDH/o365spray  
- Dehashed API or HaveIBeenPwned enterprise  
- RockYou2021, COMB, Cit0day, etc.  
- Spraying tips: SpecterOps, Black Hills

---

### 🏷️ Tags

`password-reuse` `breach-analysis` `creds` `credential-stuffing` `t1110.003` `identity-risk` `spraying` `azuread`

---

### 📈 Effort Level

**Medium (M)** — data parsing, username mapping, and access testing; useful for junior red teamers.

---

### ✅ Acceptance Criteria

- [ ] At least 1 breach source parsed for org-specific users  
- [ ] Spray plan developed with lockout limits considered  
- [ ] At least 1 success or potential weak point documented  
- [ ] Output shared securely with identity and detection teams  
- [ ] Findings logged in red team issue tracker with follow-up tasks
