
# 🔐 Research Spike: Enumerate Apps with risky OAuth scopes

**Goal:**  
Determine whether users can grant risky OAuth scopes to third-party apps without admin review. Document tenant-level and app-level consent policies and identify gaps.

**Why It Matters:**  
Unrestricted user consent is a top cause of OAuth abuse. Attackers can trick users into installing malicious apps that silently exfiltrate data — without needing a password or triggering MFA.

---

### 🔍 Scope
- Microsoft Azure AD and Google Workspace
- Admin consent policies, app access control settings
- User-installable apps, app gallery submissions

---

### ✅ Tasks
- [ ] Review current consent policies:
  - Azure: Enterprise Applications > User Settings
  - Google: Admin Console > Security > App Access Control
- [ ] Attempt consent flows as:
  - Standard user
  - Contractor / guest
- [ ] Identify apps that request dangerous scopes (e.g., `offline_access`, `files.read.all`, `mail.read`)
- [ ] Note whether consent succeeds or is blocked
- [ ] Optional: Create a test OAuth app and attempt internal installation

---

### 🎯 Deliverables
- Policy snapshot (screenshots or exports)
- Table of:
  - Consent source
  - Scope requested
  - Success or failure
  - Detection / alerting present?
- Recommendations for tightening tenant-wide and app-specific consent controls

---

### 📚 Reference Materials
- Microsoft Admin Consent Policies: https://learn.microsoft.com/en-us/azure/active-directory/manage-apps/configure-admin-consent-workflow  
- Google App Access Controls: https://support.google.com/a/answer/7281227  
- MITRE ATT&CK T1556.006 – Phishing for OAuth Consent

---

### 🏷️ Tags / Labels
`oauth` `token-abuse` `identity` `azure` `google` `phishing`

---

### 📈 Effort Level
**Medium (M)** — needs test identities and policy access to validate consent outcomes.

---

### ✅ Acceptance Criteria
- [ ] At least 2 risky scope requests tested
- [ ] Consent outcome documented for standard user
- [ ] Recommendation shared for consent enforcement or admin workflows
