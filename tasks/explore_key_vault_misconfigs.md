# 🛡️ Research Spike: Explore Azure Key Vault or AWS Secrets Manager Misconfigurations

**Goal:**  
Enumerate misconfigurations in cloud secrets managers, such as overly permissive access policies, missing audit logging, or insecure retrieval patterns. Identify opportunities for unauthorized access or privilege escalation.

**Why It Matters:**  
Secrets managers are designed to protect credentials, keys, and tokens — but improper configurations can expose sensitive data. These services are often overlooked during cloud assessments, creating stealthy persistence and exfil paths.

---

### 🔍 Scope
- AWS Secrets Manager, Parameter Store
- Azure Key Vault
- IAM roles, policies, and key access audit logs

---

### ✅ Tasks
- [ ] Enumerate secrets and associated access policies:
  - AWS: `list-secrets`, `get-resource-policy`, `describe-secret`
  - Azure: `az keyvault list`, `az keyvault show --name <vault>`
- [ ] Check for excessive permissions:
  - Wildcard `*` actions
  - Broad `Resource` scopes
  - Access by non-human identities (CI/CD, third-party tools)
- [ ] Validate audit logging:
  - AWS: CloudTrail enabled for Secrets Manager?
  - Azure: Diagnostic settings / Key Vault logging
- [ ] Optional:
  - Enumerate who can retrieve secrets without MFA
  - Scan for secrets injected into containers or Lambda ENV
  - Attempt red-team style retrieval (with low-priv credentials)

---

### 🎯 Deliverables
- Report of secrets access policies and risk level
- Table of over-permissioned identities
- Audit status of logging + alerting
- Recommended remediations:
  - Least-privilege roles
  - Scoped resource access
  - Monitoring on read operations
  - Vault access via short-lived credentials or OIDC

---

### 📚 Reference Materials
- AWS Secrets Manager: https://docs.aws.amazon.com/secretsmanager/  
- Azure Key Vault: https://learn.microsoft.com/en-us/azure/key-vault/general/  
- MITRE T1552.004 (Cloud-based Secrets): https://attack.mitre.org/techniques/T1552/004/  
- Cloudsplaining IAM analysis: https://github.com/salesforce/cloudsplaining  
- Azure Key Vault permissions: https://learn.microsoft.com/en-us/azure/key-vault/general/secure-your-key-vault

---

### 🏷️ Tags / Labels
`cloud-security` `aws` `azure` `secrets-manager` `key-vault` `iam` `t1552.004`

---

### 📈 Effort Level
**Medium (M)** — requires access to secrets manager API and familiarity with IAM or RBAC configurations.

---

### ✅ Acceptance Criteria
- [ ] Secrets enumerated in one cloud environment (AWS or Azure)
- [ ] At least 3 examples of over-permissioned or risky access documented
- [ ] Logging and alerting status reviewed and summarized
- [ ] Report or wiki entry created with recommendations
