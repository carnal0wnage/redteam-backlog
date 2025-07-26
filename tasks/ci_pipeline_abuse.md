# 🧪 Research Spike: Audit CI/CD Pipelines for Misconfigurations & Abuse Paths

**Goal:**  
Evaluate the company’s CI/CD pipeline tools (GitHub Actions, GitLab CI, Jenkins, Azure DevOps, etc.) for privilege abuse, exposed secrets, and code execution paths accessible by low-priv users.

**Why It Matters:**  
CI/CD pipelines have access to secrets, deployment credentials, and internal infra. Weak controls here can lead to high-impact supply chain attacks or lateral movement into production environments.

---

### 🔍 Scope
- GitHub Actions, GitLab CI/CD, Jenkins, Azure Pipelines
- Focus on:
  - Secrets injection
  - Shared runners/workers
  - Build artifacts/code output
  - Pipeline triggers from forks/branches

---

### ✅ Tasks
- [ ] Inventory pipelines and linked secrets
- [ ] Test for:
  - [ ] Privilege escalation from PRs/forks
  - [ ] Secret exposure in logs or artifacts
  - [ ] Insecure curl/bash usage in builds
- [ ] Check access control between dev and prod pipelines
- [ ] Validate whether secrets rotate and are scoped properly

---

### 🎯 Deliverables
- Findings doc with:
  - Pipeline inventory and access model
  - PoC for any code injection or secret exposure
- Risk ranking for each pipeline based on data access and trust level
- Suggested mitigation steps for securing pipeline trust zones

---

### 📚 Reference Materials
- GitHub Actions Security Best Practices: https://docs.github.com/en/actions/security-guides  
- CI/CD Threat Modeling: https://cloudsecurityalliance.org  
- GitLab CI Security: https://docs.gitlab.com/ee/ci/

---

### 🏷️ Tags / Labels
`cicd` `supply-chain` `github-actions` `jenkins` `azure-devops` `pipeline-abuse`

---

### 📈 Effort Level
**Medium (M)**

---

### ✅ Acceptance Criteria
- [ ] At least one CI/CD system tested
- [ ] One or more abuse paths documented
- [ ] Recommendations for securing CI workflow created
