# Red Team Backlog

For all those backlog items/ideas that all red teams need to do :-)

send diffs with yours

## Questions
* Q. What's a spike? A. A short(ish) research task
* 

Table of Contents
=================

# 🧑‍💻 Credential & Identity Abuse

- [ ] [Public Password Dump Analysis & Spraying](/tasks/research_spike_password_dump_analysis_&_cred.md)
- [ ] [Identify Sensitive Services That Don't Require MFA](/tasks/research_spike_mfa_gaps_services_access.md)  
- [ ] [Password Spraying O365 / Azure](/tasks/research_spike_password_spraying_office_365.md)
- [ ] [Password Spray Internal Applications](/tasks/password_spraying_internal_login.md)


# 🗝️ Secrets Managment

- [ ] [GitHub/Gitlab First Party Creds & Configs Discovery Tool](/tasks/github_gitlab_internal_dorking.md)
- [ ] [Run TruffleHog Against Internal git Repos](/tasks/enumerate_hardcoded_secrets.md)
- [ ] [Confluence/Jira Secret Scanning](/tasks/research_spike_search_confluence_jira_credentials.md)   
- [ ] [Searching Docker Images for Secrets](/tasks/research_spike_unpacking_docker_containers_for_secrets.md)  
- [ ] Enumerate Misconfigured SaaS Webhooks (Slack, GitHub, Asana)
- [ ] [Scan CI/CD Logs for Secrets](/tasks/scan_ci_logs_for_secrets.md)

# 🕸️ Web & Various Application Attack Surface

- [ ] [Forgotten Web Artifacts](/tasks/research_spike_forgotten_web_artifacts.md) 
- [ ] [Identify Debug Endpoints Web Surface (Debug, Metrics, Actuator, etc.)](/tasks/research_spike_debug_or_health_endpoints.md)  
- [ ] [GraphQL Attack Surface Enumeration](/tasks/research_spike_graphql_attack_surface_enumera.md)  
- [ ] [Federated Search Auth Bypass (Splunk/Elastic/M365)](/tasks/research_spike_federated_search_auth_bypass.md)  
- [ ] Dependency Confusion in Artifact Repos  
- [ ] CI/CD Misconfig Scanning (via Nuclei)  

# 🎣 Phishing & Social Engineering

- [ ] Phishing Pretext Template Pack (Internal Tools)  
- [ ] Voice Deepfake for Helpdesk Abuse  
- [ ] Automated Phishing Phone Trees  
- [ ] Office Macro Phish Payloads (MITRE-mapped)
- [ ] [Initial Access - Inovations](/tasks/initial_access_innovations.md)
- [ ] [Office Macro Malware](/tasks/research_spike_office_macro_malware.md)
- [ ] [Initial Access - Windows - Payload Generation (MSI)](/tasks/msi_payload_delivery.md)
- [ ] [Initial Access - Windows - Alternate Scripting Languages for Payload Delivery](/tasks/alternate_binary_payload_delivery.md)

# 🧱 Post-Exploitation & Privilege Escalation

- [ ] Post-Ex Secret Hunt (Windows/Linux/macOS)   
- [ ] Cross-Platform Secret Sniper Tool  
- [ ] [Living-Off-the-SaaS-Land (LOSL) TTP Library](/tasks/research_spike_living-off-the-saas-land.md)
- [ ] [Search Compromised Developers for Cloud Credentials](/tasks/token_harvest_from_cli_configs.md)
- [ ] [Tool to Audit Windows Developers for Privilege Escalation or RCE opportunities](/tasks/audit_windows_dev_tools.md)
- [ ] [Tool to Audit OSX Developers for Privilege Escalation or RCE opportunities](/tasks/audit_macos_dev_tools.md)
- [ ] Evaluate First Party Software Deployment Tools for Persistence or Privilege Escalation Opportunities

# 📌 Persistence
- [ ] [macOS - Agentless macOS Persistence](/tasks/research_spike_agentless_macos_persistence.md)
- [ ] [Windows - Enumerate Persistence Opportunities in Corporate Managed Devices](/tasks/enumerate_managed_device_persistence.md) 


# 🧰 Infrastructure Recon & Exploitation

- [ ] [NetBIOS/SMB Enumeration](/tasks/research_spike_enumerate_internal_smb.md)  
- [ ] [NFS Recon & Exploitation](/tasks/research_spike_nfs_share_enumeration_and_exploit.md)  
- [ ] Layer 2 Attack Toolkit (ARP spoofing, LLMNR, DHCP, VLAN hops)  
- [ ] [Printer Hacking & Lateral Movement](/tasks/research_spike_printer_hacking_and_lateral_movement.md)  
- [ ] IoT Fleet Pivoting (Printers, Cameras, AV gear)
- [ ] [Exposed Version Control Artifacts](/tasks/research_spike_exposed_version_control_artifacts.md)
- [ ] [Enumerate Internal Admin Portals](/tasks/research_spike_discovering_internal_admin_portals.md)

# 🌩️ Cloud
- [ ] [AWS - PrivEsc via PMapper Analysis](/tasks/research_spike_aws_privilege_escalation.md)

# 📡 Red Team Infrastructure, C2, & Payload Engineering

- [ ] [C2 Infrastructure Basics (Mythic / Sliver)](/tasks/research_spike_c2_infrastructure_basics.md)  
- [ ] [Advanced Payload Obfuscation & Packers](/tasks/research_spike_advanced_payload_obfuscation_and_packers.md)
- [ ] [Custom C2 Channel Development](/tasks/research_spike_custom_c2_channel_development.md)
- [ ] [Create Virtual Macines of Corporate Builds for testing](/tasks/create_corp_os_vms.md)
- [ ] Create terraform/ansible scripts for attack box builds
- [ ] [Create a Long-Term Stealth C2 Using Legit Cloud Channels](/tasks/stealth_cloud_c2.md)
- [ ] Create a New C2 Channel for Mythic

# 🔐 Physical Security / RF / Access Control

- [ ] Physical Access Audit Starter Kit  
- [ ] USB Drop Research (OMG Cable, lure docs)  
- [ ] [Rogue USB-C Dock (Video+KVM+LAN)](/tasks/research_spike_rogue_usb-c_multi-function_implant.md)  
- [ ] [Long-Range RFID Cloner](/tasks/research_spike_long-range_rfid_badge_capture.md)  
- [ ] [Mobile Wallet Application vs. Prox Badge Clone & Replay](/tasks/research_spike_enterprise_badge_clone_vs_mobile_auth.md)  
- [ ] [Unencrypted RF Eavesdropping (Radios, BLE, mics)](/tasks/research_spike_rf_recon.md)  

# 🧪 Vuln Management & Signal Prioritization
 
- [ ] [Chaining Low Vulns for Elevated Access (Low2Pwned) - Quarterly](/tasks/research_spike_chaining_low_vulns_into_pwned_things.md)  

# 🧬 Custom Tooling & Automation

- [ ] Git Secret Scanner Tool  
- [ ] Teams/Confluence/Jira Credential Recon  
- [ ] GraphQL Fuzzing + Custom Queries  
- [ ] CI/CD Scan Rule Development
- [ ] [Tool - GitHub/GitLab Secret Discovery](/tasks/research_spike_github-gitlab_secret_search_to.md)

# 📘 Documentation & Reporting

- [ ] Update Team Wiki
- [ ] Update $Process SOP or Wiki
- [ ] Create Vulnerability Trends from Past Pentests and Red Team Operations
- [ ] TODO


