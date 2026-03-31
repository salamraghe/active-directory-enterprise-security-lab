# Active Directory Enterprise Security Lab

## Overview
Built a multi-VM enterprise cybersecurity lab in Oracle VM VirtualBox to practice Active Directory administration, identity and access fundamentals, Windows and Linux system management, network configuration, log monitoring, and security troubleshooting.

## Why This Project Matters
This project was built to simulate a small enterprise environment and strengthen hands-on skills in system deployment, identity infrastructure, endpoint setup, network configuration, and technical troubleshooting. It demonstrates practical experience with technologies commonly used in enterprise IT, IAM, and cybersecurity environments.

## Project Purpose
The goal of this lab is to build and document a working enterprise-style environment using multiple virtual machines. The project is designed to strengthen hands-on experience with Windows and Linux administration, Active Directory preparation, endpoint setup, security tooling, and troubleshooting across interconnected systems.

## Environment

### Virtual Machines
- **ADDC01** — Windows Server 2022
- **TARGET-PC** — Windows 10 Pro
- **Splunk** — Ubuntu Server 22.04.4 LTS
- **Kali** — Kali Linux

## Architecture
- **ADDC01** — Windows Server 2022 domain controller
- **TARGET-PC** — Windows 10 endpoint
- **Splunk** — Ubuntu Server intended for Splunk Enterprise
- **Kali** — Attacker and testing machine

## Lab Configuration
- **ADDC01** — 4096 MB RAM, 1 CPU, 50 GB disk
- **TARGET-PC** — 4096 MB RAM, 1 CPU, 50 GB disk
- **Splunk** — 8192 MB RAM, 2 CPUs, 100 GB disk
- **Kali** — Imported Kali Linux VirtualBox image

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
- Atomic Red Team

## Core Skills Demonstrated
- Virtual machine deployment and management
- Windows Server installation and administration
- Windows 10 endpoint deployment
- Ubuntu Server installation and Linux troubleshooting
- ISO mounting, boot troubleshooting, and recovery workflows
- Multi-system troubleshooting in a virtual enterprise lab
- Preparation for Active Directory, networking, logging, and security monitoring workflows

## Phase 1 — VM Installation

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
- Resolved an Ubuntu authentication issue by resetting the user password in recovery mode
- Verified successful login to the terminal
- Updated the system with:

```bash
sudo apt-get update && sudo apt-get upgrade -y
