# Red Team Backlog

For all those backlog items/ideas that all/most Red Teams need to do :-)

send diffs with yours

## Questions
* Q. What's a spike? Ans. A short(ish) research task.
  
* Q. Why? Ans. I always fail to take my list of backlog items when I leave a place and I'm tired of trying to remember all of them. So now I'm crowdsourcing something for all Red Team managers/leads
  
* Q. Did ChatGPT make these?  Ans. A lot of of them with the main ideas coming from me and other Red Team leads. Inspect things closely for potential AI nonsense. Please create issues or diffs for stuff that doesn't make sense so I can update them.

* Q. I have an idea can I contribute? Ans. Absolutely we take diffs (use the template) or create an issue and someone will get around to updating the particular task.

## Contributors
carnal0wnage, 

Table of Contents
=================

# 🧑‍💻 Credential & Identity Abuse

- [ ] [Public Password Dump Analysis & Spraying](/tasks/research_spike_password_dump_analysis_&_cred.md)
- [ ] [Identify Sensitive Services That Don't Require MFA](/tasks/research_spike_mfa_gaps_services_access.md)  
- [ ] [Password Spraying O365 / Azure](/tasks/research_spike_password_spraying_office_365.md)
- [ ] [Password Spray Internal Applications](/tasks/password_spraying_internal_login.md)
- [ ] Credential Stuffing Against SaaS Apps (Google Workspace, Salesforce, Zoom) (NEEDS TEMPLATE)
- [ ] Session Token Replay Tests (NEEDS TEMPLATE)
- [ ] ADCS (Active Directory Certificate Services) Abuse (NEEDS TEMPLATE)
- [ ] Passwordless Auth Bypass Research (FIDO2/WebAuthn fallback handling) (NEEDS TEMPLATE)


# 🗝️ Secrets Managment

- [ ] [GitHub/Gitlab First Party Creds & Configs Discovery Tool](/tasks/github_gitlab_internal_dorking.md)
- [ ] [Run TruffleHog Against Internal git Repos](/tasks/enumerate_hardcoded_secrets.md)
- [ ] [Confluence/Jira Secret Scanning](/tasks/research_spike_search_confluence_jira_credentials.md)   
- [ ] [Searching Docker Images for Secrets](/tasks/research_spike_unpacking_docker_containers_for_secrets.md)  
- [ ] [Scan CI/CD Logs for Secrets](/tasks/scan_ci_logs_for_secrets.md)
- [ ] Explore Azure Key Vault or AWS Secrets Manager Misconfigurations
- [ ] Cloud Metadata API Abuse (IAM creds from EC2 metadata or GCP instance tokens) (NEEDS TEMPLATE)
- [ ] Hunting Secrets in Shared Cloud Storage (e.g., S3 buckets with shared links) (NEEDS TEMPLATE)
- [ ] Hardcoded Secrets in Mobile APKs or Electron Apps (NEEDS TEMPLATE)

# 🕸️ Web & Various Application Attack Surface

- [ ] [Forgotten Web Artifacts](/tasks/research_spike_forgotten_web_artifacts.md) 
- [ ] [Identify Debug Endpoints Web Surface (Debug, Metrics, Actuator, etc.)](/tasks/research_spike_debug_or_health_endpoints.md)  
- [ ] [GraphQL Attack Surface Enumeration](/tasks/research_spike_graphql_attack_surface_enumera.md)
- [ ] [GraphQL Subscriptions & WebSocket Abuse](/tasks/research_spike_graphql_subscriptions_&_websockets.md)
- [ ] [Federated Search Auth Bypass (Splunk/Elastic/M365)](/tasks/research_spike_federated_search_auth_bypass.md)  
- [ ] Dependency Confusion in Artifact Repos
- [ ] Identify Internal Software Libraries for Supply Chain Attack Risk 
- [ ] Audit CI/CD Pipelines for Misconfigurations & Abuse Paths
- [ ] Create Nuclei Scans + Custom Templates for Internal Apps
- [ ] Test for Secret Theft via CI Variables
- [ ] Test for Misuse of OAuth Refresh Tokens in M365/GWS
- [ ] Enumerate Overly Permissive OAuth Scopes
- [ ] Test for Open Redirects
- [ ] Research JWT Token Validation for Internal Apps
- [ ] Enumerate Misconfigured SaaS Webhooks (Slack, GitHub, Asana)
- [ ] Enumerate Apps with risky OAuth scopes
- [ ] Audit OAuth App Registrations in Azure / Google
- [ ] Browser Extension Security Review (NEEDS TEMPLATE)
- [ ] Exploitation of Misconfigured CSP / CORS Headers (NEEDS TEMPLATE)
- [ ] Testing for DOM-based XSS in Internal Apps (NEEDS TEMPLATE)
- [ ] gRPC Endpoint Enumeration and Fuzzing (NEEDS TEMPLATE)

# 🎣 Phishing & Social Engineering

- [ ] Phishing Pretext Template Pack (Internal Tools)  
- [ ] [Voice Deepfake for Helpdesk Abuse](/link)  
- [ ] [Automated Phishing Phone Trees](/tasks/research_spike_automated_phishing_phone_tree.md)  
- [ ] Office Macro Phish Payloads (MITRE-mapped)
- [ ] [Test Internal Email Filtering Rules](/tasks/test_internal_email_filtering.md)
- [ ] [Initial Access - Inovations](/tasks/initial_access_innovations.md)
- [ ] [Office Macro Malware](/tasks/research_spike_office_macro_malware.md)
- [ ] [Initial Access - Windows - Payload Generation (MSI)](/tasks/msi_payload_delivery.md)
- [ ] [Initial Access - Windows - Alternate Scripting Languages for Payload Delivery](/tasks/alternate_binary_payload_delivery.md)
- [ ] [Initial Access - macOS - Investigate Initial Access Options for the organization](/tasks/research_spike_top_10_initial_access_vectors_macOS.md)
- [ ] Create Malicious OAuth App for Phishing
- [ ] Abuse Jira/Confluence Macros or Web Panels for Payload Delivery
- [ ] Consent Phishing Simulation & Detection Evasion (NEEDS TEMPLATE)
- [ ] Targeted QR Code Phishing Pretext Design (NEEDS TEMPLATE)
- [ ] Compromised OAuth Token Refresh Lifecycle Analysis (NEEDS TEMPLATE)

# 🧱 Post-Exploitation & Privilege Escalation

- [ ] [Post-Exploitation Scripting for Password File Discovery(Windows)](/tasks/research_spike_post-exploitation_scripting_for_windows.md)
- [ ] [Post-Exploitation Scripting for Password File Discovery (Linux)](/tasks/research_spike_post-exploitation_scripting_for_linux.md)
- [ ] [Post-Exploitation Scripting for Password File Discovery (macOS)](/tasks/research_spike_post-exploitation_scripting_for_macOS.md)   
- [ ] Cross-Platform Secret Sniper Tool  
- [ ] [Living-Off-the-SaaS-Land (LOSL) TTP Library](/tasks/research_spike_living-off-the-saas-land.md)
- [ ] [Search Compromised Developers for Cloud Credentials](/tasks/token_harvest_from_cli_configs.md)
- [ ] [Tool to Audit Windows Developers for Privilege Escalation or RCE opportunities](/tasks/audit_windows_dev_tools.md)
- [ ] [Tool to Audit OSX Developers for Privilege Escalation or RCE opportunities](/tasks/audit_macos_dev_tools.md)
- [ ] Evaluate First Party Software Deployment Tools for Persistence or Privilege Escalation Opportunities
- [ ] Samba Server for Legitimate DCSync Attack Simulation
- [ ] Simulate a Malicious Insider with Developer Tool Access
- [ ] Create a Local Privilege Escalation Checklist Script for macOS
- [ ] Create an Internal Recon Script with SharpHound-lite Features
- [ ] [Write a Shell Script to Find Passwords on Linux and macOS](/tasks/find_passwords_shell_script.md)
- [ ] [Create a Fake Service to Capture Vulnerability Scanner Logins](/tasks/fake_service_credential_capture.md)
- [ ] [Write a Script to Auto-Pivot with SSH + Proxychains + Route Injection](/tasks/auto_pivot_with_ssh_proxychains.md)
- [ ] Abuse Misconfigured .npmrc, .pypirc, .dockerconfig Files
- [ ] Use of ADS (Alternate Data Streams) for File Hiding on Windows (NEEDS TEMPLATE)
- [ ] Abuse Windows Shadow Copies for Persistence / Recovery (NEEDS TEMPLATE)
- [ ] macOS TCC DB Tampering Scenarios (NEEDS TEMPLATE)
- [ ] macOS Shortcuts Automation Abuse (NEEDS TEMPLATE)

# 📌 Persistence
- [ ] [macOS - Agentless macOS Persistence](/tasks/research_spike_agentless_macos_persistence.md)
- [ ] [Windows - Enumerate Persistence Opportunities in Corporate Managed Devices](/tasks/enumerate_managed_device_persistence.md)
- [ ] Create a Malicious Outlook Add-in
- [ ] Create a Malicious IDE Plugin for Red Team Use
- [ ] Abuse Google Workspace OAuth Scopes to Persist & Read User Mail
- [ ] Browser-Based Persistence Mechanisms (NEEDS TEMPLATE)
- [ ] Persistence in WMI Subscriptions (NEEDS TEMPLATE)
- [ ] Slack or Teams Bot Persistence (NEEDS TEMPLATE)


# 🧰 Infrastructure Recon & Exploitation

- [ ] [NetBIOS/SMB Enumeration](/tasks/research_spike_enumerate_internal_smb.md)  
- [ ] [NFS Recon & Exploitation](/tasks/research_spike_nfs_share_enumeration_and_exploit.md)  
- [ ] [Layer 2 Attack Toolkit (ARP spoofing, LLMNR, DHCP, VLAN hops](/tasks/research_spike_common_layer_2_attacks.md))  
- [ ] [Printer Hacking & Lateral Movement](/tasks/research_spike_printer_hacking_and_lateral_movement.md)  
- [ ] IoT Fleet Pivoting (Printers, Cameras, AV gear)
- [ ] [Exposed Version Control Artifacts](/tasks/research_spike_exposed_version_control_artifacts.md)
- [ ] [Enumerate Internal Admin Portals](/tasks/research_spike_discovering_internal_admin_portals.md)
- [ ] Assessing Jira & Confluence Security
- [ ] IPv6-Only Network Reconnaissance (NEEDS TEMPLATE)
- [ ] Lateral Movement via Misconfigured Container Networking (NEEDS TEMPLATE)
- [ ] DNS Zone Transfer or Subdomain Takeover on Internal Services (NEEDS TEMPLATE)

# 🌩️ Cloud
- [ ] [AWS - PrivEsc via PMapper Analysis](/tasks/research_spike_aws_privilege_escalation.md)
- [ ] Exploit Secrets in Downstream Services (Containers, Lambda, etc.)
- [ ] Cloud Function Abuse for Callback Persistence (e.g., AWS Lambda, GCP Cloud Functions) (NEEDS TEMPLATE)
- [ ] CloudTrail or GCP Audit Log Evasion Techniques (NEEDS TEMPLATE)
- [ ] Analysis of Org-Wide Roles vs. Project Roles in GCP (NEEDS TEMPLATE)
- [ ] Azure Automation Account Abuse (NEEDS TEMPLATE)
- [ ] Storage Bucket (S3/GCS) Policy Bypass Tactics (NEEDS TEMPLATE)


# 📡 Red Team Infrastructure, C2, & Payload Engineering

- [ ] [C2 Infrastructure Basics (Mythic / Sliver)](/tasks/research_spike_c2_infrastructure_basics.md)  
- [ ] [Advanced Payload Obfuscation & Packers](/tasks/research_spike_advanced_payload_obfuscation_and_packers.md)
- [ ] [Custom C2 Channel Development](/tasks/research_spike_custom_c2_channel_development.md)
- [ ] [Create Virtual Macines of Corporate Builds for testing](/tasks/create_corp_os_vms.md)
- [ ] Create terraform/ansible scripts for attack box builds
- [ ] [Create a Long-Term Stealth C2 Using Legit Cloud Channels](/tasks/stealth_cloud_c2.md)
- [ ] Create a New C2 Channel for Mythic
- [ ] Create a Sliver or Mythic Profile Mimicking Corporate TLS Patterns
- [ ] Side-Loading Legitimate DLLs for C2 Execution (NEEDS TEMPLATE)
- [ ] Malicious Container Image for Initial Access or Persistence (NEEDS TEMPLATE)
- [ ] Use of AI Model APIs (e.g., GPT, Claude) as C2 Channels (NEEDS TEMPLATE)

# 🔐 Physical Security / RF / Access Control

- [ ] Physical Access Audit Starter Kit  
- [ ] USB Drop Research (OMG Cable, lure docs)
- [ ] [RFID Relay Attacks via BLE / Wi-Fi (Badge Replay)](/tasks/research_spike_rfid_relay_attacks.md)
- [ ] [Rogue USB-C Dock (Video+KVM+LAN)](/tasks/research_spike_rogue_usb-c_multi-function_implant.md)  
- [ ] [Long-Range RFID Cloner](/tasks/research_spike_long-range_rfid_badge_capture.md)  
- [ ] [Mobile Wallet Application vs. Prox Badge Clone & Replay](/tasks/research_spike_enterprise_badge_clone_vs_mobile_auth.md)  
- [ ] [Unencrypted RF Eavesdropping (Radios, BLE, mics)](/tasks/research_spike_rf_recon.md)
- [ ] Signal Analysis of Mobile Credential BLE Advertisements (NEEDS TEMPLATE)
- [ ] Attack Scenarios Against Modern Smart Locks (NEEDS TEMPLATE)
- [ ] Malicious Firmware Analysis for HID Reader Clones (NEEDS TEMPLATE)

# 🧪 Vuln Management & Signal Prioritization
 
- [ ] [Chaining Low Vulns for Elevated Access (Low2Pwned) - Quarterly](/tasks/research_spike_chaining_low_vulns_into_pwned_things.md)
- [ ] Weaponize a Poc exploit for services/applications the company uses (NEEDS TEMPLATE)

# 🧬 Custom Tooling & Automation

- [ ] Git Secret Scanner Tool  
- [ ] Teams/Confluence/Jira Credential Recon  
- [ ] CI/CD Scan Rule Development
- [ ] [Tool - GitHub/GitLab Secret Discovery](/tasks/research_spike_github-gitlab_secret_search_to.md)
- [ ] Tool to Auto-Correlate Secrets Found Across Logs, Containers, Git (NEEDS TEMPLATE)
- [ ] Browser Extension to Help Red Teamers Enumerate Apps (NEEDS TEMPLATE)
- [ ] Malware Config Extractor Tool for Internal Threat Intel (NEEDS TEMPLATE)
- [ ] 

# 📘 Documentation & Reporting

- [ ] Update Team Wiki
- [ ] Update $Process SOP or Wiki
- [ ] Create Vulnerability Trends from Past Pentests and Red Team Operations
- [ ] Document Alert Evasion Patterns for Repeat Testing (NEEDS TEMPLATE)
