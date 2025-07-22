# 🗂️ Research Spike: Enumerate Internal NetBIOS & SMB Shares

**Goal:**  
Identify internal systems that expose SMB shares or NetBIOS name service information that could aid in lateral movement, credential harvesting, or unauthorized file access.

**Why It Matters:**  
Legacy protocols like SMBv1 and NetBIOS still exist in many enterprise environments and are often overlooked. Exposed file shares can contain sensitive data, config files, credentials, or scripts that attackers can leverage to escalate access or pivot deeper into a network.

---

### 🔍 Scope
- Internal IPv4 network ranges accessible to the red team lab or engagement system
- Windows systems, NAS devices, or Linux boxes with SMB services
- NetBIOS name resolution and SMB enumeration via ports 137, 139, and 445

---

### ✅ Tasks
- [ ] Identify live hosts using ping sweep or Nmap scan (e.g., `nmap -p 139,445 -sV 10.0.0.0/24`)
- [ ] Run NetBIOS and SMB enumeration tools:
  - `enum4linux-ng` (recommended)
  - `smbclient -L //IP/` (unauthenticated and authenticated)
  - `nmap --script smb-enum-shares,smb-enum-users -p 445`
  - `crackmapexec smb` for fast enumeration
- [ ] Capture:
  - Hostname, domain/workgroup info
  - Shared folder names and permissions
  - Whether anonymous access is allowed
  - SMB version support (especially SMBv1)
- [ ] Attempt to connect to shares:
  - Browse contents
  - Search for interesting files (e.g., `.ps1`, `.txt`, `.xlsx`, `passwords.csv`)
- [ ] Log any files found that contain creds, keys, tokens, scripts, or sensitive documents
- [ ] Map any trust relationships or identity leaks (e.g., who last accessed the share)

---

### 🎯 Deliverables
- Internal wiki entry or short report containing:
  - List of identified SMB servers and shares
  - Access level (guest, read-only, write, anonymous)
  - Screenshots of enum or dump results
  - List of interesting or risky files (with sanitized examples)
  - Recommendations for hardening or segmentation (e.g., remove guest access, disable SMBv1)

---

### 📚 Reference Materials
- enum4linux-ng: https://github.com/cddmp/enum4linux-ng  
- CrackMapExec: https://github.com/Porchetta-Industries/CrackMapExec  
- TryHackMe “SMB” module: https://tryhackme.com/room/smb  
- SANS Pentest Poster (SMB section): https://www.sans.org/posters/purple-team-tactics/  
- SMB hardening: https://learn.microsoft.com/en-us/windows-server/storage/file-server/troubleshoot/detect-disable-smbv1

---

### 🏷️ Tags / Labels
`junior-friendly` `smb` `netbios` `recon` `lateral-movement` `internal-enum` `windows`

---

### 📈 Effort Level
**Small (S)** — tooling is straightforward and results are often high signal.

---

### ✅ Acceptance Criteria
- [ ] Minimum 3 systems tested for SMB/NetBIOS exposure
- [ ] At least one share enumerated (anonymous or with creds)
- [ ] Potential lateral movement or data access scenario documented
- [ ] Screenshots or output logs included in writeup
- [ ] Recommendations made (e.g., guest access removal, share minimization)
- [ ] Shared report or internal wiki updated for future use