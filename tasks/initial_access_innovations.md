
## 🧲 Research Spike: Initial Access Innovations

**Goal:**  
Explore and test non-traditional phishing techniques to gain initial access, including QR code phishing, SMS-based lures, and physical rogue elements like malicious QR stickers placed in office environments. Catalog working techniques and their detection visibility.

**Why It Matters:**  
Traditional phishing techniques are increasingly filtered or anticipated. Alternative access vectors like QR-based and physical-channel attacks bypass many controls — especially when they exploit user curiosity or BYOD gaps. Understanding these methods enhances simulation realism and helps defenders adjust training and detections.

---

### 🔍 Scope
- Office settings, hybrid/remote users, BYOD devices  
- Channels: QR codes, SMS, sticker campaigns, airdrop/share exploits  
- Payloads: credential harvesting, device fingerprinting, URL tracking  
- No delivery of real malware — simulations only

---

### ✅ Tasks
- [ ] Research:
  - QR phishing methods (email-to-QR, rogue stickers)
  - SMS phishing and fake number services (e.g., Twilio)
  - USB drop QR hybrids or NFC bait attacks
- [ ] Create PoC phishing templates using:
  - Malicious QR code leading to phishing page
  - SMS with shortened URLs (test domains)
  - Office sticker + QR + "Employee Portal Update" signage
- [ ] Track:
  - User interaction (scans, clicks)
  - Platform behavior (iOS vs Android)
  - MFA or URL inspection responses
- [ ] Optionally test with telemetry (e.g., Canarytokens, GSuite link previews)

---

### 🎯 Deliverables
- Library of:
  - QR phishing designs (PDF, sticker format)
  - SMS phish templates (inbound/outbound wording)
  - Placement tactics (e.g., bathrooms, elevators, desks)
- Metrics from test users or test lab scans
- Risk write-up:
  - Top performing lures
  - Technical vs social difficulty
  - Visibility to detection tools
- Countermeasures:
  - Mobile EDR tuning
  - QR scanner warnings
  - Internal signage verification protocol

---

### 📚 Reference Materials
- QR Phishing Techniques (Lookout, Zimperium)  
- EvilQR PoC: https://github.com/quentinhardy/EvilQR  
- OWASP Phishing Resources: https://owasp.org/www-community/social_engineering  
- SMS spoofing research (HackTricks, Mobile Attacks)  
- NCSC QR guidance: https://www.ncsc.gov.uk/

---

### 🏷️ Tags / Labels
`initial-access` `qr-phishing` `social-engineering` `mobile` `sms-phish` `physical` `junior-friendly` `t1566`

---

### 📈 Effort Level
**Medium (M)** — requires creative thinking, infrastructure for lures, and physical/social setup.

---

### ✅ Acceptance Criteria
- [ ] At least 3 distinct initial access techniques tested (QR, SMS, rogue signage)
- [ ] Templates created and saved to shared repo
- [ ] Metrics or test results captured from at least 1 live trial
- [ ] Countermeasure suggestions documented in wiki or internal guidance
