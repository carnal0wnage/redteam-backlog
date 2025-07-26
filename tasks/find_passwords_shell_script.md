# 🐚 Research Spike: Write a Shell Script to Find Passwords on Linux and macOS

**Goal:**  
Create a lightweight shell script that recursively scans user directories on Linux and macOS systems for files and strings likely to contain secrets (e.g., passwords, tokens, API keys, `.env`, `.pem`).

**Why It Matters:**  
Credential sprawl is common on developer workstations, staging environments, and shared systems. A simple script can rapidly surface low-hanging secrets that attackers or insider threats would exploit.

---

### 🔍 Scope
- Target: Local user directories (`/home/*`, `/Users/*`)
- Focus on non-system files: config files, dotfiles, leftover credentials
- No file modification or exfil — read-only scanning only

---

### ✅ Tasks
- [ ] Write a shell script that:
  - Recursively scans for keywords like `password`, `passwd`, `secret`, `token`
  - Looks for file extensions like: `.env`, `.pem`, `.p12`, `.json`, `.yml`
  - Ignores binary files and system directories
- [ ] Add exclusions for:
  - `/proc`, `/dev`, system logs
  - Files over a certain size (e.g., 10MB)
- [ ] Output results into a log file with:
  - File path
  - Line of match (for context)
- [ ] Test script on a dev box or VM
- [ ] Optional: add flags for:
  - Output format (plain/log)
  - File extension filtering

---

### 🎯 Deliverables
- Final shell script with:
  - Usage instructions
  - Safe output directory
- Log file showing real matches (sanitized if needed)
- Recommendations:
  - Secrets handling policy
  - Move credentials to vaults (e.g., HashiCorp Vault, AWS Secrets Manager)

---

### 📚 Reference Materials
- `grep`, `find`, `awk`, `sed` basics: https://explainshell.com/  
- GitHub search best practices: https://docs.github.com/en/code-security  
- Dotfile discovery examples: https://github.com/projectdiscovery/dotfiles  
- Shell scripting for red teams: https://book.hacktricks.xyz/

---

### 🏷️ Tags / Labels
`junior-friendly` `osx` `linux` `passwords` `secrets` `bash` `dotfiles`

---

### 📈 Effort Level
**Small (S)** — great practice in scripting and real-world secrets hunting.

---

### ✅ Acceptance Criteria
- [ ] Script created and runs successfully on both Linux and macOS
- [ ] Output includes at least 5 matches from sample files
- [ ] Output is safe and readable (no creds exfil or tampering)
- [ ] Shared internally with usage guidance
