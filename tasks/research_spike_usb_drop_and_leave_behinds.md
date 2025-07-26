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
