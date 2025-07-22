
# 🔐 Research Spike: Harvest Tokens from Common CLI Configs (AWS, GCP, Heroku, etc.)

**Goal:**  
Create a tool or script that parses local developer environments for cloud provider credentials, API tokens, and access keys commonly stored in CLI configuration files.

**Why It Matters:**  
Red teamers often gain access to developer machines where cloud credentials are sitting unprotected in dotfiles or local config folders. These tokens can lead to full cloud access with minimal noise.

---

### 🔍 Scope
- CLI config paths for:
  - AWS (`~/.aws/credentials`)
  - GCP (`~/.config/gcloud/`)
  - Heroku (`~/.netrc`)
  - Azure (`~/.azure`)
  - GitHub CLI (`~/.config/gh`)
- Include Windows + *nix platforms

---

### ✅ Tasks
- [ ] Write script (Python, bash, or Go) to:
  - [ ] Detect installed CLI tools
  - [ ] Parse credential files safely
  - [ ] Check for:
    - [ ] Expired or inactive credentials
    - [ ] Token scopes or permissions
  - [ ] Flag high-risk findings (e.g., AWS root keys)
- [ ] Output results as table or JSON
- [ ] Optional: attempt cloud account enumeration via token

---

### 🎯 Deliverables
- `token-harvest.sh` or `cli-token-audit.py`
- Internal report of exposed tokens from test machines
- Suggested mitigation: `vault`, MFA, token lifetimes

---

### 📚 Reference Materials
- https://hackingthe.cloud  
- https://github.com/RhinoSecurityLabs/Cloud-Security-Research  
- https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html  
- https://cloud.google.com/sdk/docs

---

### 🏷️ Tags / Labels
`token-harvesting` `aws` `gcp` `azure` `secrets` `devops`

---

### 📈 Effort Level
**Medium (M)**

---

### ✅ Acceptance Criteria
- [ ] Script runs on both Windows and macOS/Linux
- [ ] At least 3 cloud provider tokens detected
- [ ] Example output generated
- [ ] Internal usage guidance published
