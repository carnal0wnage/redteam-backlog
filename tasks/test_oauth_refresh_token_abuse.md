# 🔑 Research Spike: Test for Misuse of OAuth Refresh Tokens in M365/GWS

**Goal:**  
Investigate persistence via OAuth refresh tokens in Microsoft 365 and Google Workspace. Explore what low-visibility scopes allow long-term access to email, Drive, and calendar data.

**Why It Matters:**  
Attackers can retain access long after user password resets by abusing OAuth refresh tokens. These tokens are often overlooked in incident response.

---

### 🔍 Scope
- Microsoft 365: Azure AD apps, Graph API
- Google Workspace: OAuth 2.0 Playground, GCP console apps
- Low-visibility scopes: Gmail.readonly, Files.readonly, offline_access

---

### ✅ Tasks
- [ ] Register low-priv OAuth app with user consent
- [ ] Capture refresh/access tokens
- [ ] Test token validity after:
  - [ ] Password change
  - [ ] Session reset
  - [ ] OAuth app removal
- [ ] Monitor visibility in admin logs

---

### 🎯 Deliverables
- Access scope matrix (token vs. access vs. revocation)
- Timeline of persistence across sessions/resets
- Recommendations for admin monitoring and revocation

---

### 📚 Reference Materials
- Microsoft OAuth: https://learn.microsoft.com/en-us/azure/active-directory/develop/  
- Google OAuth: https://developers.google.com/identity/protocols/oauth2  
- M365 Token Lifetimes: https://learn.microsoft.com/en-us/azure/active-directory/develop/tokens-overview

---

### 🏷️ Tags / Labels
`oauth` `token-abuse` `m365` `google-workspace` `persistence` `cloud`

---

### 📈 Effort Level
**Medium (M)**

---

### ✅ Acceptance Criteria
- [ ] At least 2 token abuse scenarios tested
- [ ] Persistence documented across resets
- [ ] Admin logs reviewed for detection paths
