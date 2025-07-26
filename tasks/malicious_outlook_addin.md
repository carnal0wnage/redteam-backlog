# 📩 Research Spike: Create a Malicious Outlook Add-in

**Goal:**  
Use a Visual Studio Tools for Office (VSTO) project to create a malicious Outlook add-in that runs arbitrary code on application launch.

**Why It Matters:**  
Office Add-ins are often overlooked by EDR solutions and allow for persistent execution within trusted apps like Outlook. This technique is suitable for phishing-based payload delivery, internal lateral movement, or initial persistence.

---

### 🔍 Scope
- Office 365 or Microsoft Outlook Desktop
- Windows environment with Visual Studio
- Local user write access (AppData)

---

### ✅ Tasks
- [ ] Create a VSTO project in Visual Studio targeting Outlook
- [ ] Write a payload trigger on `ThisAddIn_Startup`
  - Simple command execution or beacon callout
- [ ] Sign the add-in with a test certificate (optional)
- [ ] Package for installation via `.vsto` and manifest file
- [ ] Install and validate execution on launch of Outlook
- [ ] Optional: Test add-in delivery via phishing or internal software share

---

### 🎯 Deliverables
- Visual Studio project files
- Build artifacts: `.vsto`, `.dll`, manifest
- Execution logs/screenshots
- Optional: Defender/EDR bypass observations
- Documentation on install paths and persistence vectors

---

### 📚 Reference Materials
- Microsoft VSTO documentation: https://learn.microsoft.com/en-us/visualstudio/vsto  
- Outlook Add-in security guide: https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish  
- MITRE ATT&CK:  
  - T1137.006 – Office Application Startup (Outlook)

---

### 🏷️ Tags / Labels
`office-persistence` `outlook` `vsto` `t1137.006` `junior-plus`

---

### 📈 Effort Level
**Medium (M)** — requires Visual Studio experience and Office configuration.

---

### ✅ Acceptance Criteria
- [ ] Add-in executes arbitrary code on Outlook launch
- [ ] Setup and installation paths documented
- [ ] At least one detection or bypass attempt documented
