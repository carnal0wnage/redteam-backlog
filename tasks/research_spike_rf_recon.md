# 📻 Research Spike: RF Recon – Guard Radios, Bluetooth Headsets, Conference Mics

**Goal:**  
Identify and analyze unencrypted RF communication sources in the corporate environment — including guard radio chatter, Bluetooth headset leakage, wireless conference room microphones, or DECT/2.4GHz audio systems — to evaluate eavesdropping or impersonation risk.

**Why It Matters:**  
Organizations often overlook the physical-layer attack surface. Security guards, receptionists, and execs may unknowingly leak credentials, alarm codes, or sensitive business intel over unsecured radios or headsets. These channels can be silently intercepted, recorded, and abused.

---

### 🔍 Scope
- Analog & digital radios (e.g., VHF/UHF walkie-talkies)
- Bluetooth Classic / BLE headsets, keyboards, speakers
- DECT-based wireless mics or phones (e.g., Polycom, Cisco)
- Proprietary 2.4GHz wireless audio gear
- Targets: guard stations, front desk, exec conference rooms, boardrooms

---

### ✅ Tasks
- [ ] Hardware setup:
  - SDR (e.g., HackRF, RTL-SDR, LimeSDR, Flipper Zero)
  - Directional antenna or wideband omni antenna
  - Bluetooth scanning tools (`bluetoothctl`, `btmon`, `BLEScanner`, Flipper)
- [ ] Passive RF survey:
  - Sweep 30 MHz – 1 GHz (guard radios, analog/digital voice)
  - Sweep 2.4 GHz spectrum (Bluetooth, DECT, wireless mics)
  - Use tools like:
    - `SDR#`, `GQRX`, `CubicSDR` (for real-time monitoring)
    - `URH`, `rfcat`, `BLEScanner`, `Kismet`
- [ ] Identify signals of interest:
  - Listen for voice or DTMF tones
  - Match MACs to known headset vendors (Apple, Bose, Plantronics, etc.)
  - Tag DECT or proprietary audio protocols
- [ ] Test recording / replay feasibility:
  - Can you record audio from radios or mics?
  - Can Bluetooth be coerced into pairing or audio redirection?
  - Can DECT calls be intercepted? (Only with proper test gear!)
- [ ] Document risk scenarios:
  - Guard shares alarm PINs over unencrypted walkie
  - Bluetooth headset keeps channel open after meeting
  - Conference mic leaks exec conversations during standby

---

### 🎯 Deliverables
- RF frequency map of site:
  - Frequencies used, modulation, encryption/no-encryption
- Device matrix:
  - Brand/model, range, signal strength, attack potential
- Captured audio or packet logs (only in test environments)
- Replay test results (if applicable)
- Risk scoring for each device class
- Mitigation guidance:
  - Use encrypted radio systems (e.g., P25, TETRA)
  - Disable standby mics
  - Rotate Bluetooth devices regularly
  - Block external RF with shielding/filters

---

### 📚 Reference Materials
- RTL-SDR Setup: https://www.rtl-sdr.com/  
- SDRSharp: https://airspy.com/download/  
- Universal Radio Hacker: https://github.com/jopohl/urh  
- GQRX SDR: https://gqrx.dk/  
- Flipper Zero RF Tools: https://docs.flipperzero.one/  
- BlueHydra Bluetooth Recon: https://github.com/pwnieexpress/blue_hydra  
- DECT Sniffing with RTL-SDR: https://www.rtl-sdr.com/tag/dect/  
- MITRE T1420 (Eavesdropping): https://attack.mitre.org/techniques/T1420/

---

### 🏷️ Tags / Labels
`rf-recon` `bluetooth` `dect` `guard-radio` `conference-mic` `sdr` `eavesdropping` `t1420` `not-junior-friendly`

---

### 📈 Effort Level
**Large (L)** — requires hardware, RF knowledge, signal hunting, and interpretation of low-level comms.

---

### ✅ Acceptance Criteria
- [ ] SDR sweep logs and visual signal captures collected
- [ ] At least 2 device types (e.g., radio + headset) identified and analyzed
- [ ] Audio/packet recording proof-of-concept created (test only)
- [ ] RF frequency + device matrix documented
- [ ] Clear recommendations written for blue team (technical + awareness)
- [ ] Internal wiki or report includes screenshots, diagrams, and tool configs