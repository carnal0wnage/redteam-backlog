
# 🧪 Research Spike: Test Alternate Windows Binary Formats for Payload Delivery

**Goal:**  
Explore lesser-used executable formats such as `.NET Core`, `.WSF`, `.HTA`, `.JSE`, and `.VBS` for use in red team payload delivery. Evaluate effectiveness, detection rates, and compatibility with email delivery and execution paths.  

**Why It Matters:**  
Most EDRs and security teams focus heavily on `.exe` and `.dll` binaries. Alternate scripting formats and container types are often overlooked, making them viable vectors for social engineering, phishing, and initial access. None of these should realistically be delivered via phishing but you gotta make sure.

---

### 🔍 Scope
- Focus formats:
  - Windows Script Host (WSH): `.WSF`, `.HTA`, `.JSE`, `.VBS`
  - .NET Core apps (self-contained and portable)
  - Office script-compatible formats
- Delivery mechanisms:
  - Email with attachments or download links
  - USB drops
  - Internal chat/file transfer platforms
- Target environments:
  - Windows 10/11 with Defender enabled
  - Outlook and internal mail gateways

---

### ✅ Tasks
- [ ] Create PoC payloads in:
  - [ ] `.WSF` and `.HTA` (with embedded VBScript or JavaScript)
  - [ ] `.NET Core` console app with embedded C2 stager
  - [ ] `.JSE` and `.VBS` with basic downloader logic
- [ ] Test payloads:
  - Execute on lab systems (Defender + EDR)
  - Analyze endpoint telemetry
- [ ] Package for delivery:
  - [ ] Email as attachments
  - [ ] Encapsulated in `.zip` or `.docx`
  - [ ] External download links with redirect
- [ ] Track detection signals:
  - Email gateway alerts (EOP, ATP, etc.)
  - Host-based blocking (AMSI, EDR)
  - Behavioral alerts in SIEM
- [ ] Evaluate user interaction required (e.g., double-click, macros, trust prompts)

---

### 🎯 Deliverables
- Internal matrix of:
  - Format
  - Delivery vector
  - Execution success
  - Detection results
- Sample payload templates for reuse
- Red + blue team documentation:
  - Tradeoffs of each format
  - Detection signatures
  - Suggested mitigations

---

### 📚 Reference Materials
- MITRE ATT&CK:
  - T1204.002 – Malicious File
  - T1059 – Command and Scripting Interpreter
  - T1055 – Process Injection
- SANS Windows Script Host Guide
- Outlook Safe File Types: https://learn.microsoft.com/en-us/outlook/troubleshoot/security/blocked-attachments-in-outlook

---

### 🏷️ Tags / Labels
`senior` `payload-delivery` `hta` `netcore` `wsf` `email-phishing` `t1204`

---

### 📈 Effort Level
**Medium (M)** — requires scripting knowledge and email testing environment.

---

### ✅ Acceptance Criteria
- [ ] Minimum 3 formats tested with payloads
- [ ] Each tested in at least 2 delivery scenarios
- [ ] Matrix of execution and detection outcomes created
- [ ] Red + blue team documentation finalized and shared
