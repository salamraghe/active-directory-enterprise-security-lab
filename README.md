# Active Directory Enterprise Security Lab

## Overview
Built a multi-VM enterprise cybersecurity lab in Oracle VM VirtualBox to practice Active Directory administration, identity and access fundamentals, Windows and Linux system management, network configuration, log monitoring, and security troubleshooting.

## Why This Project Matters
This project was built to simulate a real enterprise environment and strengthen hands-on skills in system deployment, identity infrastructure, endpoint setup, network configuration, and technical troubleshooting. It demonstrates practical experience with technologies commonly used in enterprise IT, IAM, PAM, and cybersecurity environments.

## Project Purpose
The goal of this lab is to build and document a working enterprise-style environment using multiple virtual machines. The project covers Windows and Linux administration, Active Directory setup and management, SIEM deployment, endpoint monitoring, attack simulation, and log analysis — providing end-to-end exposure to the tools and workflows used in real cybersecurity and IAM roles.

---

## Environment

### Virtual Machines
| VM Name | OS | Role |
|---|---|---|
| ADDC01 | Windows Server 2022 | Domain Controller |
| TARGET-PC | Windows 10 Pro | Endpoint / Target Machine |
| Splunk | Ubuntu Server 22.04.4 LTS | SIEM Host |
| Kali | Kali Linux | Attacker / Testing Machine |

### Network Configuration
- NAT Network: `192.168.10.0/24`
- ADDC01 (Domain Controller): `192.168.10.7`
- TARGET-PC (Endpoint): `192.168.10.100`
- Splunk Server: `192.168.10.10`
- Kali Linux (Attacker): `192.168.10.250`

### Lab Hardware Specs
- **ADDC01** — 4096 MB RAM, 1 CPU, 50 GB disk
- **TARGET-PC** — 4096 MB RAM, 1 CPU, 50 GB disk
- **Splunk** — 8192 MB RAM, 2 CPUs, 100 GB disk
- **Kali** — Imported Kali Linux VirtualBox image

---

## Tools Used
- Oracle VM VirtualBox
- Windows Server 2022
- Windows 10 Pro
- Ubuntu Server 22.04.4 LTS
- Kali Linux
- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- Crowbar
- Atomic Red Team (ART)
- PowerShell

---

## Core Skills Demonstrated
- Virtual machine deployment and management across multiple OS platforms
- Windows Server 2022 installation and administration
- Windows 10 Pro endpoint deployment
- Ubuntu Server installation and Linux troubleshooting
- NAT network configuration and static IP assignment
- Splunk Enterprise deployment and SIEM configuration
- Splunk Universal Forwarder setup for endpoint log collection
- Sysmon deployment for Windows endpoint telemetry
- Active Directory Domain Services setup and domain controller promotion
- Organizational Unit and user account management in Active Directory
- Joining Windows endpoints to an Active Directory domain
- Brute force attack simulation using Crowbar over RDP
- Security log analysis in Splunk (Event IDs 4624, 4625)
- Adversary simulation using Atomic Red Team
- Detection gap identification through purple team testing
- PowerShell scripting and automation
- ISO mounting, boot troubleshooting, and OS recovery workflows
- Patch management on Linux (apt update/upgrade)

---

## Lab Progress

| Phase | Description | Status |
|---|---|---|
| Phase 1 | VM Installation & Environment Setup | ✅ Completed |
| Phase 2 | Network Configuration & SIEM Deployment | 🔄 In Progress |
| Phase 3 | Active Directory & Domain Configuration | ⏳ Upcoming |
| Phase 4 | Attack Simulation & Log Analysis | ⏳ Upcoming |

---

## Phase 1 — VM Installation ✅

### Oracle VM VirtualBox Setup
Installed Oracle VM VirtualBox and prepared the lab environment for multi-VM deployment.

### Windows Server 2022 (`ADDC01`)
- Created a Windows Server VM with 4096 MB RAM, 1 CPU, and 50 GB storage
- Installed Windows Server 2022 Standard Evaluation (Desktop Experience)
- Resolved an installation issue caused by incorrect unattended optical media by manually attaching the correct ISO
- Verified successful boot to Server Manager

### Windows 10 Pro (`TARGET-PC`)
- Created a Windows 10 VM with 4096 MB RAM, 1 CPU, and 50 GB storage
- Corrected an issue where the wrong Windows 11 ISO was mounted
- Installed Windows 10 Pro successfully
- Verified successful boot to the Windows desktop

### Kali Linux
- Imported the Kali Linux VirtualBox image
- Verified successful boot to the Kali desktop

### Ubuntu Server (`Splunk`)
- Created an Ubuntu Server VM with 8192 MB RAM, 2 CPUs, and 100 GB storage
- Installed Ubuntu Server 22.04.4 LTS
- Resolved an authentication issue by resetting the user password in recovery mode
- Verified successful login to the terminal
- Applied system updates:

```bash
sudo apt-get update && sudo apt-get upgrade -y
```

📸 [Screenshots — Phase 1](screenshots/phase-1-environment-setup/)

---

## Phase 2 — Network Configuration & SIEM Deployment 🔄
> In Progress — documentation will be added upon completion

**Planned work for this phase:**
- Configure NAT Network in VirtualBox and assign static IPs to all VMs
- Set static IP on Ubuntu Server and verify connectivity to network
- Deploy Splunk Enterprise on Ubuntu Server
- Configure Splunk receiving port (9997) and create endpoint index
- Install Splunk Universal Forwarder on Windows Server and Windows 10
- Deploy Sysmon on both Windows machines using sysmon-modular config
- Configure inputs.conf to forward Application, Security, System, and Sysmon logs
- Verify both endpoints (TARGET-PC and ADDC01) appear in Splunk under index=endpoint

---

## Phase 3 — Active Directory & Domain Configuration ⏳
> Upcoming — documentation will be added upon completion

**Planned work for this phase:**
- Install Active Directory Domain Services role on Windows Server (ADDC01)
- Promote ADDC01 to domain controller and create domain `demodomain.local`
- Create Organizational Units (IT, HR) in Active Directory Users and Computers
- Create and manage user accounts within each OU
- Configure TARGET-PC DNS to point to domain controller at `192.168.10.7`
- Join Windows 10 endpoint to `demodomain.local` domain
- Verify domain login using created user accounts
- Enable Remote Desktop on TARGET-PC for domain users

---

## Phase 4 — Attack Simulation & Log Analysis ⏳
> Upcoming — documentation will be added upon completion

**Planned work for this phase:**
- Configure Kali Linux static IP and verify lab network connectivity
- Install Crowbar and prepare password wordlist from rockyou.txt
- Execute RDP brute force attack against TARGET-PC domain user account
- Analyze attack telemetry in Splunk — Event ID 4625 (failed logon) and 4624 (successful logon)
- Identify brute force pattern from log timestamps and volume in Splunk
- Deploy Atomic Red Team framework on TARGET-PC
- Execute persistence and lateral movement test cases (e.g., T1136.001)
- Identify detection gaps using Splunk and document findings

---

*Lab actively in progress — each phase will be updated with full documentation and screenshots upon completion.*
