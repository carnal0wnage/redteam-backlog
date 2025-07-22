# 🧬 Research Spike: Chaining Low Vulns into High Exploitation Paths (Low2Pwned)

**Goal:**  
Identify and document how medium (or even low) severity vulnerabilities — especially those ignored by remediation teams — can be chained together to achieve RCE, privilege escalation, lateral movement, or initial foothold elevation in internal environments.

**Why It Matters:**  
Real-world privilege escalation often begins with overlooked misconfigurations or subtle flaws. By learning to chain these together, red teamers can emulate realistic post-access progression and help defenders prioritize the “boring but dangerous.”

---

### ✅ Tasks

- [ ] Review scanner output (Nessus, Qualys, OpenVAS, etc.) or prior red team findings
- [ ] Filter for:
  - Misconfigurations (e.g., writable services, weak permissions)
  - Insecure versions with known LPEs (Local Priv Esc vulnerabilities)
  - Information disclosures (e.g., config backups, error messages)
  - Open shares or unauthenticated internal web apps
- [ ] Identify at least **3-5 medium/low issues** that could support escalation
- [ ] Research CVEs or known chaining techniques (e.g., LFI + log injection → RCE)
- [ ] Document 1–2 complete attack chains with step-by-step escalation logic

---

### 🎯 Deliverables

- Attack path diagrams and written walkthroughs
  - Include starting vuln, chain logic, and end-state (e.g., local admin or domain escalation)
- Annotated scanner report: highlight overlooked priv-esc points
- Recommendations:
  - Flag these types of findings in future scans
  - Create purple team detection coverage for each chain step
  - Share playbooks with vulnerability management teams

---

### 📚 References

- MITRE ATT&CK T1068 (Exploitation for Privilege Escalation)  
- GTFOBins (Linux privesc abuse cases): https://gtfobins.github.io  
- LOLBAS (Windows built-in abuse paths): https://lolbas-project.github.io  
- HackerOne/BB writeups involving chained medium-severity vulns  
- “From Misconfig to DA” blog posts (SpecterOps, MDSec)

---

### 🏷️ Tags

`privesc` `vuln-chaining` `medium-risk` `misconfig` `windows` `linux` `lateral-movement` `t1068` `red-team-ops` `defense-prioritization`

---

### 📈 Effort Level

**Medium (M)** — requires research, testing in lab, and chaining logic; ideal for red teamers and purple team analysts.

---

### ✅ Acceptance Criteria

- [ ] At least 3 real-world medium/low findings identified and chained  
- [ ] 1–2 escalation chains fully documented (steps, tools, logic)  
- [ ] Clear visual or written path from “boring” vuln to elevated access  
- [ ] Shared with detection and vulnerability management teams  
- [ ] Considered for inclusion in red team toolkit and purple scenarios
