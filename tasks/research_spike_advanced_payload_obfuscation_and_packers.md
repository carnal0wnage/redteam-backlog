# 🧬 Research Spike: Advanced Payload Obfuscation & Packers

**Goal:**  
Develop and test advanced techniques for obfuscating payloads — including custom packers, encryption layers, and in-memory loaders — to bypass modern endpoint detection and response (EDR), antivirus (AV), and static analysis tools.

**Why It Matters:**  
Many off-the-shelf payloads are rapidly signatured and flagged. Building internal red team capability around obfuscation, packing, and evasive loaders increases resilience during assessments and improves understanding of evasion mechanics.

---

### ✅ Tasks

- [ ] Review known packers and obfuscators (UPX, ConfuserEx, Donut, sRDI)
- [ ] Build or adapt:
  - Custom XOR or AES packers for shellcode/PEs
  - In-memory loaders (C++, Nim, Rust, PowerShell, Python)
  - Section shufflers, header manglers, poly loaders
- [ ] Create automation scripts for:
  - Multi-layer obfuscation pipelines
  - Stub generation with variable payload wrappers
- [ ] Test against:
  - Defender + common EDR platforms (CrowdStrike, SentinelOne, etc.)
  - VT-like static analysis engines
- [ ] Document detection delta per iteration
- [ ] Optionally add features:
  - Delayed execution
  - Parent PID spoofing
  - AMSI and ETW bypasses

---

### 🎯 Deliverables

- Obfuscation pipeline script or tool (Python, C#, or shell)
- Sample payloads and evasion metrics across iterations
- EDR/Defender detection chart
- Recommendations:
  - Layer obfuscation (packer + in-memory loader)
  - Vary IAT, PE metadata, and encoding per op
  - Build per-engagement unique stubs

---

### 📚 References

- MITRE ATT&CK T1027.002 (Software Packing)  
- Donut Shellcode Generator: https://github.com/TheWover/donut  
- sRDI: Shellcode Reflective DLL Injection  
- NimPackt or NimlineWhispers (Nim loaders)  
- AMSI/ETW bypasses: https://github.com/RythmStick/BypassAV  
- Daniel Bohannon Obfuscation Techniques

---

### 🏷️ Tags

`payload-evasion` `packer` `obfuscation` `bypass-av` `in-memory` `sRDI` `donut` `nim` `amsi-bypass` `t1027`

---

### 📈 Effort Level

**Large (L)** — involves scripting, evasive engineering, detection testing, and lab tuning.

---

### ✅ Acceptance Criteria

- [ ] Obfuscation pipeline script created and tested  
- [ ] Payload runs cleanly on at least 1 EDR-protected test VM  
- [ ] Detection delta documented across iterations  
- [ ] Usage guide and safety notes provided for internal red team  
- [ ] Artifacts added to internal tooling repo under `redteam/payloads/evade`