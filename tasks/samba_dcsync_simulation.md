# 🧪 Research Spike: Samba Server for Legitimate DCSync Attack Simulation

**Goal:**  
Create a script that spins up a Samba server with the necessary configuration to simulate a Domain Controller for the purpose of testing DCSync attacks in a controlled, legitimate lab environment.

**Why It Matters:**  
DCSync attacks (abusing `replicate directory changes` rights) are a powerful method for extracting domain credentials. Simulating this against a fake Samba DC allows red teams to test detection and demonstrate impact without affecting production environments.

---

### 🔍 Scope
- Deploy Samba on an isolated Linux VM
- Configure Samba to simulate AD replication capabilities
- Grant a controlled user the `Replicate Directory Changes` rights
- Use Mimikatz or Impacket's `secretsdump.py` to run DCSync

---

### ✅ Tasks
- [ ] Write a setup script that:
  - Installs Samba and necessary dependencies
  - Configures it as a pseudo domain controller
  - Sets up a dummy domain and test user accounts
  - Enables LDAP and DRS replication features
- [ ] Grant DCSync rights to a test user:
  - Modify ACLs appropriately using `samba-tool`
- [ ] Validate using:
  - [ ] Mimikatz DCSync module
  - [ ] Impacket’s `secretsdump.py`
- [ ] Log and monitor:
  - What gets synced
  - Tool behavior and output
  - Detection opportunities on endpoint and network layers
- [ ] Optional:
  - Add Sysmon/log parser for Windows domain member telemetry
  - Create reusable snapshot of VM for resettable testing

---

### 🎯 Deliverables
- Script that sets up a Samba DCSync lab environment
- Proof that replication data can be requested by test user
- Screenshots or logs of `secretsdump`/`mimikatz` outputs
- Detection artifacts to share with blue team
- Write-up of how rights were configured and abused

---

### 📚 Reference Materials
- MITRE ATT&CK:
  - T1003.006 – DCSync
- Impacket SecretsDump: https://github.com/fortra/impacket
- Mimikatz DCSync: https://adsecurity.org/?p=1729
- Samba AD DC Guide: https://wiki.samba.org/index.php/Setting_up_Samba_as_an_Active_Directory_Domain_Controller

---

### 🏷️ Tags / Labels
`senior` `dcsync` `impacket` `mimikatz` `t1003.006` `samba` `simulation` `lab`

---

### 📈 Effort Level
**Medium (M)** — requires AD protocol familiarity and Samba config knowledge.

---

### ✅ Acceptance Criteria
- [ ] Samba server stands up and serves AD-like responses
- [ ] At least one tool successfully performs a DCSync against it
- [ ] Test user granted necessary rights and abuse demonstrated
- [ ] Output and artifacts captured and documented
