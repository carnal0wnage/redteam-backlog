# 📶 Research Spike: RFID Relay Attacks via BLE / Wi-Fi (Badge Replay)

**Goal:**  
Build and test a proof-of-concept RFID relay setup that transmits badge data over BLE or Wi-Fi to a remote relay station near a legitimate badge reader. This demonstrates how attackers can access secure areas by forwarding real badge signals — without cloning or decrypting them.

**Why It Matters:**  
Many modern RFID systems (even encrypted ones like iCLASS SE or MIFARE DESFire) are vulnerable to relay attacks. This bypasses crypto by transmitting the raw challenge-response in real time. Executives, high-value targets, and keycard holders are especially vulnerable in public areas.

---

### 🔍 Scope
- Supported badge types:
  - 13.56 MHz cards (e.g., iCLASS SE, DESFire EV1/EV2, MIFARE Classic)
- Devices:
  - Flipper Zero w/ BLE module
  - Proxmark3 RDV4 or PiKVM w/ USB RFID reader
  - Custom relay setups (ESP32, BLE proxy, Raspberry Pi)
- Environments:
  - Lab or authorized test zone with known card readers

---

### ✅ Tasks
- [ ] Choose relay path:
  - BLE: Flipper Zero → phone/ESP32 → relay reader
  - Wi-Fi: Raspberry Pi sniffer → VPN tunnel → remote Proxmark
- [ ] Set up reader-side receiver:
  - Proxmark3, contactless USB reader, or commercial door reader in lab
- [ ] Set up badge-side transmitter:
  - Flipper Zero BLE relay firmware or app like `nfc-relay`
  - Phone or ESP32 Bluetooth proxy script
- [ ] Capture challenge/response from real badge
- [ ] Relay signal in real-time to remote reader
  - Confirm if access is granted or handshake succeeds
  - Log delay/latency issues
- [ ] Measure range and signal reliability:
  - What’s the max distance from cardholder?
  - How much delay is tolerable before handshake fails?
- [ ] Investigate the best tool for the job
  - ESPKey https://www.redteamtools.com/espkey
  - BLEKey https://hackerwarehouse.com/product/blekey/
  - The Tick https://www.securing.pl/en/the-tick/  https://www.securing.pl/eetsassy/2025/03/The-Tick-Field-Guide.pdf https://github.com/jkramarz/TheTick

---

### 🎯 Deliverables
- Relay Architecture Diagram:
  - Device 1 (badge-side), network channel, Device 2 (reader-side)
- Device configurations and firmware used
- Test results:
  - Badge type, reader type, signal success/fail
  - Distance and latency measurements
- Failure modes:
  - Crypto timeout
  - Signal collision
  - Reader retry thresholds
- Detection + defense writeup:
  - Randomized cryptographic challenge timeout
  - Anti-relay protections (distance bounding, motion sensors, tap patterns)

---

### 📚 Reference Materials
- Flipper BLE Badge Relay Project: https://github.com/0xchocolate/flipper-badge-relay  
- RFIDler Relay Research: https://github.com/ApertureLabsLtd/RFIDler  
- Black Hat Talk – “Badge of Shame” by BishopFox: https://www.youtube.com/watch?v=tbtzN0AiqPY  
- NFCRelay (Android): https://github.com/ICReverseEngineeringProject/nfcrelay  
- MITRE ATT&CK T1200 (Hardware Additions): https://attack.mitre.org/techniques/T1200/  
- MIFARE Attack Research: https://www.usenix.org/conference/woot15/workshop-program/presentation/garcia
- Bishop Fox: https://bishopfox.com/tools/rfid-hacking
- BlackHat Talk: https://i.blackhat.com/Asia-25/Asia-25-Zdunczyk-Behind-Closed-Doors-Bypassing-RFID-Readers.pdf


---

### 🏷️ Tags / Labels
`rfid` `relay-attack` `physical-access` `smartcards` `t1200` `flipper` `nfc` `not-junior-friendly`

---

### 📈 Effort Level
**Large (L)** — requires hardware integration, RF understanding, network relaying, and real-time performance testing.

---

### ✅ Acceptance Criteria
- [ ] Relay path established between badge-side and reader-side devices
- [ ] At least one badge signal relayed successfully (e.g., challenge/response forwarded)
- [ ] Success/failure conditions documented
- [ ] Range, latency, and reliability metrics captured
- [ ] Defense and mitigation recommendations shared (technical + physical)
- [ ] Wiki/report includes diagrams, screenshots, and all hardware configs