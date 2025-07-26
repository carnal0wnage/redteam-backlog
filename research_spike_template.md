# 📘 Red Team Research Spike Template

This markdown file serves as the **default template** and guide for all research spikes in this GitHub repository. Each spike represents a focused, time-boxed exploration of a technique, tool, or tactic relevant to red team operations.

---

### 🔍 What’s a Research Spike?

A **spike** is a small, exploratory research task used to answer a question, validate a tool, or investigate a technique. It should produce a concrete deliverable: a script, PoC, demo, internal documentation, or security recommendation. Spikes are designed to help red teamers build repeatable tradecraft and improve internal capabilities.

---

### 📑 Standard Fields

Each `.md` file in this repo follows the format below:

```
## 🎯 Research Spike: [Title Here]

**Goal:**  
Briefly describe what you're exploring and why.

**Why It Matters:**  
Explain the security or operational value of this research.

---

### 🔍 Scope
Clarify what’s in scope (systems, users, apps) and what’s out. Be specific.

---

### ✅ Tasks
- [ ] Step-by-step activities to try
- [ ] Include tools, scripts, or manual tests
- [ ] Reference command lines or payload formats if helpful

---

### 🎯 Deliverables
List what you'll submit: screenshots, PoCs, internal wiki post, detection rules, etc.

---

### 📚 Reference Materials
Link out to GitHub projects, blogs, MITRE ATT&CK, vendor docs, etc.

---

### 🏷️ Tags / Labels
`junior-friendly`, `cloud`, `aws`, `windows`, `osx`, `tactic`, `infra`, `identity`, etc.

---

### 📈 Effort Level
**Small (S)** – 1-2 hours  
**Medium (M)** – 2-4 hours  
**Large (L)** – Multi-day / cross-team

---

### ✅ Acceptance Criteria
Checklist for what a “done” spike looks like.
```

---

### 🧪 Example Use Cases

- Test a new phishing lure or initial access tactic
- Explore abuse of OAuth scopes or refresh tokens
- Audit IAM or permission boundaries in cloud accounts
- Build a custom C2 channel or obfuscation method
- Identify internal systems vulnerable to overlooked misconfigs

---

### 👩‍💻 How to Contribute

1. Copy this template to a new `.md` file with a descriptive name.
2. Complete each section with enough detail for another team member to reproduce.
3. Keep it scoped — spikes should answer a clear question or test a specific hypothesis.
4. Submit PRs or push internally depending on your workflow.

---

### 🧷 Notes

- All spikes should be approved and tracked in Jira/GitHub Issues if part of sprint planning.
- Only conduct live tests in approved sandboxes, dev, or lab environments unless authorized.

---

### 📎 Tags Glossary

- `junior-friendly` – Tasks suitable for newer team members
- `infra` – Red team infrastructure, redirectors, C2
- `cloud` / `aws` / `azure` / `gcp` – Cloud-specific content
- `identity` – IAM, credential abuse, MFA bypass
- `persistence`, `priv-esc`, `initial-access`, `lateral` – ATT&CK-aligned tactics
- `tactic:TA0003` – Use MITRE Tactic and Technique IDs for filtering
- Feel free to add more or dont...IDC
