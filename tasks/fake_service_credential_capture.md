# 🎣 Research Spike: Create a Fake Service to Capture Vulnerability Scanner Logins

**Goal:**  
Develop a deceptive internal service (e.g., fake SSH, FTP, SMB, or HTTP login endpoint) that accepts inbound connection attempts from automated vulnerability scanners and captures login attempts, especially cleartext or default credentials.

**Why It Matters:**  
Security tools and vulnerability scanners often probe internal environments with default or weak credentials. Capturing these interactions can help red teams identify scanning behavior, uncover reused credentials, and exploit trust in scanning tools.

---

### 🔍 Scope
- Target login protocols:
  - SSH (port 22)
  - Telnet
  - SMB
  - FTP
  - Web-based logins (HTTP Basic, Forms)
- Goal is to appear vulnerable but never allow full access
- Logging of:
  - Credentials (cleartext or encoded)
  - Source IPs and scanner types
  - Timestamp and method used

---

### ✅ Tasks
- [ ] Set up decoy services using tools like:
  - [`Cowrie`](https://github.com/cowrie/cowrie) (SSH/Telnet honeypot)
  - Custom Python-based HTTP or FTP server
  - Fake SMB with [`smbtrap`](https://github.com/SecureAuthCorp/impacket/blob/master/examples/smbtrap.py)
- [ ] Configure on internal test network
- [ ] Wait for or lure vulnerability scanners to the decoy IP
- [ ] Log:
  - Attempted usernames and passwords
  - Request headers and banners
  - Credential reuse across services
- [ ] Analyze:
  - Whether scanners follow 301/302 redirects
  - Frequency of scanner retries
  - Default credential sets attempted
- [ ] Optional: Create web dashboard to view captured attempts in real-time

---

### 🎯 Deliverables
- Decoy login server running in internal test subnet
- Logs of scanner-driven login attempts
- Summary report:
  - What tools or engines triggered (e.g., Qualys, Nessus, Rapid7)
  - Credentials used
  - Internal source IPs and patterns
- Optional detection integration:
  - Syslog or Splunk feed
  - Alert on reused or privileged credentials

---

### 📚 Reference Materials
- MITRE ATT&CK:
  - T1110 – Brute Force
  - T1078 – Valid Accounts
- Cowrie Honeypot: https://github.com/cowrie/cowrie
- Nmap Scripts: `nmap -p 22 --script ssh-brute`
- SANS Honeypot Deployment Guide

---

### 🏷️ Tags / Labels
`senior` `credential-capture` `deception` `honeypot` `valid-accounts` `brute-force` `ssh` `ftp` `t1078` `t1110`

---

### 📈 Effort Level
**Medium (M)** — requires system config, scripting, and careful log parsing.

---

### ✅ Acceptance Criteria
- [ ] Fake service deployed and accepting login attempts
- [ ] Captured and logged at least 10 credential attempts
- [ ] Documented source and format of logins
- [ ] Red team report shared with captured data and findings
