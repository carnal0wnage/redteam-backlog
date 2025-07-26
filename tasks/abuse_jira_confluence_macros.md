# 🧩 Research Spike: Abuse Jira/Confluence Macros or Web Panels for Payload Delivery

**Goal:**  
Explore abuse of Jira or Confluence macros and dynamic web panels to deliver payloads (XSS, redirects, JS injection). Evaluate whether red team can use these paths for phishing or C2 stagers.

**Why It Matters:**  
These platforms are widely trusted internally and integrated into DevOps. Malicious content here blends in and can phish or load malware directly into trusted interfaces.

---

### 🔍 Scope
- Confluence HTML macro, iframe macro, gadget macros
- Jira dynamic panels, issue view plugins
- Contexts: ticket views, dashboards, public links

---

### ✅ Tasks
- [ ] Identify common macros or UI components that render HTML/JS
- [ ] Test for:
  - [ ] JS injection
  - [ ] External content loading
  - [ ] Open redirect abuse
- [ ] Craft payload delivery PoC
- [ ] Check visibility/logging and detection coverage

---

### 🎯 Deliverables
- Payload screenshots (JS popup, redirect, token theft)
- Security write-up on risky macro usage
- Remediation guidance (macro policy, CSP headers)

---

### 📚 Reference Materials
- Atlassian Macro Docs: https://developer.atlassian.com/  
- Confluence Security Best Practices  
- Previous bug bounty writeups on Jira/Confluence

---

### 🏷️ Tags / Labels
`jira` `confluence` `xss` `macro-abuse` `lateral-movement`

---

### 📈 Effort Level
**Medium (M)**

---

### ✅ Acceptance Criteria
- [ ] At least one macro payload rendered
- [ ] Risk scenarios documented with screenshots
- [ ] Suggested detection or prevention approaches
