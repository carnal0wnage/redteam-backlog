# 🪪📱 Research Spike: Enterprise Badge Clone vs Mobile Credential Replay

**Goal:**  
Compare the attack surface of traditional proximity-based access badges (e.g., 125kHz HID Prox) against modern mobile credentials (e.g., NFC/BLE-based Apple Wallet, HID Mobile Access). Test cloning, replay, and relay capabilities for both, and assess how they integrate into on-premises logical access control systems.

**Why It Matters:**  
Organizations often upgrade physical access systems piecemeal, mixing legacy and modern badge types. Understanding which technologies are easiest to bypass — and how they tie into directory services or VPN auth — helps red teams provide strategic modernization advice.

---

### 🔍 Scope
- Legacy badges:
  - HID Prox, EM4100, Indala (125kHz, clonable)
- Mobile credentials:
  - HID Mobile Access, Apple Wallet NFC badge, Samsung Wallet, Bluetooth SmartBadge apps
- Test environment:
  - Controlled badge readers, door controllers, and logical auth integrations (e.g., badge-to-VPN SSO)

---

### ✅ Tasks
#### Badge Cloning
- [ ] Identify and document legacy badge type in use
- [ ] Clone test badge using:
  - Proxmark3 (`lf hid read` + `lf hid clone`)
  - Flipper Zero or T5577 rewritable tags
- [ ] Test cloned badge on real reader or lab rig
- [ ] Document success rate, range, time to clone

#### Mobile Credential Replay
- [ ] Set up mobile credential (e.g., HID Mobile Access)
- [ ] Attempt to:
  - Intercept BLE/NFC exchange using relay tools (Flipper BLE proxy, ESP32)
  - Replay interaction in real-time to reader emulator
- [ ] Document outcomes:
  - Does replay succeed? 
  - Latency or challenge/response timeout?
  - OS notifications or user warnings?

#### Integration Testing
- [ ] Trace badge/mobile signal to logical auth system:
  - LDAP/AD sync?
  - VPN or SSO mapping?
- [ ] Attempt to pivot from physical badge to logical account access
- [ ] Log any differences in audit visibility

---

### 🎯 Deliverables
- Attack Matrix:
  - Compare clone/replay success for badge vs. mobile
- Screenshots or recordings of:
  - Clone tools in action
  - Relay signal logs (pcap or SDR traces)
- Success metrics:
  - Clone time, replay latency, read range, bypass rate
- Recommendations:
  - Short-term controls (badge sleeves, alerting)
  - Long-term roadmap (kill legacy Prox, enforce MFA on badge-linked auth)
- Upgrade prioritization worksheet:
  - Reader model, badge tech, attack exposure, upgrade cost factor

---

### 📚 Reference Materials
- Proxmark3: https://github.com/RfidResearchGroup/proxmark3  
- HID Mobile Access: https://www.hidglobal.com/products/mobile-access  
- BLE Relay Tools: https://github.com/0xchocolate/flipper-badge-relay  
- NFC Relay via Android: https://github.com/ICReverseEngineeringProject/nfcrelay  
- MITRE ATT&CK T1200 (Hardware Additions): https://attack.mitre.org/techniques/T1200/  
- HID Credential Comparisons: https://www.hidglobal.com/sites/default/files/resource_files/hid-card-comparison-guide-en.pdf  
- BishopFox Badge Research: https://www.bishopfox.com/blog/rfid-hacking-tools

---

### 🏷️ Tags / Labels
`badge-cloning` `mobile-credential` `ble` `nfc` `rfid` `proxmark` `flipper` `relay-attack` `access-control` `t1200`

---

### 📈 Effort Level
**Medium (M)** — requires physical badge hardware, BLE/NFC tooling, and basic physical access testing environment.

---

### ✅ Acceptance Criteria
- [ ] Legacy badge cloned and tested successfully (or documented failure)
- [ ] Mobile credential replay attempted and logged
- [ ] Access path to on-prem auth systems mapped for both badge types
- [ ] Comparative matrix completed
- [ ] Strategic recommendations documented (with screenshots, diagrams, and upgrade priorities)