
# 🔐 Research Spike: Enumerate Overly Permissive OAuth Scopes

**Goal:**  
Identify and document dangerous OAuth scope combinations across major platforms (Microsoft, Google, GitHub, etc.), such as `offline_access`, `mail.read`, or `repo`, which could allow long-lived access or lateral movement.

**Why It Matters:**  
OAuth scopes are often granted without full understanding of their implications. Scopes like `offline_access` allow long-term persistence, while others grant access to emails, repositories, or calendar data. Abusing these permissions is a common attacker tactic in real-world breaches and BEC campaigns.

---

### 🔍 Scope
- Major OAuth platforms:
  - Microsoft (Azure AD / Microsoft 365)
  - Google Workspace
  - GitHub / GitLab
- Third-party integrations and in-house OAuth applications
- Focus on: `offline_access`, `repo`, `mail.read`, `calendar`, `user.readwrite.all`, etc.

---

### ✅ Tasks
- [ ] Identify OAuth apps in your environment using:
  - Azure: `Get-AzureADServicePrincipal` / Entra portal
  - Google: Admin console / GAM tool
  - GitHub: `gh auth status`, OAuth tokens in account settings
- [ ] Enumerate scopes granted to each app:
  - Look for tokens stored in browsers, localStorage, or apps
- [ ] Create a table of scope combinations:
  - App name, platform, scopes granted, user consent vs admin approval
- [ ] Highlight dangerous scope combos, such as:
  - `offline_access` + `mail.read`
  - `repo` (private repo access)
  - `calendar.readwrite` + `contacts.read`
- [ ] Identify long-lived tokens and refresh token capabilities
- [ ] Test what each scope actually allows using test users or accounts
- [ ] Document which apps bypass DLP/MFA/email filters via scopes

---

### 🎯 Deliverables
- Markdown or Confluence table of risky OAuth apps and scope combinations
- Screenshots of consent screens or admin views
- Risk matrix mapping OAuth apps by data access + longevity
- Recommendations for:
  - Limiting scope grants
  - Requiring admin approval
  - Revoking unused app authorizations

---

### 📚 Reference Materials
- Microsoft OAuth 2.0 Scopes: https://learn.microsoft.com/en-us/azure/active-directory/develop/permissions-consent-overview
- Google OAuth Scopes: https://developers.google.com/identity/protocols/oauth2/scopes
- GitHub OAuth Scopes: https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/scopes-for-oauth-apps
- MITRE ATT&CK – Valid Accounts (Cloud): https://attack.mitre.org/techniques/T1078/004/
- BEC/OAuth Abuse Reports: Proofpoint, Mandiant blogs

---

### 🏷️ Tags / Labels
`oauth` `scope-analysis` `cloud-security` `junior-friendly` `t1078.004` `token-abuse`

---

### 📈 Effort Level
**Medium (M)** — analysis is non-intrusive but requires time to collect and interpret scope data across multiple providers.

---

### ✅ Acceptance Criteria
- [ ] Minimum 5 OAuth apps reviewed across 2+ platforms
- [ ] List of dangerous scope combinations produced
- [ ] Long-lived token and refresh scope usage documented
- [ ] Recommendations delivered to IAM/SaaS owners
