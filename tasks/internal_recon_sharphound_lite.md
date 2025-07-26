# 🧠 Research Spike: Create an Internal Recon Script with SharpHound-lite Features

**Goal:**  
Develop a lightweight internal recon script that gathers basic domain and user context without triggering alerts typically associated with full SharpHound enumeration. This tool should be usable early post-access for safe situational awareness.

**Why It Matters:**  
Aggressive recon tooling like SharpHound can set off blue team alerts. A minimal recon script allows red teamers to understand their environment and begin pivoting while remaining under the radar. It also teaches key concepts around stealth and operational security (OPSEC).

---

### 🔍 Scope
- Windows domain-joined host with standard user access
- No elevated privileges required
- Minimal/no use of native binaries or noisy tooling
- Output to local file, clipboard, or memory only

---

### ✅ Tasks
- [ ] Identify low-noise recon targets:
  - Current domain, user, and hostname
  - Group membership for current user
  - List of domain admins (via LDAP or PowerShell)
  - Computer accounts within same OU
  - Open SMB shares within local subnet
- [ ] Write script in PowerShell or C#:
  - Use native .NET or `System.DirectoryServices` for LDAP queries
  - Avoid tools like `net`, `whoami /groups`, `nltest`, or `SharpHound`
- [ ] Add OPSEC considerations:
  - Random sleep/timers between queries
  - Limit number of objects returned
  - Allow target scoping via command-line args
- [ ] Output results to:
  - Local CSV or JSON
  - Clipboard (optional)
  - Memory-only with on-screen summary

---

### 🎯 Deliverables
- Lightweight PowerShell/C# recon script
- README with:
  - Intended use and limitations
  - OPSEC-safe usage examples
- Sample output in structured format
- Optional:
  - Integration into larger post-ex tooling
  - Detection comparison vs. SharpHound or BloodHound

---

### 📚 Reference Materials
- System.DirectoryServices namespace: https://learn.microsoft.com/en-us/dotnet/api/system.directoryservices  
- PowerView (legacy): https://github.com/PowerShellMafia/PowerSploit  
- SharpHound Data Collection: https://github.com/BloodHoundAD/SharpHound  
- SpecterOps OPSEC Advice: https://posts.specterops.io/  
- MITRE ATT&CK:  
  - T1087 – Account Discovery  
  - T1018 – Remote System Discovery

---

### 🏷️ Tags / Labels
`internal-recon` `powershell` `ldap` `bloodhound-lite` `junior-friendly` `t1087` `t1018`

---

### 📈 Effort Level
**Medium (M)** — requires LDAP familiarity and scripting, but no privileged access.

---

### ✅ Acceptance Criteria
- [ ] Script runs as standard domain user and collects at least 3 data types
- [ ] Output is human-readable and/or machine-readable (JSON/CSV)
- [ ] Script avoids high-alert system binaries and sharp signatures
- [ ] Deliverables include documentation and example usage
