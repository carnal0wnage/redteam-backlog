# 🛠️ Research Spike: Research JWT Token Validation for Internal Apps

**Goal:**  
Identify and test weaknesses in JWT access token validation such as missing `aud` checks, weak signing keys, or RS256→HS256 downgrade confusion. Explore token replay and forging in web/cloud apps.

**Why It Matters:**  
JWTs are used everywhere in auth systems, but often poorly validated. Exploiting these weaknesses enables identity spoofing, account takeover, and privilege escalation without needing real creds.

---

### 🔍 Scope
- Target apps using JWT for API access or session cookies
- Focus on self-signed tokens, RS256→HS256 downgrade bugs, and static secrets

---

### ✅ Tasks
- [ ] Capture JWTs from browser, mobile app, or API traffic
- [ ] Analyze token headers: `alg`, `kid`, `typ`
- [ ] Test RS256→HS256 swap and sign with known/empty key
- [ ] Attempt audience injection (`aud`) or impersonation
- [ ] Replay valid tokens in other endpoints or tenants
- [ ] Use `jwt_tool.py`, `jsonwebtoken`, or Burp extensions
- [ ] Optional: Fuzz `kid` to identify SSRF or path traversal attacks

---

### 🎯 Deliverables
- Table of tested tokens and outcomes (valid, bypass, rejected)
- Screenshots of successful forgery or impersonation
- Recommended JWT validation checklist
- Code samples showing crafted tokens

---

### 📚 Reference Materials
- JWT Tool: https://github.com/ticarpi/jwt_tool  
- Auth0 JWT Docs: https://auth0.com/docs/tokens/json-web-tokens  
- PortSwigger Labs: https://portswigger.net/web-security/jwt  
- MITRE ATT&CK – Credential Access (T1552), Token Abuse

---

### 🏷️ Tags / Labels
`jwt` `token-abuse` `authentication-bypass` `t1552` `replay-attacks` `senior-friendly`

---

### 📈 Effort Level
**Medium (M)** — safe in lab, potentially dangerous in real apps if validation is weak.

---

### ✅ Acceptance Criteria
- [ ] At least 3 applications tested for JWT handling
- [ ] RS256→HS256 vulnerability attempted
- [ ] Replay scenarios documented
- [ ] Token security checklist shared with engineering
