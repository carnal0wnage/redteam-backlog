# 📬 Research Spike: Abuse Google Workspace OAuth Scopes to Persist & Read User Mail

**Goal:**  
Craft a PoC app that abuses Google Workspace OAuth scopes (e.g., `Gmail.readonly`, `Drive.readonly`) to silently persist access to user data. Emulate techniques seen in OAuth token abuse and cloud persistence.

**Why It Matters:**  
OAuth-based persistence is stealthy and often overlooked in enterprise threat models. Once authorized, attackers can retain long-term access even after a password reset — and the abuse can be hard to detect without deep audit logs.

---

### 🔍 Scope
- Google Workspace tenant (test/dev instance)
- OAuth2 app registration and client secrets
- Target scopes: `https://www.googleapis.com/auth/gmail.readonly`, `drive.readonly`, `openid profile`

---

### ✅ Tasks
- [ ] Register a fake or test Google Cloud OAuth app
- [ ] Craft the auth URL requesting `Gmail.readonly` (low-visibility scope)
- [ ] Deliver to user via phishing, redirection, or self-sign-in
- [ ] Capture refresh token after successful login
- [ ] Use token to:
  - [ ] Read recent email content
  - [ ] Enumerate labels and threads
  - [ ] Log interesting data (internal comms, password resets, alerts)
- [ ] Optional: Build refresh-loop to maintain access
- [ ] Document audit log visibility and detection signals

---

### 🎯 Deliverables
- PoC OAuth app + redirector
- Token capture and replay script
- Sample email access logs or redacted content
- Summary of abuse potential
- Blue-team guide:
  - Detect unknown OAuth apps
  - Monitor unusual scope grants
  - Enforce domain-wide app approval

---

### 📚 Reference Materials
- Google OAuth 2.0 Docs: https://developers.google.com/identity/protocols/oauth2  
- MITRE ATT&CK:  
  - T1528 – Steal Application Access Token  
  - T1530 – Data from Cloud Storage  
  - T1557.003 – Cloud-based Phishing  
- OAuthScopeCreep: https://labs.withsecure.com/publications/oauth-scope-creep  
- Red Canary OAuth Persistence blog: https://redcanary.com/blog/oauth-token-abuse/

---

### 🏷️ Tags / Labels
`cloud-persistence` `oauth` `google-workspace` `t1528` `phishing` `token-abuse` `gmail`

---

### 📈 Effort Level
**Medium (M)** — requires some cloud familiarity and OAuth client setup.

---

### ✅ Acceptance Criteria
- [ ] Working test app that grants access to `Gmail.readonly`
- [ ] Refresh/access token collected and used to query inbox
- [ ] PoC includes red team usage notes and blue team detections
- [ ] Markdown documentation delivered with links and code examples
