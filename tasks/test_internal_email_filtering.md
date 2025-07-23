
## 📧 Research Spike: Test Internal Email Filtering Rules

**Goal:**  
Evaluate how internal email security filters handle different types of payloads and spoofing attempts. Test which file types, links, or sender tricks bypass existing defenses.

**Why It Matters:**  
Email remains a top threat vector. Knowing what content gets blocked or allowed inside your organization helps shape phishing simulations and secure internal communication policies. Display name spoofing and internal trust abuse often go undetected.

---

### 🔍 Scope
- Internal email delivery between corporate users (via Exchange, Google Workspace, etc.)
- Payload types:
  - `.zip`, `.docm`, `.xlsm`, `.lnk`, `.js`, `.url`
  - Links to known phishing/malware domains (controlled)
  - Base64-encoded or obfuscated payloads
- Spoofing:
  - Display name spoofing (e.g., “CEO <external@domain.com>”)
  - Internal domain spoofing without SPF/DKIM alignment
- Out-of-band detection tests (e.g., delay or sandboxing)

---

### ✅ Tasks
- [ ] Build test payloads using:
  - Encrypted and unencrypted zip files
  - Macro-enabled Office documents with benign macros
  - Links with shortened URLs or redirectors
- [ ] Test display name variations:
  - “IT Support” <random@external.com>
  - Spoofed internal user with mismatched address
  - Typosquatting domains (optional)
- [ ] Send from external controlled address to internal users:
  - Observe if email is delivered, quarantined, flagged, or sanitized
- [ ] Document:
  - Which payloads are blocked or delivered
  - Delay between send and delivery
  - Visual alerts (banner, warning text)
- [ ] Optional: Test how EDR/email security tools log or analyze attachments

---

### 🎯 Deliverables
- Matrix of email tests:
  - Payload type / spoof type
  - Delivered? Quarantined? Warned?
- Screenshots or headers of filtered vs allowed messages
- Summary of:
  - Filtering gaps
  - Risky payloads that were allowed
  - Recommended rule updates or detections
- Optional: Create reusable phishing payload pack for future testing

---

### 📚 Reference Materials
- Microsoft Safe Links & Attachments: https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security  
- Google Workspace Security Tools: https://support.google.com/a/answer/  
- Email Spoofing & Bypass Techniques: https://github.com/Raikia/EmailSpoofTest  
- MITRE ATT&CK T1566 – Phishing: https://attack.mitre.org/techniques/T1566/

---

### 🏷️ Tags / Labels
`junior-friendly` `email` `phishing` `t1566` `macro` `display-name-spoofing` `payload-testing`

---

### 📈 Effort Level
**Medium (M)** — requires safe infrastructure and planning to avoid real risk.

---

### ✅ Acceptance Criteria
- [ ] At least 5 different payloads tested
- [ ] At least 3 display name spoofing variants tested
- [ ] Delivery results recorded for each
- [ ] Matrix of outcomes and recommendations created
