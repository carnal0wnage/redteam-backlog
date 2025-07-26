# 🧬 Research Spike: Identify Internal Software Libraries for Supply Chain Attack Risk

**Goal:**  
Audit internal codebases, registries, and third-party packages for internally developed or self-hosted libraries that could be abused for software supply chain attacks (e.g., name collisions, pre/post build injection points, dependency trust abuse).

**Why It Matters:**  
Many enterprise codebases rely on internal packages with loose controls — attackers who gain limited access can poison builds, inject malicious code, or shadow dependencies across dev environments.

---

### 🔍 Scope
- Private registries: PyPI (Artifactory), npm, Maven, RubyGems
- Internal shared libraries or SDKs
- Build tools: Jenkins, GitHub Actions, internal CI/CD
- Focus: packages used across projects, deployed in prod

---

### ✅ Tasks
- [ ] Inventory internal packages in dev ecosystem:
  - Python, Node, Java, Ruby, Go
- [ ] Determine which ones are:
  - Used by multiple teams/projects
  - Automatically fetched from internal registries
  - Not monitored for code changes or integrity
- [ ] Check for:
  - Name shadowing risks (e.g., package also available publicly)
  - Pre/post build hooks in package scripts
  - Package publication controls
- [ ] Create threat models for 2–3 abuse paths:
  - Malicious update to a trusted internal lib
  - Developer confusion between internal vs. public version
  - Code injection via CI/CD pipeline misuse

---

### 🎯 Deliverables
- Internal markdown doc or wiki page with:
  - Inventory of high-risk internal libraries
  - Shadowing or trust issues documented
  - Suggested mitigation actions (e.g., signing, monitoring)
- Optional:
  - PoC exploit of postinstall script or version overwrite

---

### 📚 Reference Materials
- OWASP Software Supply Chain Cheat Sheet: https://cheatsheetseries.owasp.org/  
- Dependency Confusion: https://research.nccgroup.com/  
- Supply-chain threat modeling: https://github.com/IEEESA/ossd-maturity-model  
- Npm/yarn preinstall scripts: https://docs.npmjs.com/misc/scripts

---

### 🏷️ Tags / Labels
`supply-chain` `internal-libraries` `devsec` `dependency-confusion` `ci-cd`

---

### 📈 Effort Level
**Medium (M)** — requires cross-team awareness and dev pipeline access.

---

### ✅ Acceptance Criteria
- [ ] At least 5 internal packages evaluated
- [ ] Shadowing or trust weaknesses documented
- [ ] Mitigation plan and sample threat models completed
