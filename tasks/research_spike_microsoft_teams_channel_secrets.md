# 💬 Research Spike: Microsoft Teams Channel Secret Discovery

**Goal:**  
Create a script or automation pipeline to identify exposed credentials, secrets, and API tokens shared in Microsoft Teams channels — including public team channels, shared files, and pasted chat content.

**Why It Matters:**  
Teams often becomes an unofficial helpdesk, deployment diary, or backchannel — which means credentials, passwords, and secrets are frequently pasted without awareness of retention or searchability. These leaks often persist for years and are accessible via delegated or misconfigured permissions.

---

### ✅ Tasks

- [ ] Authenticate to Teams API (Graph API or delegated token)
- [ ] Enumerate:
  - Teams > Channels > Messages
  - Files shared in chat (`driveItem` links)
- [ ] Search message bodies, filenames, and attachments for:
  - Patterns like `password=`, `token:`, `api_key`, `secret=`
  - High-entropy strings (e.g., JWTs, AWS keys)
- [ ] Optional:
  - Score risk by user type (admin vs. intern)
  - Flag secrets pasted in large channels (>X members)

---

### 🎯 Deliverables

- Script/tool: `teams-sniffer.py` or PowerShell module  
- Output: CSV or JSON with message ID, user, snippet, timestamp  
- Redacted example results  
- Regex library for Teams message scanning  
- Recommendations:
  - Block pasting of credentials in sensitive Teams spaces
  - Auto-expire shared secrets in chat history
  - Educate users on safe credential handling

---

### 📚 References

- Microsoft Graph API – [List Channel Messages](https://learn.microsoft.com/en-us/graph/api/channel-list-messages)  
- [Teams message retention docs](https://learn.microsoft.com/en-us/microsoftteams/retention-policies)  
- MITRE ATT&CK T1552.001 – Credentials in Files  
- Entropy detection: truffleHog, gitleaks regexes

---

### 🏷️ Tags

`teams` `microsoft365` `secrets` `chat-recon` `graph-api` `token-leakage` `t1552.001` `office365` `internal-comms` `post-access`

---

### 📈 Effort Level

**Medium (M)** — requires Microsoft Graph API knowledge and secure auth context (App Registration or delegated user token).

---

### ✅ Acceptance Criteria

- [ ] Script authenticates and extracts messages from Teams  
- [ ] At least 5 redacted test secrets identified  
- [ ] Output includes user, team, channel, and timestamp  
- [ ] False-positive filter logic added (e.g., ignore bot tokens)  
- [ ] Tool or script documented and shared internally