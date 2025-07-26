# 🍎 Research Spike: Create a Local Privilege Escalation Checklist Script for macOS

**Goal:**  
Develop a script that checks for common local privilege escalation (LPE) opportunities on macOS (e.g., world-writable files, misconfigured sudoers, vulnerable LaunchAgents).

**Why It Matters:**  
macOS systems often receive less scrutiny than Windows in enterprise environments. A lightweight local LPE script helps red teamers identify privilege abuse vectors quickly and consistently.

---

### 🔍 Scope
- macOS 12–14 (Intel and Apple Silicon)
- Local user context
- Focus on:
  - World-writable binaries in `$PATH`
  - Sudoers file misconfigs
  - Insecure LaunchAgents/LaunchDaemons
  - Homebrew-related issues
  - Setuid/setgid binaries

---

### ✅ Tasks
- [ ] Write a script using `bash` or `zsh` that checks for:
  - [ ] Writable files in privileged directories
  - [ ] Weak `sudoers` file entries (`NOPASSWD`, `%admin`)
  - [ ] Custom LaunchAgents loading from user directories
  - [ ] Insecure permissions on Homebrew install path
  - [ ] Binary hijacks via environment variables (`DYLD_*`)
- [ ] Include output formatting (Markdown or CSV)
- [ ] Ensure script is read-only and non-destructive

---

### 🎯 Deliverables
- `macos-lpe-checklist.sh` script
- Example output with high/medium/low-risk findings
- Internal wiki post explaining how to use the tool

---

### 📚 Reference Materials
- https://github.com/scriptingosx  
- https://www.trendmicro.com/en_us/research/22/f/macos-privilege-escalation-vulnerabilities.html  
- https://objective-see.org/

---

### 🏷️ Tags / Labels
`macos` `privilege-escalation` `lpe` `post-exploitation` `automation`

---

### 📈 Effort Level
**Medium (M)**

---

### ✅ Acceptance Criteria
- [ ] Script runs cleanly on both Intel and M1/M2 Macs
- [ ] At least 5 LPE checks implemented
- [ ] Output supports team documentation format
- [ ] Shared internally via repo or wiki
