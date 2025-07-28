# 🌐 Research Spike: IPv6-Only Network Reconnaissance

**Goal:**  
Develop and document techniques to discover, enumerate, and map internal IPv6-only networks. Focus on host discovery, service enumeration, and identifying potential targets where IPv4 is disabled or limited.

**Why It Matters:**  
As organizations adopt IPv6 for internal infrastructure, traditional IPv4-only recon tools and methodologies fall short. IPv6 can hide critical assets from standard scans, and many environments fail to monitor IPv6 traffic effectively. Understanding how to probe these networks increases red team coverage.

---

### 🔍 Scope
- Internal enterprise networks with dual-stack or IPv6-only subnets
- Linux, macOS, and Windows systems with IPv6 enabled
- Tools that support IPv6 network reconnaissance
- Scope is limited to **authorized internal lab or test environments**

---

### ✅ Tasks
- [ ] Set up or access an IPv6-enabled lab environment
- [ ] Perform IPv6 address discovery using:
  - `nmap -6`, `netdiscover`, `zmap`, `ipv6-toolkit`
  - Multicast ping sweep (ff02::1)
- [ ] Enumerate link-local and global addresses
- [ ] Identify IPv6 services (DNS, HTTP, SSH, LDAP) with:
  - `nmap -6 -sV`, `masscan`, `amap`, `nc`, `telnet`
- [ ] Document use of IPv6 extension headers or fragmented packets for stealth
- [ ] Evaluate network logging and detection gaps for IPv6 activity
- [ ] Compare results with IPv4-only recon for visibility deltas
- [ ] Optional: Test IPv6 SLAAC, RA spoofing, or DHCPv6 misconfigurations

---

### 🎯 Deliverables
- Markdown or wiki writeup with:
  - IPv6 recon tool list and commands
  - Key findings and visibility gaps
  - Screenshots or outputs from enumeration
  - Differences in recon capability vs. IPv4
  - Recommendations for IPv6 detection and hardening
- Optional:
  - Internal IPv6 subnet mapping
  - SLAAC or RA abuse PoC

---

### 📚 Reference Materials
- [nmap IPv6 support](https://nmap.org/book/man-target-specification.html)  
- [ipv6-toolkit](https://github.com/ivanthreat/ipv6-toolkit)  
- [SANS - IPv6 Reconnaissance](https://www.sans.org/white-papers/36697/)  
- [Offensive IPv6 Cheatsheet](https://github.com/0x4D31/Offensive-IPv6-Cheatsheet)  
- [Red Team IPv6 Attack Guide](https://github.com/cckuailong/IPv6-attack-toolkit)

---

### 🏷️ Tags / Labels
`mid-level` `network-recon` `ipv6` `dual-stack` `stealth-scan` `internal`

---

### 📈 Effort Level
**Medium (M)** — specialized tooling and test environments required.

---

### ✅ Acceptance Criteria
- [ ] IPv6-enabled recon lab set up or accessed
- [ ] At least 3 tools tested and documented for IPv6 scanning
- [ ] Clear evidence of visibility differences between IPv4 and IPv6
- [ ] Output shared via wiki, markdown, or report with screenshots
- [ ] Recommendations for IPv6 detection improvements drafted
