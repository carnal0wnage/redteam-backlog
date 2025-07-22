
## 🛂 Research Spike: MFA Gaps in Internal & External Services

**Goal:**  
Identify all internal and external systems where valid credentials can be used without multi-factor authentication (MFA). Categorize each service by account type (user, contractor, service account, etc.) and risk level. Focus on systems reachable via the internet or internal VPN entry points.

**Why It Matters:**  
Attackers frequently begin with valid credentials. If MFA is not enforced consistently across services, even low-privilege accounts can become entry points or pivots — especially in SaaS, legacy systems, or misconfigured SSO integrations.

---

### 🔍 Scope
- Internet-facing and internal services: VPN, SSO portals, Git, Jira, email, SaaS apps  
- Authentication methods: SAML, OIDC, local login, LDAP, Kerberos  
- MFA enforcement types: none, optional, enforced, conditional (IP/device-based)

---

### ✅ Tasks
- [ ] Inventory all systems that accept user login (internal + external):
  - VPNs / firewalls / remote access portals
  - Email (OWA, Gmail, Exchange)
  - SSO portals (Okta, Azure AD, Duo, Ping)
  - Developer tools (GitHub, GitLab, Jenkins, Artifactory)
  - Productivity tools (Confluence, Jira, Notion, Zoom, Slack)
- [ ] For each system, test login flows using:
  - [ ] Internal employee account
  - [ ] Contractor / vendor account
  - [ ] Service account (if applicable)
- [ ] Identify whether MFA is:
  - Not required
  - Enforced after first login
  - Enforced always
  - Enforced only in certain networks or devices
- [ ] Log session behavior:
  - Can you reuse session tokens?
  - Can you bypass MFA via alternate auth flows?
- [ ] Track failures and MFA enforcement gaps

---

### 🎯 Deliverables
- Table of systems with MFA enforcement status and exceptions:
  - System name
  - Login type
  - MFA status (none, partial, full)
  - Notes on enforcement bypass or configuration issues
- Screenshots or session logs showing MFA gaps
- Summary of:
  - High-risk systems without MFA
  - MFA bypass opportunities
  - Inconsistent enforcement across identity tiers
- Recommendations for IAM enforcement, conditional access, and SaaS hardening

---

### 📚 Reference Materials
- MITRE ATT&CK T1078 – Valid Accounts: https://attack.mitre.org/techniques/T1078/  
- Microsoft MFA rollout guide: https://learn.microsoft.com/en-us/security/compass/mfa  
- Okta MFA enforcement rules: https://help.okta.com/  
- SAML MFA bypass techniques: https://posts.specterops.io/  
- Common MFA misconfigurations: https://www.raxis.com/blog/mfa-misconfigurations/

---

### 🏷️ Tags / Labels
`mfa` `identity` `access-control` `valid-accounts` `sso` `iam` `cloud-security` `t1078`

---

### 📈 Effort Level
**Medium (M)** — requires multi-account testing and SSO/SaaS familiarity.

---

### ✅ Acceptance Criteria
- [ ] At least 10 systems tested for MFA enforcement
- [ ] MFA status clearly logged for each account type
- [ ] At least 2 high-risk systems identified without MFA
- [ ] Recommendations documented and shared internally
