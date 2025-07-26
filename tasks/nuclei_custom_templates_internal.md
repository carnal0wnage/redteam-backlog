# 🧪 Research Spike: Create Nuclei Scans + Custom Templates for Internal Apps

**Goal:**  
Automate Nuclei scans using custom templates tailored to the organization’s internal applications, including custom auth, headers, and routing quirks.

**Why It Matters:**  
Internal attack surface often hides behind custom middleware or weird auth flows. Customizing detection templates enables deeper, safer, and more relevant web vulnerability scans.

---

### 🔍 Scope
- Internal staging/dev apps
- Auth types: JWT, SAML, header-based auth
- Existing Nuclei templates as base

---

### ✅ Tasks
- [ ] Identify 3–5 common internal app patterns (e.g., auth, routing)
- [ ] Fork Nuclei repo or use local template set
- [ ] Build custom templates for:
  - [ ] Verbose errors
  - [ ] Debug routes
  - [ ] Secrets in responses
- [ ] Write script to:
  - [ ] Run Nuclei across internal subnets
  - [ ] Handle auth tokens per app
- [ ] Output JSON or markdown reports

---

### 🎯 Deliverables
- Custom Nuclei templates (.yaml)
- Automation wrapper script (bash/python)
- Sample output for at least 3 apps
- Wiki doc: how to run, update, extend templates

---

### 📚 Reference Materials
- Nuclei templates: https://github.com/projectdiscovery/nuclei-templates  
- Custom template guide: https://nuclei.projectdiscovery.io

---

### 🏷️ Tags / Labels
`nuclei` `internal-apps` `template-dev` `scanner-automation`

---

### 📈 Effort Level
**Medium (M)** — strong for junior–mid folks learning recon customization.

---

### ✅ Acceptance Criteria
- [ ] 3+ custom Nuclei templates created and validated
- [ ] Wrapper script handles auth and reports cleanly
- [ ] Output shared on internal wiki
