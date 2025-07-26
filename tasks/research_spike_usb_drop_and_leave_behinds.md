#  💾 Research Spike: USB Drop Research (Payloads, Lure Docs, & OMG Cable Attacks)

**Goal:**  
Design, execute, and measure the effectiveness of USB drop attacks using various payload types — from benign lure documents to malicious `.lnk` files, HID injection (Rubber Ducky), and OMG cables. Evaluate the psychological angle (pretext) and technical payload success across environments.

**Why It Matters:**  
USB drops are a classic but effective method for initial access in physical security assessments and red team exercises. This research helps red teamers test assumptions around user behavior, endpoint defenses, and attack delivery options — blending technical payloads with social pretexting.

---

### 🔍 Scope
- Internal office environments (with approval) or controlled lab setting
- USB-based payloads or social engineering lures
- No malware or destructive payloads — use benign scripts, callbacks, or harmless logging
- Target devices: Windows, macOS, Linux endpoints

---

### ✅ Tasks
- [ ] Prepare multiple USB attack types:
  - [ ] **Lure Document:** e.g., “Executive Bonus Plan Q3.docx” with tracking pixel or macro prompt
  - [ ] **Shortcut Payload (.lnk):** disguised file that runs `powershell` or similar
  - [ ] **Rubber Ducky / HID Injection:** pre-programmed keystrokes that open terminal and run a callback command
  - [ ] **OMG Cable:** use Hak5 OMG Programmer to flash and test payloads (e.g., open reverse shell, grab hostname, exfil Wi-Fi creds)
- [ ] Design social pretexts:
  - “Lost badge drive”
  - “HR applicant resume”
  - “Company party photos”
- [ ] Drop in varied, controlled environments:
  - Internal office drop (if scoped)
  - Parking lot, lobby, break room
  - Lab setup with fake workstation
- [ ] Track pickup behavior and telemetry:
  - File access via callback URL or webhook
  - Payload execution via staged script logs
  - USB insertion detection using endpoint logs or EDR (if available)
- [ ] Observe what kinds of drives get picked up and what gets executed
- [ ] Evaluate endpoint protections (AV pop-ups, EDR block, macro warnings, autorun behavior)

---

### 🎯 Deliverables
- Internal report or wiki page with:
  - Drop types and pretexts tested
  - Environment and user behavior observations
  - Screenshots of payload execution or triggered callbacks
  - Recommendations for user training, endpoint control, USB port policies
  - Example payloads (sanitized), scripts, and OMG cable programming files

---

### 📚 Reference Materials
- Hak5 USB Rubber Ducky: https://shop.hak5.org/products/usb-rubber-ducky  
- OMG Cable Programmer: https://github.com/O.MG/O.MG-Cable-Firmware  
- Hak5 Payloads Repo: https://github.com/hak5darren/USB-Rubber-Ducky/wiki/Payloads  
- PowerShell Callback Examples: https://github.com/samratashok/nishang  
- Lure file tricks: https://book.hacktricks.xyz/pentesting/pentesting-file-inclusion  
- Mitre T1200 (Hardware Additions): https://attack.mitre.org/techniques/T1200/

---

### 🏷️ Tags / Labels
`junior-friendly` `physical-access` `usb-attack` `social-engineering` `omg-cable` `rubber-ducky` `pretexting`

---

### 📈 Effort Level
**Medium (M)** — requires hardware setup, scripting, and social analysis.

---

### ✅ Acceptance Criteria
- [ ] At least 3 USB attack types tested (lure doc, shortcut, HID or OMG)
- [ ] 2–3 social pretexts crafted and used
- [ ] Drop attempts logged with pickup behavior or telemetry (even if no execution)
- [ ] Screenshots or logs showing successful execution or user interaction
- [ ] Recommendations written for blue team + awareness training
- [ ] Internal documentation created for future USB drop simulations
## 🪟 Research Spike: Top 10 Initial Access Vectors for Windows

