# 🛠️ Research Spike: Debug or Health Endpoints Exposure

**Goal:**  
Enumerate, access, and evaluate the security impact of exposed debug and health endpoints like `/debug/pprof`, `/actuator`, `/metrics`, `/status`, and similar. Determine what sensitive data (or control) is exposed and build a quick scanner or checklist to identify them across environments.

**Why It Matters:**  
Debug endpoints are often left exposed in dev or staging environments — and sometimes even in prod. They can leak internal architecture, secrets, or offer ways to execute code or pivot laterally. Many require no auth and are rarely monitored.

---

### 🔍 Scope
- Internal and staging environments preferred
- Public-facing apps only if explicitly scoped
- Common endpoint paths:
  - `/debug/pprof`, `/metrics`, `/actuator`, `/status`, `/healthz`, `/vars`, `/env`, `/swagger`
- Frameworks: Spring Boot, Go, Node.js, Python Flask/FastAPI, Prometheus/Grafana, Kubernetes apps

---

### ✅ Tasks
- [ ] Scan internal and test web apps with wordlists or `ffuf`/`feroxbuster` to identify:
  - `/debug/`, `/metrics`, `/actuator`, `/status`, `/env`, etc.
- [ ] Attempt unauthenticated access to each endpoint
  - [ ] Log what’s exposed: version info, stack traces, internal IPs, configs, env variables
- [ ] Check if the following risks are present:
  - Internal IP disclosure
  - Auth bypass on control endpoints (e.g., `/actuator/shutdown`)
  - Service crash or overload potential
  - `.env` or secret exposure
- [ ] If access is blocked, review HTTP response (403, 401, redirect) for signs of:
  - Insecure auth methods (e.g., Basic Auth)
  - Potential SSRF targets (if these are protected internally)
- [ ] Build a Top 5 "Debug Endpoint Dangers" list based on your findings
- [ ] Write a Nuclei template or add to a detection script for automation

---

### 🎯 Deliverables
- Internal wiki or markdown doc with:
  - Endpoint table (URL, response status, what was exposed)
  - Screenshots of impactful data or dangerous functionality
  - “Top 5 Debug Endpoint Dangers” list (with examples)
  - Custom tool/script/template for scanning/debug-detection
  - Recommended fixes (e.g., auth enablement, route blocking, env hardening)

---

### 📚 Reference Materials
- HackTricks Debug Endpoints: https://book.hacktricks.xyz/pentesting-web/debug-endpoints  
- OWASP Top 10: https://owasp.org/www-project-top-ten/  
- Go pprof docs: https://pkg.go.dev/net/http/pprof  
- Spring Boot Actuator docs: https://docs.spring.io/spring-boot/docs/current/reference/html/actuator.html  
- Nuclei Templates (debug, pprof, actuator): https://github.com/projectdiscovery/nuclei-templates

---

### 🏷️ Tags / Labels
`junior-friendly` `debug-endpoints` `information-disclosure` `misconfig` `web`

---

### 📈 Effort Level
**Small to Medium (S–M)** — lightweight, but great for learning how “boring” endpoints create real risk.

---

### ✅ Acceptance Criteria
- [ ] At least 3 debug/health endpoints identified and tested
- [ ] At least 2 examples where sensitive info or risk is documented
- [ ] “Top 5 Debug Endpoint Dangers” list created with descriptions
- [ ] Scanner template or ffuf/Nuclei rule written and saved
- [ ] Internal wiki page created with screenshots and remediation tips