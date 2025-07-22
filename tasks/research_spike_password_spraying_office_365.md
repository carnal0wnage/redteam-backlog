# ## 🔐 Research Spike: Password Spraying Office 365 / Azure

**Goal:**  
Simulate safe, low-and-slow password spraying attacks against Microsoft 365 / Azure AD tenant(s) using tools like `O365Spray`, `MSOLSpray`, or `ROADtools`. Understand lockout thresholds, detection methods, and how attackers identify valid usernames.

**Why It Matters:**  
Password spraying is one of the most common techniques for initial access — especially in cloud environments where MFA is inconsistently applied. Junior red teamers must learn how to perform these tests safely and how blue teams detect or miss them.

---

### 🔍 Scope
- Approved O365 / Azure AD tenant (test, dev, or designated lab tenant)
- Valid user enumeration (seeded test users or existing email addresses)
- Tools must respect tenant lockout policies (max 1–3 attempts per user per hour)
- **No actual credential theft or brute-force**

---

### ✅ Tasks
- [ ] Research O365 / Azure AD account lockout policies:
  - Microsoft Smart Lockout: https://learn.microsoft.com/en-us/azure/active-directory/authentication/concept-smart-lockout
  - Determine number of allowed bad auths per user / IP
- [ ] Use one or more of the following tools:
  - [`O365Spray`](https://github.com/0xZDH/o365spray)
  - [`MSOLSpray`](https://github.com/dafthack/MSOLSpray)
  - [`ROADtools`](https://github.com/dirkjanm/ROADtools)
- [ ] Prepare test data:
  - Wordlist of known or guessable usernames (e.g., `j.smith`, `admin`, `hr`, `marketing`)
  - Wordlist of 1–2 passwords for simulation (e.g., `Winter2024`, `Welcome123`)
- [ ] Write and execute a spray plan:
  - Limit to 1 password per round across all usernames
  - Wait 30–60 min between rounds
  - Monitor for account lockouts or MFA prompts
- [ ] Document detection and logging behavior:
  - Was traffic visible in Azure logs, Defender, or SIEM?
  - Were any accounts locked?
  - What telemetry showed up in audit logs?
- [ ] Optional: test with VPN rotation, proxy, or user-agent spoofing

---

### 🎯 Deliverables
- Internal report or wiki page including:
  - Tool used, spray schedule, and username format
  - Screenshots or logs of detection (or absence)
  - Notes on lockout behavior and MFA enforcement
  - Recommendations for improving detection & lockout policies
- Password spraying cheat sheet:
  - Rate limits, safe spray cadence, evasion tips
  - Detection rules (e.g., multiple failures from single IP, horizontal auth)

---

### 📚 Reference Materials
- O365Spray: https://github.com/0xZDH/o365spray  
- MSOLSpray: https://github.com/dafthack/MSOLSpray  
- SpecterOps "Attacking and Defending Azure AD": https://posts.specterops.io/  
- Microsoft Smart Lockout: https://learn.microsoft.com/en-us/azure/active-directory/authentication/concept-smart-lockout  
- MITRE T1110.003 (Password Spraying): https://attack.mitre.org/techniques/T1110/003/

---

### 🏷️ Tags / Labels
`junior-friendly` `password-spraying` `azure` `office365` `cloud-auth` `t1110.003`

---

### 📈 Effort Level
**Small (S)** — requires caution and timing, but tool use is straightforward.

---

### ✅ Acceptance Criteria
- [ ] Tool successfully executed with safe spray cadence
- [ ] Valid and invalid usernames tested with 1–2 passwords
- [ ] Detection results (or lack thereof) documented
- [ ] Lockout behavior observed and noted
- [ ] Spray plan + findings documented in internal wiki