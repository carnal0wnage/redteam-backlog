# 🍎 Research Spike: Top 10 Initial Access Vectors for macOS

**Goal:**  
Research, replicate, and document the most common initial access techniques targeting macOS endpoints. Simulate these techniques in a lab to understand how attackers gain their first foothold — and what defenses respond (or fail to).

**Why It Matters:**  
macOS usage in enterprises is growing, but it’s often less protected than Windows. Red teamers need hands-on experience understanding how attackers exploit trust, user behavior, and built-in macOS features to gain access.

---

### 🔍 Scope
- macOS Ventura/Sonoma or later (test VM or physical machine)
- Delivery via email, web, USB, AirDrop, or shared network
- Non-destructive payloads (harmless scripts or callbacks)

---

### ✅ Tasks
- [ ] Research and simulate the following **Top 10 Initial Access Vectors for macOS**:

  1. **Malicious Office Macros (Word/Excel)**  
     - Macros still work on macOS Office with prompting  
     - Use test doc with harmless script (e.g., `osascript`)
  
  2. **Malicious `.app` Bundle**  
     - Custom `.app` with disguised payload (e.g., AppleScript)  
     - Delivered via DMG, ZIP, or web download

  3. **Internet-Downloaded Script with Quarantine Bypass**  
     - Use curl/wget to drop file and manually remove quarantine attribute:  
       `xattr -d com.apple.quarantine file.sh`

  4. **Malicious Shortcut or Script via AirDrop / USB**  
     - Delivered as .sh, .command, or even PDF+script payloads  
     - Use Rubber Ducky or OMG cable for auto-exec on insertion

  5. **Default Credential Reuse (e.g., SSH, MDM, Homebrew)**  
     - Attempt access via reused creds, SSH keys, or misconfigured MDM systems

  6. **Abuse of TCC Permissions (Automation/Accessibility)**  
     - Drop or execute payload that tries to access screen, mic, or input  
     - Observe System Preferences prompt and how AV/EDR responds

  7. **LaunchAgent / LaunchDaemon Implantation**  
     - Write a plist file to `~/Library/LaunchAgents/` for persistence and auto-execution

  8. **PDF or OneNote Social Engineering (prompt-based)**  
     - Embed script or link in trusted format (safe test only)

  9. **Drive-By Download from Safari/Chrome**  
     - Host fake update `.dmg` or `.pkg` — log user interaction, Gatekeeper behavior

  10. **Remote AppleScript Execution (osascript + SSH)**  
      - Use `osascript` or `osascript -e` with a valid user context over SSH  
      - Optional: simulate MDM abuse or Apple Remote Desktop

- [ ] Log whether the attack:
  - Required user interaction
  - Triggered Gatekeeper, AV, or system warnings
  - Resulted in file execution, persistence, or network callout

- [ ] Create a summary table:
  - Vector, delivery method, payload type, detection/mitigation triggered
- [ ] Write internal “Top 10 macOS Initial Access Vectors” guide
- [ ] Note which attacks work with standard user privileges vs admin

---

### 🎯 Deliverables
- Internal wiki/markdown page with:
  - Table of each vector, execution success, and screenshots
  - Screenshots of Gatekeeper prompts, AV blocks, user prompts
  - Recommended detection or hardening settings (e.g., restrict LaunchAgents, disable unsigned apps)
  - Optional: shell scripts or `.app` payload templates (benign)

---

### 📚 Reference Materials
- Mac Security Blog: https://objective-see.com/blog.html  
- MITRE ATT&CK for macOS: https://attack.mitre.org/matrices/enterprise/macos/  
- TCC Bypass Explainer: https://theevilbit.github.io/posts/exploring_tcc/  
- AppleScript Basics: https://developer.apple.com/library/archive/documentation/AppleScript/Conceptual/AppleScriptLangGuide  
- TryHackMe / HackTheBox macOS labs (if available)  
- `spctl`, `codesign`, and `xattr` command man pages

---

### 🏷️ Tags / Labels
`junior-friendly` `macos` `initial-access` `payloads` `applescript` `usb` `gatekeeper`

---

### 📈 Effort Level
**Medium (M)** — requires lab setup and understanding of macOS-specific quirks (TCC, Gatekeeper, file quarantine).

---

### ✅ Acceptance Criteria
- [ ] All 10 vectors researched and at least 5 tested in lab
- [ ] For each vector, log execution result, user interaction needed, and detections (if any)
- [ ] “Top 10 macOS Initial Access” summary table created
- [ ] Internal writeup or wiki page shared with team
- [ ] Notes on hardening settings and recommended controls provided