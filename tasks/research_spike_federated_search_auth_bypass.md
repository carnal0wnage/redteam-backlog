# 🛰️ Research Spike: Federated Search Auth Bypass

**Goal:**  
Identify ways to abuse federated search platforms (e.g., Elastic Enterprise Search, Splunk Federated Search, Microsoft 365 Graph Search, or Google Workspace Indexing) to bypass segmentation, access controls, or data governance boundaries by crafting targeted queries. Basically, we are checking if any of the federated search tools like Glean, Gsuite tools or other things are over permissioned and allow you to see content you shouldnt.

**Why It Matters:**  
Enterprises increasingly use federated search to unify access across data silos. However, misconfigured connectors, poorly scoped indexes, and over-permissive Graph APIs often allow attackers to read sensitive documents, emails, or logs they shouldn't — silently and at scale.

---

### 🔍 Scope
- Platforms & connectors:
  - Elastic Enterprise Search → SharePoint, OneDrive
  - Splunk Federated Search → remote clusters, cold storage
  - Microsoft 365 Graph → Teams chat, mailbox, files
  - Google Cloud Search → GDrive, Gmail, Vault
- Abuse paths:
  - Query shaping to trick index scopes (e.g., `path:*//finance/*`)
  - Wildcard expansion revealing extra content
  - Source-side ACLs bypassed by overly trusted connector
- Threat model:
  - Insider or low-privileged user abusing federated tooling
  - Red team member post-access attempting lateral view

---

### ✅ Tasks
- [ ] Set up federated search in test/lab environment:
  - Connectors to M365, GDrive, or Splunk remote
- [ ] Identify misconfigured connector types:
  - Over-permissive source access
  - Improper result filtering
  - No per-user enforcement at query time
- [ ] Craft queries:
  - Use wildcards, regex, nested path traversal
  - Test search against scoped vs. unscoped permissions
- [ ] Simulate role escalation or shadow access:
  - E.g., search "CEO confidential" from intern user role
- [ ] Build basic test harness (Python or PowerShell)
  - Scripted Graph/Elastic queries with role context switching

---

### 🎯 Deliverables
- Test harness (API query tool with role simulator)
- Misconfigured connector patterns (vendor + config details)
- Sample queries for:
  - Exfil of documents
  - Lateral mail index abuse
  - Vault/GDrive reach-around access
- Sigma or detection rules:
  - Large wildcard queries
  - Role mismatch access events
  - Repeated Graph “searchQuery” calls with pattern fuzzing
- Strategic mitigation:
  - Enforce least privilege in connectors
  - Role-aware query filtering at federation layer
  - Visibility into search queries and responses

---

### 📚 Reference Materials
- Elastic Enterprise Search Docs: https://www.elastic.co/enterprise-search/  
- Microsoft Graph Search API: https://learn.microsoft.com/en-us/graph/search-concept-overview  
- Splunk Federated Search: https://docs.splunk.com/Documentation/Splunk/latest/Dispatch/FederatedSearch  
- Google Cloud Search: https://developers.google.com/cloud-search  
- Sigma: https://github.com/SigmaHQ/sigma  
- MITRE ATT&CK T1213.002 (Data from Information Repositories): https://attack.mitre.org/techniques/T1213/002/  

---

### 🏷️ Tags / Labels
`federated-search` `data-access` `elasticsearch` `m365-graph` `splunk` `gdrive` `query-abuse` `t1213.002` `quiet-access` `data-diodes`

---

### 📈 Effort Level
**Medium (M)** — requires federated infra and role testing across search layers.

---

### ✅ Acceptance Criteria
- [ ] Federated search setup with at least two connectors
- [ ] Queries crafted that overreach original access scope
- [ ] Confirmed data visibility without direct source system interaction
- [ ] Sample Sigma/detection logic provided
- [ ] Test harness and documentation captured in shared repo
