# 🧰 Research Spike: Rogue USB-C Multi-Function Implant (Video + KVM + LAN)

**Goal:**  
Build, acquire, or analyze a covert hardware implant that poses as a standard USB-C docking hub or multi-function adapter (e.g., HDMI, Ethernet, USB hub) while enabling covert command-and-control via hidden network interfaces, HID injection, or KVM-style remote access.

**Why It Matters:**  
Executives, IT staff, and remote workers frequently use USB-C hubs and travel docks — creating a perfect cover for stealth hardware implants. With video passthrough and HID/network access, an attacker can bypass endpoint protections entirely and gain direct access to a live, trusted machine.

---

### 🔍 Scope
- Commercial off-the-shelf (COTS) or DIY USB-C docking hubs
- Target OS: Windows/macOS (laptop)
- Implant capabilities:
  - Covert Ethernet interface or reverse proxy
  - HID injection (Rubber Ducky/OMG Cable-like behavior)
  - Optional: HDMI passthrough or video capture for VNC-style exfil

---

### ✅ Tasks
- [ ] Acquire or build test implant:
  - COTS USB-C hub with modifiable internals, or
  - DIY build using:
    - Raspberry Pi Zero 2W
    - PiKVM / USB Armory / OMG Cable firmware
    - USB-to-Ethernet chipset (ASIX / Realtek)
- [ ] Add one or more payload paths:
  - [ ] Hidden reverse shell or tunneling payload via embedded NIC
  - [ ] HID script for credential exfil or command execution
  - [ ] Keylogger or clipboard monitor (if feasible)
- [ ] Test implant on macOS and Windows targets:
  - Observe pop-ups, device manager artifacts, or AV/EDR response
  - Confirm device shows as expected (e.g., “USB Ethernet” or “HDMI display”)
- [ ] Document detection surfaces:
  - Device enumeration (`lsusb`, `ioreg`, Windows Device Manager)
  - Network logs, keystroke injection behavior
  - USB serial/VID/PID analysis
- [ ] Build user awareness playbook:
  - Visual indicators to check for tampering
  - Travel device policies or supply chain controls
  - Physical security controls (USB port blockers, EDR with HID alerts)

---

### 🎯 Deliverables
- Hardware build notes or teardown of COTS device
- Payload logic: HID script, network tunneling configs, keylogger PoC (safe)
- Test results from Windows/macOS:
  - Screenshots of detected devices
  - Execution traces
  - AV or OS alerts
- Detection and defense recommendations:
  - Host-level (USB restrictions, audit logging)
  - Physical (tamper-evident tape, device lockdown)
  - User training (USB hygiene)
- Executive-focused 1-pager for awareness training

---

### 📚 Reference Materials
- Hak5 OMG Cable: https://shop.hak5.org/products/omg-cable  
- PiKVM Project: https://pikvm.org/  
- USB Rubber Ducky: https://github.com/hak5darren/USB-Rubber-Ducky/wiki  
- Raspberry Pi Zero HID tricks: https://github.com/gtfobins/gtfobins/blob/master/exploits/raspberrypi_hid.md  
- MITRE ATT&CK T1200 (Hardware Additions): https://attack.mitre.org/techniques/T1200/  
- USB Forensics Tools: `usbview`, `usbmon`, `UDEV`, `ioreg`, Windows Event IDs 2003–2103

---

### 🏷️ Tags / Labels
`hardware-implant` `usb-attack` `physical-access` `hid-injection` `covert-access` `t1200` `advanced-tradecraft`

---

### 📈 Effort Level
**Large (L)** — especially if building DIY hardware or modifying internals. Moderate (M) if analyzing or testing COTS implants.

---

### ✅ Acceptance Criteria
- [ ] At least one implant (COTS or DIY) acquired or simulated
- [ ] Payload successfully delivered (e.g., HID or covert network path)
- [ ] Detection vectors logged and screenshots captured
- [ ] Build notes or teardown photos included
- [ ] Recommendations created for defense and user training