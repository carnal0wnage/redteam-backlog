
## 🛰️ Research Spike: Custom C2 Channel Development

**Goal:**  
Explore the development of custom command-and-control (C2) channels using covert or commonly permitted communication paths such as DNS over HTTPS (DoH), Slack bots, Telegram bots, Microsoft Teams webhooks, or other SaaS APIs. Build a proof-of-concept agent and controller to demonstrate evasion and communication viability.

**Why It Matters:**  
Traditional C2 frameworks are often blocked, monitored, or sinkholed. Building knowledge of stealthier, application-layer C2 channels improves red team tradecraft and helps defenders design better detection logic for nonstandard channels.

---

### 🔍 Scope
- Internal red team test environment or lab  
- One custom C2 channel: choose from Slack API, Telegram Bot API, DoH, or Webhooks  
- No use against production infrastructure  
- Primary focus: C2 viability, evasion, and detection surface

---

### ✅ Tasks
- [ ] Research existing custom C2 implementations (e.g., C3, merlin, DNSCat2)  
- [ ] Select one channel for PoC (e.g., Slack, Telegram, DoH)  
- [ ] Build a minimal agent + controller to:
  - Beacon
  - Receive task
  - Send response  
- [ ] Add basic evasion features:
  - Randomized timing
  - Payload encoding
  - Traffic camouflage (e.g., mimicking real API requests)  
- [ ] Test in lab environment using monitoring tools (e.g., Zeek, Suricata, Arkime)  
- [ ] Compare network and detection signature to typical Sliver/Mythic C2  
- [ ] Document operational constraints and blue-team detection opportunities

---

### 🎯 Deliverables
- Minimal custom C2 proof-of-concept (client + server)
- Internal write-up or wiki:
  - Design decisions
  - Network visibility impact
  - Evasion techniques used
  - Screenshots or traffic captures
- Bonus: Sigma/Splunk/Zeek rule examples for detection

---

### 📚 Reference Materials
- [C3 Cloud C2 Framework (mdsec)](https://github.com/mdsecactivebreach/C3)  
- [Slack Bot API](https://api.slack.com/bot-users)  
- [Telegram Bot API](https://core.telegram.org/bots/api)  
- [DNSCat2](https://github.com/iagox86/dnscat2)  
- [MITRE ATT&CK – T1095 (Standard Application Layer Protocol)](https://attack.mitre.org/techniques/T1095/)

---

### 🏷️ Tags / Labels
`custom-c2` `covert-channel` `dns` `slack` `telegram` `application-layer` `t1095` `evasion`

---

### 📈 Effort Level
**Medium (M)** — requires moderate programming and network monitoring experience.

---

### ✅ Acceptance Criteria
- [ ] One working custom C2 channel demonstrated in lab
- [ ] Tasking and response successfully implemented
- [ ] Evasion techniques applied (e.g., obfuscation, timing, mimicked traffic)
- [ ] Documentation completed with detection notes and code references
