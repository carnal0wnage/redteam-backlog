# 🧭 Research Spike: Write a Script to Auto-Pivot with SSH + Proxychains + Route Injection

**Goal:**  
Build a script or small tool that automates post-foothold pivoting with SSH dynamic forwarding, proxychains config, and optional route additions.

**Why It Matters:**  
Pivoting is a tedious and error-prone task that slows down ops. Automating this helps red teamers move faster while also standardizing logs and cleanup.

---

### 🔍 Scope
- Internal network pivoting
- Tools: `ssh`, `proxychains`, `iptables`, `socat`, `chisel`
- Linux/Unix environment with SSH access

---

### ✅ Tasks
- [ ] Build script that:
  - [ ] Establishes SSH dynamic SOCKS tunnel
  - [ ] Edits proxychains.conf
  - [ ] Verifies connectivity to internal IPs
  - [ ] Optionally adds routes
- [ ] Test access through:
  - Nmap
  - Curl
  - Web proxy tools
- [ ] Clean up afterward

---

### 🎯 Deliverables
- Pivot script (.sh or .py)
- Example target with proxychains/Nmap success
- Cleanup routine or signal trap handler

---

### 📚 Reference Materials
- Proxychains-ng  
- Chisel: https://github.com/jpillora/chisel  
- SSH tunneling docs

---

### 🏷️ Tags / Labels
`pivoting` `ssh` `proxychains` `tunneling` `network-access`

---

### 📈 Effort Level
**Medium (M)** — excellent hands-on pivot automation and tunnel hardening.

---

### ✅ Acceptance Criteria
- [ ] Script runs SOCKS proxy and confirms connectivity
- [ ] Output verified via test connection
- [ ] Readme or wiki usage doc created
