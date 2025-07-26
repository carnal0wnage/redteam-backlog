# 🔐 Research Spike: Abuse Misconfigured .npmrc, .pypirc, .dockerconfig Files

**Goal:**  
Identify and exploit misconfigured or exposed developer configuration files like `.npmrc`, `.pypirc`, and `.docker/config.json` that contain plaintext credentials or access tokens to internal/private registries.

**Why It Matters:**  
These files often contain hardcoded tokens or credentials that allow pulling or publishing to private package registries. If leaked or improperly secured, they can enable code tampering, dependency poisoning, or unauthorized access to proprietary packages.

---

### 🔍 Scope
- Developer workstations
- Internal CI/CD environments (build runners, containers)
- Public and private source code repositories
- Container images or base layers with build config files

---

### ✅ Tasks
- [ ] Search for `.npmrc`, `.pypirc`, and `.docker/config.json` using:
  - `find`, `grep`, or `fd` on Linux/macOS
  - Custom YARA or regex rules in source code
- [ ] Identify if tokens or passwords are present:
  - Look for `authToken`, `_auth`, `username/password`, or base64 blobs
- [ ] Attempt to use the credentials to:
  - Pull from internal or cloud-based registries
  - Push poisoned packages (with permission)
- [ ] Check CI/CD environments:
  - Look for these files in build logs, Dockerfile ADD/COPY steps, or mounted volumes
- [ ] Optional:
  - Create a poisoned dependency to test if build pipelines automatically install it
  - Audit registry permissions for privilege escalation

---

### 🎯 Deliverables
- Inventory of identified misconfigured config files
- Table of accessible registries and level of access (read/write)
- Proof-of-concept pull/push actions (where allowed)
- Recommendations:
  - Use credential helpers
  - Enforce vault-backed secrets
  - Avoid storing tokens in plaintext
  - Rotate exposed credentials

---

### 📚 Reference Materials
- npm config file: https://docs.npmjs.com/cli/v9/configuring-npm/npmrc  
- PyPI config: https://packaging.python.org/en/latest/specifications/pypirc/  
- Docker credential store: https://docs.docker.com/engine/reference/commandline/login/  
- Registry poisoning example: https://blog.reversinglabs.com/software-supply-chain-attacks  
- Aqua Security's supply chain research: https://blog.aquasec.com  

---

### 🏷️ Tags / Labels
`secrets` `developer-config` `registry-abuse` `npm` `pypi` `docker` `junior-friendly`

---

### 📈 Effort Level
**Medium (M)** — basic scanning is straightforward, but exploitation depends on access levels and registry configurations.

---

### ✅ Acceptance Criteria
- [ ] At least 3 file types scanned across multiple systems or repos
- [ ] At least one vulnerable config file discovered or validated
- [ ] PoC registry access attempt documented
- [ ] Summary report or internal wiki writeup with mitigation steps
