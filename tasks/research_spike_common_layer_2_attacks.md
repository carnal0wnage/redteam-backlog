# 🌐 Research Spike: Common Layer 2 Attacks (2025 Edition)

**Goal:**  
Test a modern corporate network for viable Layer 2 attack paths, such as ARP spoofing, rogue DHCP, VLAN hopping, and MAC flooding — to simulate pivot, sniffing, or DoS scenarios in poorly segmented or legacy environments.

**Why It Matters:**  
Layer 2 attacks still persist in flat networks, legacy infrastructure, or poorly configured access layers. Many EDR and detection platforms focus on Layer 3+ and overlook switch-level or MAC-based abuse, especially in on-prem, lab, or hybrid deployments.

---

### 🔍 Scope
- Target environments:
  - Flat Layer 2 subnets (guest VLANs, lab networks)
  - VoIP / printer / unmanaged device VLANs
  - User access switch ports (802.1X or not)
- Still-viable attacks in 2025:
  - ✅ ARP spoofing / poisoning
  - ✅ DHCP starvation + rogue DHCP
  - ✅ MAC address flooding (CAM table exhaustion)
  - ✅ VLAN hopping via double tagging or trunk abuse
  - ✅ STP manipulation (Spanning Tree Protocol root hijack)
  - ✅ Multicast spoofing / IGMP hijacking
  - ✅ LLDP spoofing for topology mapping
  - ✅ Passive packet sniffing in misconfigured environments

---

### ✅ Tasks
- [ ] Deploy test system to target VLAN or physical port
- [ ] Run baseline recon:
  - `tcpdump`, `arp-scan`, `lldpctl`, `netdiscover`
- [ ] Execute attacks:
  - ARP spoofing (Bettercap, arpspoof)
  - Rogue DHCP (Yersinia, dhcpstarv)
  - VLAN hopping (double-tagged frames w/ scapy)
  - MAC flooding (macof or custom script)
  - STP root claim via BPDU injection
- [ ] Observe network impact:
  - Sniffed credentials or sessions
  - Pivot opportunities
  - Switch CPU spikes / service impact
- [ ] Identify mitigations in place:
  - DHCP snooping, DAI, Port Security, 802.1X
  - VLAN pruning, trunk restrictions
- [ ] Document effective attack paths vs blocked ones

---

### 🎯 Deliverables
- Attack result matrix (works / blocked / degraded)
- PCAPs of successful MITM or DoS attacks
- Diagram of switch-level attack surface
- Recommendations:
  - Enforce 802.1X with dynamic VLAN assignment
  - Enable Port Security with MAC binding
  - Deploy DHCP snooping + DAI
  - Disable unused trunking and double-tagged frames
- Scripts for:
  - Automated L2 recon
  - Simulated rogue DHCP injection
  - VLAN tag manipulations with `scapy`

---

### 📚 Reference Materials
- MITRE ATT&CK T1557.002 (ARP Cache Poisoning): https://attack.mitre.org/techniques/T1557/002/  
- Cisco L2 Attack Mitigations: https://www.cisco.com/c/en/us/about/security-center/layer2-security.html  
- Bettercap: https://www.bettercap.org/  
- Yersinia (Layer 2 attack toolkit): https://github.com/tomac/yersinia  
- VLAN Hopping Primer: https://packetlife.net/blog/2008/sep/9/vlan-hopping/  

---

### 🏷️ Tags / Labels
`layer2` `vlan-hopping` `arp-spoofing` `mac-flooding` `rogue-dhcp` `bettercap` `stp-abuse` `sniffing` `l2-mitm` `t1557.002`

---

### 📈 Effort Level
**Medium (M)** — hands-on switch access required, plus test VLAN or segmented lab.

---

### ✅ Acceptance Criteria
- [ ] At least 3 Layer 2 attacks tested in lab or target VLAN
- [ ] Outcomes documented (impact, detection, mitigation present)
- [ ] Deliverables uploaded (PCAPs, diagrams, tool logs)
- [ ] Recommendations tailored to environment added to report
- [ ] Spike linked to service hardening or detection initiative