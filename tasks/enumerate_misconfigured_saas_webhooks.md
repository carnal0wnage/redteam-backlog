# 🔗 Research Spike: Enumerate Misconfigured SaaS Webhooks (Slack, GitHub, Asana, etc)

**Goal:**  
Identify misconfigured or overly permissive webhook integrations in common SaaS platforms such as Slack, GitHub, and Asana. Evaluate opportunities for data leakage or command injection.

**Why It Matters:**  
Webhooks often transmit sensitive data between systems. When exposed publicly or improperly scoped, they can allow attackers to trigger workflows or siphon information silently.

---

### 🔍 Scope
- Slack outgoing/incoming webhooks
- GitHub repo webhooks
- Asana task automation/webhooks
- Internal services that consume webhook data

---

### ✅ Tasks
- [ ] Enumerate webhook URLs, secrets, payload schemas
- [ ] Check for:
  - [ ] Exposed webhook URLs in repos or code
  - [ ] Lack of request signing or validation
  - [ ] Misconfigured triggers (e.g., any PR triggers sensitive automation)
- [ ] Replay requests to test spoofing/triggering workflows
- [ ] Capture webhook payloads for sensitive data

---

### 🎯 Deliverables
- Table of SaaS webhooks, endpoint URLs, permissions, validation
- Replay PoCs and screenshots
- Recommendations for validation, scoping, secret storage

---

### 📚 Reference Materials
- GitHub Webhooks: https://docs.github.com/en/webhooks  
- Slack Webhooks: https://api.slack.com/messaging/webhooks  
- Asana Webhooks: https://developers.asana.com/docs/webhooks

---

### 🏷️ Tags / Labels
`saas` `webhooks` `slack` `github` `asana` `supply-chain`

---

### 📈 Effort Level
**Medium (M)**

---

### ✅ Acceptance Criteria
- [ ] At least 3 services tested
- [ ] Replay tested and weaknesses documented
- [ ] Security recommendations produced
