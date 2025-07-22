# 🪪 Research Spike: Long-Range RFID Badge Capture & Cloning

**Goal:**  
Design or assemble a long-range RFID reader setup capable of capturing badge credentials (e.g., 125kHz HID Prox or 13.56MHz smart cards) from a distance, then clone or emulate those credentials for physical access red team simulations.

**Why It Matters:**  
Many organizations rely on badge-based physical access systems, which are often vulnerable to signal capture, replay, or cloning attacks — especially if they use legacy RFID protocols. Understanding this threat helps red teams uncover physical security gaps and train blue teams on real-world badge abuse scenarios.

---

### 🔍 Scope
- RFID badge types:
  - 125kHz (HID Prox, EM4100, Indala)
  - 13.56MHz (MIFARE, iCLASS, DESFire — for detection only, not breaking crypto)
- Equipment:
  - Proxmark3 (Easy, RDV4, or RDV4.01)
  - Long-range RFID readers (e.g., WAVE ID, long antenna + amplifier)
  - Power supply, antenna design (optional)
- Targets: employee badge environments (lab or controlled test zones)

---

### ✅ Tasks
- [ ] Research target badge system:
  - Badge frequency (125kHz vs 13.56MHz)
  - Reader type, manufacturer, credential format (Wiegand, raw HID)
- [ ] Set up reader for **long-range sniffing**:
  - Build or modify antenna for increased range
  - Power reader with portable battery or DC converter
  - Place device near high-traffic badge entry (lab/test zone only)
- [ ] Capture badge data using:
  - `proxmark3` with LF sniff mode (`lf search`, `lf hid read`)
  - Long-range reader connected to USB sniffer or Raspberry Pi
- [ ] Clone badge or simulate emulation:
  - Program blank 125kHz tag (T5577 or HID keyfob clone)
  - Test badge emulator (Flipper Zero, Proxmark tag emulation)
- [ ] Document read range, success rate, reliability
- [ ] Test against common defenses:
  - Shielded badge sleeves
  - Smartcards with crypto authentication (fail gracefully)
  - Multi-tech readers (e.g., fallback to legacy mode?)

---

### 🎯 Deliverables
- Badge tech matrix:
  - Badge type, frequency, encoding format, reader vendor
- Capture results:
  - Screenshots of raw badge reads
  - Observed UID/Wiegand data
  - Range at which reads succeed (in inches/feet)
- Clone or emulation results (with screenshots or logs)
- Detection & defense writeup:
  - Physical mitigations (badge sleeves, range blockers)
  - Reader configs (disable fallback to legacy mode)
  - Awareness training for badge handling

---

### 📚 Reference Materials
- Proxmark3: https://github.com/RfidResearchGroup/proxmark3  
- Flipper Zero Docs: https://docs.flipperzero.one/  
- BishopFox RFID Hacking Guide: https://bishopfox.com/blog/rfid-hacking-tools  
- RFID Tools & Tags: https://lab401.com/, https://dangerousprototypes.com  
- HID Prox Overview: https://www.hidglobal.com/sites/default/files/resource_files/hid-prox-product-brochure-en.pdf  
- MITRE ATT&CK T1200 (Hardware Additions): https://attack.mitre.org/techniques/T1200/

---

### 🏷️ Tags / Labels
`hardware-implant` `rfid` `badge-cloning` `physical-access` `t1200` `proxmark` `not-junior-friendly`

---

### 📈 Effort Level
**Large (L)** — involves hardware tuning, field testing, and signal capture/emulation.

---

### ✅ Acceptance Criteria
- [ ] Long-range reader assembled or acquired and configured
- [ ] Badge data captured in controlled environment
- [ ] At least one badge cloned or emulated (for supported types)
- [ ] Capture range and success rates documented
- [ ] Recommendations written for detection and user awareness
- [ ] Internal wiki or report shared with photos, tools, and test logs