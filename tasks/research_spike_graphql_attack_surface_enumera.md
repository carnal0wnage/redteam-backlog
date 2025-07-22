# 🔍 Research Spike: GraphQL Attack Surface Enumeration & Exploitation

**Goal:**  
Identify GraphQL endpoints in internal or external web apps, and assess them for common security weaknesses such as introspection leaks, excessive data exposure, access control flaws, and injection attacks.

**Why It Matters:**  
GraphQL APIs are widely adopted but often lack mature security controls. Over-fetching, broken authorization at the resolver level, and verbose error messages make them rich targets for red teams. GraphQL also enables lateral data discovery and deep recon without traditional crawling.

---

### 🔍 Scope

**Common Vulnerabilities in GraphQL APIs:**
- 🧠 Introspection Enabled (query schema for all types/fields)
- 🔓 Broken Access Control (e.g., query other users’ data)
- 💣 Deep Object Nesting DoS
- 📦 Mass Assignment via Input Objects
- 🧵 Injection into Resolvers (SQL/NoSQL/SSRF)
- 🪜 Field-level privilege escalation
- 🔍 Query Batching or Alias Abuse

**Targets:**
- Internal microservices with GraphQL APIs
- Web + mobile apps (React Native, Apollo, Relay)
- Third-party SaaS integrations exposing GraphQL

---

### ✅ Tasks

- [ ] Detect GraphQL endpoints:
  - Look for `/graphql`, `/api/graphql`, or custom routes via Burp / nuclei
- [ ] Test introspection:
  - Send `{ __schema { types { name } } }` or use GraphQL Voyager
- [ ] Enumerate:
  - Queries, mutations, fields, nested objects
  - Hidden admin operations or undocumented fields
- [ ] Exploit:
  - Query other users’ data (IDOR via GraphQL)
  - Use aliases and nested fragments to bypass filters
  - Inject payloads into resolver inputs (SQL, NoSQL, SSRF)
- [ ] Test rate limits, DoS:
  - Deep nesting (`user { friends { friends { friends { ... } } } }`)
- [ ] Test auth/z by replaying queries across roles
- [ ] Build repeatable fuzz scripts with:
  - `GraphQLMap`, `InQL`, `Burp GraphQL extensions`

---

### 🎯 Deliverables

- GraphQL Attack Matrix:
  - Endpoint / Feature / Vuln Type / Exploitable / Mitigated
- Screenshots or Burp logs of successful query/response abuse
- Sample malicious queries (introspection, IDOR, injection)
- Detection recommendations:
  - Disable introspection in prod
  - Enforce auth/z at resolver level
  - Limit depth, alias, and complexity per query
- Optional: GraphQL query fuzzer PoC in Python

---

### 📚 Reference Materials

- GraphQL Security Checklist: https://graphql.security  
- InQL Burp Plugin: https://github.com/doyensec/inql  
- GraphQLmap: https://github.com/swisskyrepo/GraphQLmap  
- GraphQL Voyager: https://github.com/APIs-guru/graphql-voyager  
- MITRE T1210 (Exploitation of Remote Services)  
- OWASP GraphQL Cheat Sheet: https://cheatsheetseries.owasp.org/cheatsheets/GraphQL_Cheat_Sheet.html  

---

### 🏷️ Tags / Labels

`graphql` `api-abuse` `introspection` `t1210` `overfetching` `authorization-bypass` `inql` `burp-suite` `modern-apps`

---

### 📈 Effort Level

**Medium (M)** — requires basic web/API tooling knowledge; payoff can be high with weak GraphQL design.

---

### ✅ Acceptance Criteria

- [ ] At least 1 GraphQL endpoint discovered and mapped via introspection  
- [ ] Sample exploitation path documented (e.g., over-fetch, IDOR, injection)  
- [ ] Detection and hardening recommendations included  
- [ ] Scripted query or fuzzing example delivered  
- [ ] Added to internal appsec red team wiki or repo