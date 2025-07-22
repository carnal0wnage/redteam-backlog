# 🛰️ Research Spike: C2 Infrastructure Basics (Redirectors + Profiles)

**Goal:**  
Stand up a basic C2 infrastructure stack consisting of a redirector (Apache or Nginx) and a command-and-control framework (e.g., Cobalt Strike, Mythic, Sliver). Customize and test basic HTTP profiles to simulate real-world beaconing while observing how traffic behaves across layers.

**Why It Matters:**  
Understanding C2 infrastructure is critical to red team operations. Junior operators often rely on pre-built platforms, but building and customizing redirectors teaches OPSEC, detection evasion, and command flow fundamentals.

---

### 🔍 Scope
- Single redirector (e.g., DigitalOcean, AWS, home lab)
- Single C2 framework: Mythic (recommended for open source) or Sliver
- HTTP(S)-based beacon channel
- Custom redirector rules & basic profile customization
- Beaconing validation and packet inspection

---

### ✅ Tasks
- [ ] Deploy a redirector server (Apache or Nginx)
- [ ] Configure basic redirector rules (e.g., `/blog` = redirect, `/index` = C2 handler)
- [ ] Set up a Mythic or Sliver C2 server with basic teamserver config
- [ ] Create a new HTTP profile:
  - Change default URIs
  - Modify headers (User-Agent, Host, Cookie)
  - Add jitter or randomized sleep
- [ ] Launch test implant and verify:
  - Successful check-in through redirector
  - Proper logging of C2 traffic
- [ ] Use `tcpdump`, `Wireshark`, or `Zeek` to analyze traffic and verify OPSEC hygiene
- [ ] Document command structure, redirector logic, and where logs appear
- [ ] Identify what would be obvious to blue team tooling (default headers, jitter, URIs)

---

### 🎯 Deliverables
- Internal wiki or repo page with:
  - Step-by-step setup of redirector and C2
  - Screenshot of successful beacon check-in
  - Sample HTTP profile used
  - Screenshots or captures of C2 traffic
  - List of OPSEC pitfalls observed (e.g., default URIs or server headers)
- Cleanup instructions or teardown script

---

### 📚 Reference Materials
- TrustedSec Redirector Configs: https://github.com/trustedsec/egressbuster  
- Raphael Mudge blogs on redirectors: https://blog.cobaltstrike.com  
- Mythic C2: https://github.com/its-a-feature/Mythic  
- Sliver C2: https://github.com/BishopFox/sliver  
- Nginx Redirector Example: https://github.com/0x4D31/nginxC2Redirector  
- Packet Analysis Basics: https://wiki.wireshark.org/

---

### 🏷️ Tags / Labels
`junior-friendly` `c2` `infrastructure` `redirector` `mythic` `sliver` `ops-fundamentals`

---

### 📈 Effort Level
**Medium (M)** — setup is straightforward, but testing and troubleshooting adds learning curve.

---

### ✅ Acceptance Criteria
- [ ] Redirector and C2 deployed and functioning
- [ ] Implant beacon successfully passes through redirector
- [ ] Custom HTTP profile used (non-default URIs/headers)
- [ ] Traffic observed and documented
- [ ] At least 3 OPSEC observations noted (e.g., headers, cert issues, redirect fingerprints)
- [ ] Internal guide or checklist created for future infra deployments