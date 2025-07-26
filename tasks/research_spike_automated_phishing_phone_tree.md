# ☎️ Research Spike: Automated Phishing Phone Trees

**Goal:**  
Build and test a programmable phone tree (IVR system) that impersonates trusted brands (e.g., bank, IT, HR hotline) to automatically harvest credentials, MFA codes, or sensitive responses. Evaluate realism, interaction drop-off, and detection challenges.

**Why It Matters:**  
Automated phone phishing (a.k.a. vishing) at scale removes the need for a live attacker and increases volume and coverage. Pretexted robocalls with voice menus or SMS callbacks can capture sensitive info from victims trained to trust phone interactions.

---

### 🔍 Scope
- Target vectors:
  - MFA code harvesting (“Press 1 to confirm your identity”)
  - Password reset flows (“Enter your AD username and current password”)
  - Benefits/HR phishing (“Confirm your SSN to update your benefits”)
- Tools:
  - Twilio Studio or Asterisk for IVR flows
  - DTMF capture and storage
  - Speech-to-text for voicemail or spoken responses
- Pretexts:
  - MFA approval (“Your IT account was accessed — to stop this, press 2”)
  - Office 365 re-authentication
  - HR call for time-sensitive update (e.g., “open enrollment”)

---

### ✅ Tasks
- [ ] Build IVR system with:
  - Welcome message
  - Dynamic menu (“Press 1 for security, 2 for HR…”)
  - DTMF recording and logging
  - Optional: Speech-to-text transcription of voicemail or verbal input
- [ ] Record realistic voice messages:
  - Use cloned voices or standard professional text-to-speech
  - Tune for pacing, tone, and caller ID spoofing
- [ ] Simulate outbound call campaign (authorized lab targets only)
- [ ] Measure:
  - Answer vs. hang-up rates
  - DTMF input submission
  - Whether targets notice red flags
- [ ] Document detection & prevention:
  - EDR logging of call apps
  - Telephony gateway filtering
  - Behavioral call analytics
  - Voiceprint registration vs. challenge-response auth

---

### 🎯 Deliverables
- Working IVR flow (Twilio Studio or Asterisk script)
- Audio recordings (attack messages and menu prompts)
- Attack tree diagram (call → menu → DTMF capture)
- Metrics dashboard:
  - % call pickup, menu navigation depth, DTMF entries
- Recommendations:
  - Flag outbound robocalls mimicking internal numbers
  - Pre-warn employees about HR/MFA phishing vectors
  - Add behavioral checks for high-risk calls

---

### 📚 Reference Materials
- Twilio Studio IVR Docs: https://www.twilio.com/docs/studio  
- Asterisk IVR Tutorial: https://wiki.asterisk.org/wiki/display/AST/Creating+Interactive+Voice+Response+(IVR)+Menus  
- MITRE ATT&CK T1598 (Phishing for Information): https://attack.mitre.org/techniques/T1598/  
- TTPs of Vishing Groups (e.g., FIN7): https://www.cisa.gov/news-events/cybersecurity-advisories/aa21-265a  
- EvilnoVNC Project (voice phishing simulation): https://github.com/nccgroup/EvilnoVNC  

---

### 🏷️ Tags / Labels
`ivr` `vishing` `voice-phishing` `dtmf` `mfa-harvest` `twilio` `asterisk` `automated-attacks` `t1598`

---

### 📈 Effort Level
**Medium (M)** — requires light scripting, IVR platform familiarity, and audio pretexting.

---

### ✅ Acceptance Criteria
- [ ] IVR tree deployed and callable via public number
- [ ] Menu options simulate phishing pretexts
- [ ] Logging of DTMF input or speech-to-text responses
- [ ] Sample phishing call campaign simulated (with consent or in lab)
- [ ] Recommendations for mitigation and training documented