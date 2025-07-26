# 🛡️ Research Spike: Write a Sliver or Mythic Profile Mimicking Corporate TLS Patterns

**Goal:**  
Create and deploy a custom Sliver or Mythic C2 profile that mimics the TLS fingerprint (JA3, domain fronting) of internal corporate traffic.

**Why It Matters:**  
EDRs and NDRs detect C2 via anomalies in TLS fingerprints or SNI headers. Mimicking known-good patterns reduces detection and increases dwell time.

---

### 🔍 Scope
- Sliver or Mythic C2
- TLS configuration: ciphers, headers, JA3
- Test network with TLS inspection or Zeek

---

### ✅ Tasks
- [ ] Capture real corporate TLS fingerprints (JA3 hashes)
- [ ] Modify or write profile to match:
  - TLS handshake sequence
  - Domain fronting (optional)
  - Keep-alive behavior
- [ ] Validate against Zeek/JA3 or Bro logs
- [ ] Document detection evasion benefit

---

### 🎯 Deliverables
- Custom TLS profile for Sliver/Mythic
- Comparison of JA3 before/after
- Wireshark or Zeek PCAPs
- Detection notes and evasion outcome

---

### 📚 Reference Materials
- Sliver profile dev docs  
- JA3: https://github.com/salesforce/ja3  
- Domain fronting writeups

---

### 🏷️ Tags / Labels
`c2` `tls` `ja3` `sliver` `mythic` `domain-fronting` `edr-evasion`

---

### 📈 Effort Level
**Medium (M)** — strong red team signal with stealth benefits.

---

### ✅ Acceptance Criteria
- [ ] TLS fingerprint matched to corporate pattern
- [ ] JA3 hash recorded and documented
- [ ] Packet capture and visual confirmation
