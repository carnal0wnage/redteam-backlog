# 🔁 Research Spike: Test for Open Redirects

**Goal:**  
Identify open redirect vulnerabilities in internal web applications that can be abused in phishing or session hijacking scenarios. Simulate and validate redirect chains to untrusted domains.

**Why It Matters:**  
Open redirects are low-complexity but high-leverage vulnerabilities often used in phishing campaigns. They allow attackers to abuse trusted domains to redirect victims to malicious infrastructure, bypassing URL filters and raising user trust.

---

### 🔍 Scope
- Internal web applications (portals, tools, dashboards)
- Parameters like `?redirect=`, `?url=`, `?next=`, `?target=`
- Focused on GET requests; no destructive testing

---

### ✅ Tasks
- [ ] Use tools like:
  - `ParamSpider`, `Burp Suite`, or `OWASP ZAP` to identify redirect parameters
- [ ] Test payloads such as:
  - `/login?redirect=https://evil.com`
  - URL-encoded versions (`%2F%2Fevil.com`, base64 variants)
- [ ] Verify if:
  - Redirect occurs with no warning or validation
  - Referrer leaks or token propagation occurs
- [ ] Simulate phishing chain:
  - Trusted domain → open redirect → fake login page
- [ ] Document filters or protections (if any)

---

### 🎯 Deliverables
- List of vulnerable endpoints with:
  - URL and parameter
  - Payloads tested
  - Redirect behavior observed
- Screenshots or Burp Suite request/response pairs
- Risk summary:
  - How redirect could be abused in phishing or token theft
  - Trust context of target domain
- Recommendations:
  - Use allowlist validation
  - Warn on external redirection
  - Strip auth tokens before redirection

---

### 📚 Reference Materials
- OWASP Open Redirect: https://owasp.org/www-community/attacks/Unvalidated_Redirects_and_Forwards  
- PortSwigger: https://portswigger.net/web-security/open-redirection  
- Bug bounty examples: https://hackerone.com/reports/108345  
- Burp Suite Guide: https://portswigger.net/burp/documentation/desktop/tools/repeater

---

### 🏷️ Tags / Labels
`junior-friendly` `web` `phishing` `open-redirect` `burp-suite` `t1071` `url-manipulation`

---

### 📈 Effort Level
**Small (S)** — lightweight, repeatable, with common tooling.

---

### ✅ Acceptance Criteria
- [ ] At least 5 apps or endpoints tested
- [ ] At least 1 redirect confirmed and documented
- [ ] Payloads logged and shared internally
- [ ] Recommendations written to harden redirect behavior
