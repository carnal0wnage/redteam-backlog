# 🎣 Research Spike: Create Weaponized Office Macro Phish Payloads

**Goal:**  
Design and generate Office macro payloads for phishing engagements. Focus on creating obfuscated, weaponized VBA (or other equivalent language) macros capable of delivering payloads or establishing callbacks, while bypassing common AV and EDR detection.

**Why It Matters:**  
Office macros remain a popular and successful initial access vector in real-world attacks. By building and testing these payloads internally, red teams can better simulate phishing threats and help organizations improve their detection and response capabilities.

---

### 🔍 Scope
- Internal phishing lab or authorized phishing tests
- Word and Excel macros (.docm, .xlsm files)
- Windows targets with macro execution enabled
- Payload types: reverse shell, beacon callbacks, staged droppers

---

### ✅ Tasks
- [ ] Review macro execution policies in the target environment
- [ ] Choose a payload type (e.g., PowerShell stager, EXE downloader, COM object abuse)
- [ ] Write basic VBA macro loader code
- [ ] Integrate payload into macro and obfuscate using tools like:
  - `VBA Obfuscator`
  - `macro_pack`
- [ ] Test payload execution in isolated VM with logging enabled
- [ ] Validate against common AV/EDR solutions (e.g., Defender, CrowdStrike)
- [ ] Document execution flow and detection evasion notes
- [ ] Optionally map payloads to MITRE ATT&CK techniques:
  - T1204.002 - User Execution: Malicious File
  - T1059.001 - Command and Scripting Interpreter: PowerShell
  - T1566.001 - Phishing: Spearphishing Attachment

---

### 🎯 Deliverables
- Obfuscated macro payload PoC (for internal red team use only)
- Execution test results: screenshots, AV bypass results, detection notes
- Internal wiki page or markdown with:
  - Macro code sample
  - Obfuscation method
  - Payload description and impact
  - Detection considerations and logging guidance
- Optional: Template phishing document with lure content

---

### 📚 Reference Materials
- macro_pack: https://github.com/sevagas/macro_pack  
- VBA Obfuscation Tools: https://github.com/paranoidninja/VBA-Obfuscator  
- MITRE ATT&CK - Phishing: https://attack.mitre.org/techniques/T1566/  
- Red Canary Threat Detection Report: https://redcanary.com/threat-detection-report/

---

### 🏷️ Tags / Labels
`phishing` `office-macros` `malicious-docs` `payload-dev` `t1204.002` `t1059.001`

---

### 📈 Effort Level
**Medium (M)** — Requires scripting, macro handling, obfuscation tools, and malware testing environment.

---

### ✅ Acceptance Criteria
- [ ] Macro executes payload successfully in lab environment
- [ ] Payload evades detection by at least 1 AV/EDR
- [ ] Report or wiki includes annotated macro code and obfuscation technique
- [ ] Lure document packaged and ready for phishing simulation
