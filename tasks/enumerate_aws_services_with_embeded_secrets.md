# 🔐 Research Spike: Enumerate AWS Services with Embedded Secrets

**Goal:**  
Identify AWS IAM users or services that have secrets (e.g., API keys, credentials, tokens) embedded in their inline policies, EC2 descriptions text, or exposed through environment variables in Lambda functions.

**Why It Matters:**  
Inline policies and Lambda ENV variables are often overlooked as sources of sensitive information. Attackers can use these secrets to gain unauthorized access, pivot within the cloud environment, or escalate privileges.

---

### 🔍 Scope
- AWS IAM users and their inline policies
- AWS Lambda functions and their environment variables
- Developer and legacy roles where secret sprawl is more likely

---

### ✅ Tasks
- [ ] Use AWS CLI or SDK to enumerate IAM users with inline policies:
  - `aws iam list-users`
  - `aws iam list-user-policies`
  - `aws iam get-user-policy --user-name <user>`
- [ ] Grep or parse inline policy documents for:
  - AWS secret keys
  - External tokens
  - Suspicious strings (e.g., `password`, `key`, `token`)
- [ ] Enumerate Lambda functions:
  - `aws lambda list-functions`
  - `aws lambda get-function-configuration --function-name <name>`
- [ ] Inspect `Environment -> Variables` for embedded secrets
- [ ] Optional:
  - Use tools like `Cloudsplaining` to highlight IAM issues
  - Cross-reference with Secrets Manager / Parameter Store usage

---

### 🎯 Deliverables
- Report or wiki entry listing:
  - IAM users with inline policies containing secrets
  - Lambda functions with exposed ENV variables
- Screenshots or sample payloads redacted for safety
- Suggested remediations:
  - Move secrets to AWS Secrets Manager or Parameter Store
  - Use least-privilege roles and managed policies
  - Implement secret scanning and alerting pipelines

---

### 📚 Reference Materials
- AWS IAM documentation: https://docs.aws.amazon.com/IAM/latest/UserGuide/  
- AWS Lambda env variables: https://docs.aws.amazon.com/lambda/latest/dg/configuration-envvars.html  
- Cloudsplaining: https://github.com/salesforce/cloudsplaining  
- AWS Security Blog: https://aws.amazon.com/blogs/security/  
- Detect secrets in policies: https://github.com/awslabs/policy-sentry  

---

### 🏷️ Tags / Labels
`aws` `iam` `secrets` `lambda` `cloud-security` `t1552.001`

---

### 📈 Effort Level
**Medium (M)** — requires access to AWS accounts, IAM familiarity, and policy/document parsing.

---

### ✅ Acceptance Criteria
- [ ] At least 10 IAM users and all Lambda functions reviewed
- [ ] Secrets identified in at least one inline policy or ENV block
- [ ] Report generated with redacted examples and mitigation guidance
