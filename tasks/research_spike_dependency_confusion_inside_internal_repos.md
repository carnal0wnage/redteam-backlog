# 📦 Research Spike: Dependency Confusion Inside Private Artifact Mirrors

**Goal:**  
Simulate dependency confusion attacks by publishing malicious packages that exploit namespace shadowing and version preemption within internal artifact mirrors (e.g., JFrog Artifactory, Sonatype Nexus, GitHub Packages). Measure which internal builds pull from external sources and document risky patterns in CI/CD usage.

**Why It Matters:**  
Many enterprises rely on internal package mirrors or proxies — but poor namespace hygiene or proxy configurations allow attackers to “shadow” internal package names or insert higher semantic versions. This leads to silent remote code execution in build systems, CICD, or developer workstations.

---

### 🔍 Scope
- Target ecosystems:
  - npm, PyPI, RubyGems, Maven, NuGet
- Internal tooling:
  - Artifactory, Nexus, GitHub Packages, CodeArtifact
- Environments:
  - Dev pipelines, developer local installs, CI/CD agents
- Out-of-scope:
  - Exploitation outside of authorized lab or red team engagement
  - No publishing to public mirrors without ethical disclosure

---

### ✅ Tasks
- [ ] Build simulation lab:
  - Internal artifact proxy (e.g., Artifactory + npm mirror)
  - Test pipelines with mocked internal package dependencies
- [ ] Identify targets:
  - Internal package names that are *not* claimed externally
  - Common typos or legacy internal packages with no namespace protection
- [ ] Publish attacker-controlled package:
  - Use same name or higher semver (e.g., `1.99.99`) to preempt
  - Host via public registry (PyPI, npmjs, etc.)
- [ ] Run build pipeline and observe:
  - Does the external package get pulled?
  - Is it cached internally?
  - Any logs/alerts/audit events?
- [ ] Create detection or mitigation playbooks:
  - Block outbound resolution for internal-only namespaces
  - Require private scopes (e.g., `@company/packagename`)
  - Disable fallback to public mirrors in proxies

---

### 🎯 Deliverables
- Lab setup and source code (docker-compose, example builds)
- List of vulnerable dependency resolution patterns (e.g., implicit semver, no registry lock)
- Screenshots of successful preemption
- Artifact proxy misconfig matrix (e.g., Artifactory “Allow Remote Download”)
- Detection rules and blocklist config examples
- Supply chain security recommendations tailored to org’s languages

---

### 📚 Reference Materials
- Original Disclosure by Alex Birsan: https://medium.com/@alex.birsan/dependency-confusion-4a5d60fec610  
- GitHub Advisory: https://github.blog/2021-02-12-avoiding-npm-substitution-attacks/  
- OWASP Dependency Confusion Guide: https://owasp.org/www-project-dependency-check/  
- Artifactory Proxy Security: https://jfrog.com/knowledge-base/  
- MITRE ATT&CK T1195.002 (Compromise Software Supply Chain): https://attack.mitre.org/techniques/T1195/002/  

---

### 🏷️ Tags / Labels
`dependency-confusion` `artifact-proxy` `ci-cd` `supply-chain` `semantic-versioning` `namespace-shadowing` `npm` `pypi` `t1195.002`

---

### 📈 Effort Level
**Medium (M)** — requires simulation setup, CI/CD insight, and language-specific testing.

---

### ✅ Acceptance Criteria
- [ ] Simulated lab with working artifact proxy and CI pipeline
- [ ] At least one successful namespace shadow + semver preemption
- [ ] Observed package pull from public registry inside internal build
- [ ] Patterns of risky behavior cataloged
- [ ] Mitigations and proxy block rules documented

## ⚙️ Research Spike: CI/CD Misconfiguration Detection via Nuclei & Scanning

**Goal:**  
Scan internal and/or external attack surface for misconfigured CI/CD tooling (Jenkins, GitLab, GitHub Actions, ArgoCD, TeamCity, etc.) using signature-based scanning with tools like Nuclei. Identify common weak configurations that expose build logs, secrets, dashboards, or pipelines.

**Why It Matters:**  
CI/CD infrastructure often lives in “trusted” zones and is overlooked in asset discovery. But it frequently leaks sensitive information, uses weak access control, or exposes risky web endpoints — leading to privilege escalation or full source/code compromise.

---

### 🔍 Scope
- Platforms: Jenkins, GitLab, ArgoCD, Tekton, TeamCity, DroneCI, Buildkite, Bamboo, etc.
- Targets:
  - Dev/test subdomains
  - On-prem dashboard endpoints
  - Cloud-exposed API routes
- Weak configurations of interest:
  - Anonymous dashboard access
  - Exposed `.env` or pipeline logs
  - Misconfigured webhook endpoints
  - Default credentials or tokens in metadata

---

### ✅ Tasks
- [ ] Scan with `httpx` and `nuclei` against internal & known external endpoints
  - Subdomain targets: `*.ci.*`, `*.build.*`, `*.dev.*`
  - Tech fingerprinting (open ports, server headers, JARM)
- [ ] Use relevant Nuclei templates:
  - `cicd/jenkins-detect.yaml`, `cicd/gitlab-panel.yaml`, `exposures/logs/`
  - Custom probes for `.gitlab-ci.yml`, `pipeline.yaml`, `.drone.yml`
- [ ] Validate findings manually:
  - Visit dashboards, test auth, look for logs/secrets/tokens
- [ ] Catalog findings by severity:
  - From “panel exposed” → “pipeline RCE path” via script injection or token abuse

---

### 🎯 Deliverables
- Output of all scans (httpx + nuclei + custom probes)
- Asset list of CI/CD tools with status and tech detected
- Vulnerability matrix:
  - Tool / Endpoint / Weakness / Severity / Exploitability
- Screenshots of unauthenticated access or leak points
- Suggested detections:
  - WAF/EDR logs, Shodan queries, Canary paths
- Recommendations:
  - Disable guest mode / anonymous access
  - Secure webhook endpoints
  - Review pipeline secrets management
  - Monitor `.gitlab-ci.yml`, `.env`, or job logs for token leakage

---

### 📚 Reference Materials
- Nuclei Templates (CI/CD): https://github.com/projectdiscovery/nuclei-templates  
- Project Discovery Toolset: https://projectdiscovery.io/  
- OWASP CI/CD Security Guide: https://owasp.org/www-project-cicd-security/  
- GitLab Secure Config Practices: https://docs.gitlab.com/ee/ci/secrets/  
- MITRE ATT&CK T1080 (CI/CD Compromise): https://attack.mitre.org/techniques/T1080/  

---

### 🏷️ Tags / Labels
`ci-cd` `misconfig` `nuclei` `httpx` `jenkins` `gitlab` `pipeline-leak` `t1080` `enumeration` `detection`

---

### 📈 Effort Level
**Medium (M)** — mostly scanning and verification with light manual testing.

---

### ✅ Acceptance Criteria
- [ ] Nuclei scans completed across defined assets
- [ ] All identified CI/CD platforms fingerprinted and documented
- [ ] At least 2 high-confidence misconfigs confirmed
- [ ] Recommendations and detections proposed
- [ ] Screenshots and logs added to wiki or Jira ticket