**Goal:**  
Identify, replicate, and document the top 10 initial access techniques commonly used to compromise Windows systems in enterprise environments. For each vector, simulate or test the method in a lab environment, log what works, and build a repeatable checklist or playbook.

**Why It Matters:**  
Initial access is the first step in nearly every red team operation, ransomware attack, or APT campaign. Mastering these techniques gives junior red teamers critical awareness of how attackers get in — and what defenders should monitor or block.

---

### 🔍 Scope
- Windows 10/11 or Server systems (lab preferred)
- Non-destructive payloads only (harmless shells, callbacks, or test binaries)
- Delivery methods: email, USB, web, file shares, exposed services

---

### ✅ Tasks
- [ ] Research and test the following **Top 10 Initial Access Vectors for Windows**:

  1. **Phishing with Malicious Attachment**  
     - Lure: Word doc with macro or remote template  
     - Tool: `evilginx`, `MacroPack`, `InvisiShell`  
  2. **Malicious Shortcut File (.lnk)**  
     - Delivered via USB drop, phishing, or shared drive  
     - Payload runs PowerShell or connects to external domain  
  3. **USB HID Injection (Rubber Ducky / OMG Cable)**  
     - Device emulates keyboard and executes payload instantly  
  4. **Shared Network Drives (File Drop & Exec)**  
     - Exposed SMB share or misconfigured GPO script  
  5. **Exposed RDP with Weak or Default Credentials**  
     - Brute force or use leaked creds  
  6. **HTA Files (via HTML/Email Drop)**  
     - Embedded VBScript to execute remote code  
  7. **Living off Signed Binaries (LOLBins)**  
     - Use `mshta.exe`, `regsvr32.exe`, or `rundll32.exe` for payload execution  
  8. **Remote Code Execution via Vulnerable Service**  
     - Example: EternalBlue (MS17-010), PrintNightmare (CVE-2021-34527)  
  9. **Infected Installers or Update Binaries**  
     - Fake software or poisoned `.msi`/`.exe` installers  
  10. **Trusted Document Format Abuse (PDF, OneNote)**  
      - Payloads embedded in PDFs, OneNote files, or ISO containers

- [ ] Log results for each vector:
  - Was the payload blocked or triggered?
  - Any endpoint alerts?
  - What telemetry was generated (if monitored)?
- [ ] Note which vectors require interaction (e.g., clicking "Enable Macros") vs. auto-execute
- [ ] Build a summary table with:
  - Access method
  - Execution type (user-driven, auto)
  - Mitigation or detection strategy
- [ ] Build a “Top 10 Initial Access Checklist” for internal use

---

### 🎯 Deliverables
- Table of all 10 vectors tested, with:
  - Success/fail status
  - Screenshots or payload results
  - Relevant telemetry or detection output
- Written notes on ease of execution and mitigation tips
- Internal markdown/wiki page with:
  - Top 10 Initial Access Vector cheat sheet
  - Tooling used
  - Lab setup tips
- Optional: Record short videos of each vector for internal training

---

### 📚 Reference Materials
- MITRE ATT&CK – Initial Access: https://attack.mitre.org/tactics/TA0001/  
- HackTricks Initial Access: https://book.hacktricks.xyz/pentesting/persistence  
- Red Canary Threat Detection Report: https://redcanary.com/threat-detection-report/  
- LOLBAS Project: https://lolbas-project.github.io/  
- TryHackMe “Initial Access” room: https://tryhackme.com/room/attackpaths  
- Phishing Simulation Tools: `GoPhish`, `evilginx2`, `BadSender`

---

### 🏷️ Tags / Labels
`junior-friendly` `initial-access` `windows` `payloads` `phishing` `lolbins` `usb-attacks`

---

### 📈 Effort Level
**Medium (M)** — requires lab setup and responsible payload handling, but high educational value.

---

### ✅ Acceptance Criteria
- [ ] All 10 vectors tested or simulated in a safe environment
- [ ] Screenshots or output captured for each
- [ ] Mitigation and detection notes written for each vector
- [ ] “Top 10 Initial Access” table created and shared
- [ ] Tools, scripts, and resources documented for future reuse