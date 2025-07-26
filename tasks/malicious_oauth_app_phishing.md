
# 🎣 Research Spike: Create Malicious OAuth App for Phishing

**Goal:**  
Clone legitimate application branding and request OAuth scopes that seem legitimate but give dangerous access (e.g., `contacts.read`, `mail.read`, `files.read`) to phish users into granting persistent, silent access.

**Why It Matters:**  
OAuth-based phishing bypasses many traditional security controls like MFA. Once a user consents, attackers can access sensitive data without triggering alerts. Malicious OAuth apps have been used in real-world BEC and espionage campaigns.

---

### 🔍 Scope
- Platforms: Microsoft Azure AD, Google Workspace, GitHub
- Social engineering through legitimate-looking consent screens
- No real credentials stolen — lab/test accounts only

---

### ✅ Tasks
- [ ] Register a new OAuth application in a test tenant or personal account
- [ ] Match branding of common internal or external apps (e.g., “Outlook Mail Sync”)
- [ ] Set up a consent flow that requests:
  - `offline_access`, `mail.read`, `contacts.read`, `files.read.all`
- [ ] Capture and store tokens after consent
- [ ] Test token use with Gmail/M365 APIs
- [ ] Document scope behavior (email download, contact access, etc.)
- [ ] Optional: Craft GoPhish templates to drive user interaction

---

### 🎯 Deliverables
- OAuth app configuration screenshots
- Consent page visuals
- Access logs showing granted tokens and API calls
- Risk summary of token persistence and data exposure
- Recommendations for user training and admin consent policies

---

### 📚 Reference Materials
- Microsoft OAuth: https://learn.microsoft.com/en-us/azure/active-directory/develop/permissions-consent-framework
- Google OAuth: https://developers.google.com/identity
- Proofpoint & Mandiant reports on OAuth phishing
- GoPhish Toolkit: https://getgophish.com/

---

### 🏷️ Tags / Labels
`phishing` `oauth` `social-engineering` `token-abuse` `junior-friendly` `t1556.006`

---

### 📈 Effort Level
**Medium (M)** — needs test tenant and awareness of app registration flow.

---

### ✅ Acceptance Criteria
- [ ] OAuth app created with phishing-friendly branding
- [ ] At least 3 dangerous scopes tested
- [ ] Documentation of API access + consent flow collected
- [ ] Recommendations delivered for detection and mitigation
