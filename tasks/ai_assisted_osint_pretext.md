# 🎭 Research Task: AI-Assisted Custom Pretext Generation from OSINT

**Goal:**  
Use collected OSINT (email, social profiles, interests, public posts, org charts, etc.) and feed it into an AI model (like GPT or Claude) to generate realistic and context-specific social engineering pretexts for each target. Evaluate quality, believability, and red team utility.

**Why It Matters:**  
Custom pretexts drastically increase the success rate of phishing, vishing, and impersonation attacks. Automating this with AI allows red teams to scale while maintaining realism.

---

### 🔍 Scope
- Targets with available public OSINT (LinkedIn, Twitter/X, GitHub, blog posts, conference talks, etc.)
- Use only ethical and approved red team operations or simulations
- AI model must be used securely (no PII to external models unless internally hosted)

---

### ✅ Tasks
- [ ] Define OSINT input schema (e.g., name, title, known interests, public posts, org structure)
- [ ] Write or adapt a script to take structured OSINT and pass it to an LLM with prompt templates
- [ ] Create prompt library for:
  - [ ] Email phishing
  - [ ] SMS/lure message
  - [ ] Vishing call pretext
  - [ ] Social media impersonation
- [ ] Run multiple examples and rate outputs for believability and originality
- [ ] Tune prompts for tone (friendly, urgent, professional, casual)
- [ ] Optional: Add tone or style matching to real emails if available

---

### 🎯 Deliverables
- Prompt templates
- OSINT-to-pretext automation script
- At least 5 generated pretexts for distinct personas
- Evaluation notes or scoring rubric for realism/utility
- Risk and ethics review doc (especially if model is external)

---

### 📚 Reference Materials
- GPT Prompt Engineering for SE: https://github.com/jordanpotti/prompt-injection
- OpenAI GPT APIs: https://platform.openai.com/docs
- OSINT sources: LinkedIn, Pipl, Hunter.io, GitHub, Twitter/X
- DEF CON SECTF archives: https://www.social-engineer.org/sectf/

---

### 🏷️ Tags / Labels
`ai-assisted` `osint` `social-engineering` `phishing` `vishing` `automation`

---

### 📈 Effort Level
**Medium (M)** — Requires OSINT input, prompt engineering, and model safety considerations.

---

### ✅ Acceptance Criteria
- [ ] Script accepts structured OSINT input and produces tailored pretexts
- [ ] Pretexts are stored with target metadata and scenario type
- [ ] Minimum 5 test personas processed
- [ ] At least 3 different pretext types generated per persona
- [ ] Risk and ethical implications reviewed with stakeholders
