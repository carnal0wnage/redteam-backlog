# ☁️ Research Spike: AWS Privilege Escalation Analysis with pmapper

**Goal:**  
Use `pmapper` (or similar tools) to analyze AWS IAM roles and policies for privilege escalation paths. Identify misconfigurations that would allow a user to escalate to Admin or gain unintended access through permission chaining.

**Why It Matters:**  
IAM misconfigurations are one of the most common causes of lateral movement and privilege escalation in cloud environments. Many red teams miss them because the paths aren’t obvious — `pmapper` helps visualize and surface these dangerous chains for remediation.

---

### 🔍 Scope
- AWS development, staging, or security sandbox account(s)
- IAM users, groups, and roles
- No destructive actions — read-only data collection and analysis only
- Primary focus: IAM privilege escalation paths (not S3, EC2, etc.)

---

### ✅ Tasks
- [ ] Set up an AWS IAM user with **`iam:List*`, `iam:Get*`** permissions (or use read-only role)
- [ ] Install and configure `pmapper`:
  - https://github.com/nccgroup/PMapper
- [ ] Enumerate all users, roles, groups, and policies:
  - `pmapper import --profile <aws-profile>`
  - `pmapper graph`
- [ ] Run privilege escalation analysis:
  - `pmapper query --all-paths --priv-esc`
- [ ] Identify common escalation paths such as:
  - `iam:PassRole` to a more privileged role
  - `lambda:UpdateFunctionCode` to inject code into a high-priv function
  - `ec2:RunInstances` with attached privileged instance profiles
  - `ssm:SendCommand` to run commands as another role
- [ ] Cross-reference findings with:
  - CloudSplaining (optional)
  - AWS IAM documentation
  - MITRE ATT&CK for Cloud (T1078.004, T1098.004)

---

### 🎯 Deliverables
- Internal markdown or wiki page with:
  - Summary of pmapper output and graph
  - Top 3–5 privilege escalation paths with:
    - User/role involved
    - Path type (e.g., PassRole, UpdateLambda)
    - Potential impact
  - Screenshots of graphs or path output
  - Recommended remediations (least privilege, deny actions, separation of roles)
- Optional:
  - Annotated JSON graph export
  - CloudSplaining or `PrincipalMapper` comparison if time allows

---

### 📚 Reference Materials
- pmapper GitHub: https://github.com/nccgroup/PMapper  
- NCC Group blog on IAM Escalation: https://research.nccgroup.com/  
- AWS IAM Best Practices: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html  
- MITRE ATT&CK – Cloud: https://attack.mitre.org/tactics/TA0004/  
- CloudSplaining: https://github.com/salesforce/cloudsplaining  
- Rhino Security IAM Escalation Cheatsheet: https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods/

---

### 🏷️ Tags / Labels
`junior-friendly` `aws` `iam` `privilege-escalation` `pmapper` `cloud-security` `t1078.004`

---

### 📈 Effort Level
**Medium (M)** — minimal AWS risk, but interpreting results requires careful thinking.

---

### ✅ Acceptance Criteria
- [ ] `pmapper` installed and run on at least one AWS account
- [ ] Graph generated and escalation paths identified
- [ ] At least 2 realistic privilege escalation scenarios documented
- [ ] Recommendations created to close risky paths
- [ ] Report or wiki page shared internally with screenshots and remediation notes
