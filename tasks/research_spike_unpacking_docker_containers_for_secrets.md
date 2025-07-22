# 🐳 Research Spike: Unpacking Docker Containers for Secrets

**Goal:**  
Extract and analyze Docker container images (both public and internal registries) to identify embedded secrets, plaintext credentials, tokens, private keys, or configuration mistakes that increase risk.

**Why It Matters:**  
Secrets are often mistakenly baked into container layers — including AWS keys, database passwords, internal hostnames, and SSH keys. These exposures persist even after file deletion, due to Docker’s layered filesystem. Attackers use this to escalate from dev to prod.

---

### ✅ Tasks

- [ ] Pull or access Docker images:
  - From Docker Hub, internal registry, or local repo
  - Use `docker pull`, `docker save`, or `skopeo`
- [ ] Unpack images with:
  - `docker export`, `dive`, or manual tar extraction
  - Inspect all layers (`layer.tar`) for deleted or leftover files
- [ ] Scan for high-risk secrets:
  - Regex matches for `password=`, `aws_secret=`, `PRIVATE KEY`, `.env`, `.pem`, `.crt`, `.kube/config`, `.npmrc`
  - High entropy strings or known key formats
- [ ] Identify:
  - Misconfigured file permissions
  - Hardcoded creds in config/scripts/entrypoints
  - Default creds for exposed apps or databases
- [ ] Optional:
  - Correlate `Dockerfile` with what got baked into image
  - Build auto-scanning CI/CD plugin for container secrets

---

### 🎯 Deliverables

- Container Secret Inventory Report:
  - Image name, secret type, file path, exposure risk
- Redacted screenshots or logs
- Recommendations:
  - Secrets should be injected at runtime (e.g., env vars or secret manager)
  - Add pre-push secret scanners (`docker-slim`, `truffleHog`, `dockle`)
  - Audit image build pipelines for hygiene

---

### 📚 References

- Dive: https://github.com/wagoodman/dive  
- TruffleHog: https://github.com/trufflesecurity/trufflehog  
- DockerSlim: https://github.com/docker-slim/docker-slim  
- MITRE ATT&CK T1552.001 – Credentials in Files  
- OWASP Docker Security Cheat Sheet

---

### 🏷️ Tags

`docker` `containers` `secrets` `image-analysis` `layer-inspection` `t1552.001` `devops-risk` `cicd` `trufflehog` `dockle`

---

### 📈 Effort Level

**Medium (M)** — valuable for junior red teamers or detection engineers learning DevOps attack surfaces.

---

### ✅ Acceptance Criteria

- [ ] Tool or script used to unpack at least 1 image  
- [ ] Secrets or risky configs identified in at least 1 image layer  
- [ ] Output saved in structured format (CSV/JSON) with image name and findings  
- [ ] Recommendations shared with DevOps or container security stakeholders  
- [ ] Tool added to red team recon or post-access toolkit