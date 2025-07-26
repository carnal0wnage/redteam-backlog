# 🛡️ Research Spike: Audit OAuth App Registrations in Azure / Google

**Goal:**  
Audit all enterprise OAuth app registrations in Microsoft Azure AD and Google Workspace to identify risky configurations like missing publisher verification, weak permission controls, or apps that bypass MFA.

**Why It Matters:**  
Misconfigured OAuth apps can become stealthy backdoors, especially when users can consent to risky scopes. Publisher verification and MFA enforcement are often overlooked in OAuth governance.

---

### 🔍 Scope
- Azure AD: Enterprise Applications, App Registrations
- Google Workspace: OAuth Client IDs, third-party apps
- Permissions, publisher status, MFA access settings

---

### ✅ Tasks
- [ ] Enumerate all registered OAuth apps via:
  - Azure AD Portal or `Get-AzureADApplication`
  - Google Workspace Admin > Security > App Access Control
- [ ] Identify:
  - Apps not marked as **Verified Publisher**
  - Apps with risky scopes (`mail.read`, `files.read.all`, etc.)
  - Apps not requiring MFA or bypassing conditional access
  - Apps users can install without admin consent
- [ ] Document:
  - Consent settings (admin-only vs user-consent allowed)
  - MFA policy coverage for app-based logins
- [ ] Optional: Test consent flow for a sample app and validate enforcement

---

### 🎯 Deliverables
- Spreadsheet or table of all app registrations:
  - App name, scopes, publisher status, consent model, MFA status
- Screenshots of risky apps and consent settings
- Summary report with:
  - % apps without verification
  - Apps bypassing MFA
  - Suggested policy improvements

---

### 📚 Reference Materials
- Microsoft Verified Publisher: https://learn.microsoft.com/en-us/azure/active-directory/develop/publisher-verification-overview  
- Google OAuth Access Controls: https://support.google.com/a/answer/7281227  
- Microsoft Conditional Access Policies: https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/

---

### 🏷️ Tags / Labels
`oauth` `azure` `gws` `token-abuse` `identity` `mfa`

---

### 📈 Effort Level
**Medium (M)** — requires admin access to identity platforms and careful review of app entries.

---

### ✅ Acceptance Criteria
- [ ] All apps reviewed and categorized
- [ ] At least 3 risky apps identified
- [ ] Recommendations provided to identity team
