
# 🖥️ Research Spike: Audit Windows Developer Environments for Exploitable Features

**Goal:**  
Audit common Windows developer tools (Visual Studio, Chocolatey, NuGet, PowerShell modules, build scripts) for exploitable behaviors like unsigned script loading, plugin execution, or credential exposure.

**Why It Matters:**  
Developer tools often run with elevated privileges and trust network resources. Misconfigurations or overlooked features can create persistent access, lateral movement, or local privilege escalation opportunities.

---

### 🔍 Scope
- Windows 10/11 developer endpoints
- Visual Studio, Chocolatey, NuGet, PowerShell profiles
- Windows Terminal, Windows Subsystem for Linux (WSL), Git for Windows
- Focus on plugin systems, auto-load scripts, install scripts

---

### ✅ Tasks
- [ ] Survey installed developer tooling on Windows systems
- [ ] Identify persistence mechanisms:
  - [ ] PowerShell profiles
  - [ ] Visual Studio extensions
  - [ ] Startup script injection (Chocolatey/NuGet hooks)
- [ ] Attempt:
  - [ ] Path hijacks via developer PATH injection
  - [ ] Use of unsigned or auto-trusted extensions/scripts
  - [ ] Accessing stored credentials or tokens in scripts
- [ ] Validate logging or Defender alerts

---

### 🎯 Deliverables
- PoC of at least one local code execution from dev tool
- Table of dev tools, trust mechanisms, plugin support
- Recommendations for hardening and safe config baselines

---

### 📚 Reference Materials
- Visual Studio Extensibility Docs: https://learn.microsoft.com/en-us/visualstudio/extensibility  
- Chocolatey: https://chocolatey.org/  
- PowerShell Profiles: https://learn.microsoft.com/en-us/powershell/

---

### 🏷️ Tags / Labels
`windows` `developer-tools` `powershell` `chocolatey` `lpe` `post-exploitation`

---

### 📈 Effort Level
**Medium (M)**

---

### ✅ Acceptance Criteria
- [ ] At least 3 developer tools evaluated
- [ ] At least one exploitation PoC created
- [ ] Hardened config guidance published
