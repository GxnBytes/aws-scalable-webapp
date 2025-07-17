# 🚨 Threat Detection & Monitoring Lab 
![Status](https://img.shields.io/badge/status-In%20Development-yellow)

## Project Overview
This project is a multi-VM cyber security lab designed to simulate enterprise infrastructure and explore threat detection, monitoring, and incident response in a controlled environment.

The lab includes Windows and Linux systems running Active Directory, Wazuh, Security Onion, and MailHog. Realistic attack scenarios are simulated using offensive tools such as Hydra, Evil-WinRM, NetExec, and XFreeRDP to test detection capabilities. Custom SIEM rules and alerts are developed to identify brute-force attempts, privilege escalation, and lateral movement. Logs are analysed, and incidents documented to improve blue team techniques and defensive visibility.
<br>
<br>
## Skills Learned
- Gained hands-on experience in security monitoring within a lab environment
- Configured and deployed network traffic analysis tools
- Created alerts and rules for detecting suspicious activity
- Investigated simulated security incidents and developed response procedures
- Explored log collection, parsing, and analysis for threat detection and insights
<br>

<!--
### Network Topologies
📸 ![Network Topologies](screenshots/network_topologies.png)
-->
## 🖥️ Operating Systems
- **Windows Server 2025**  
  Enterprise-grade OS for directory services and identity management. Serves as the central domain controller for network authentication and connectivity.

- **Windows 11 Enterprise**  
  Business-focused desktop OS optimized for productivity. Used to simulate a typical corporate end-user environment.
- **Ubuntu Desktop 24.04**  
  Versatile Linux desktop, ideal for development workflows. Simulates a software development workstation in an enterprise setting.
- **Security Onion**  
  Open-source platform for threat detection, log analysis, and intrusion detection. Used for monitoring and responding to network security events.
- **Ubuntu Server 24.04**  
  Reliable server OS for hosting services like mail, databases, and web applications. Deployed as the internal email server.
- **Kali Linux**  
  Penetration testing and ethical hacking distro. Equipped with tools for vulnerability scanning, exploitation, and digital forensics.
<br>


## ⚙️ Virtual Machines (VMs)

For virtualization, either **VirtualBox** or **VMware Workstation Pro** can be used as the hypervisor.

Below are the specifications for each virtual machine. These are important for setup:

| VM Name             | Operating System        | Specs           | Storage (Minimum) |
|---------------------|------------------------|-----------------|-------------------|
| `skynet-dc`      | Windows Server 2025    | 2 CPU / 4096 MB | 50 GB             |
| `skynet-win-client` | Windows 11 Enterprise | 2 CPU / 4096 MB | 80 GB             |
| `skynet-linux-client` | Ubuntu 24.04 Desktop  | 1 CPU / 2048 MB | 80 GB             |
| `skynet-sec-work` | Security Onion          | 1 CPU / 2048 MB | 55 GB             |
| `skynet-sec-box`  | Ubuntu 24.04 Desktop    | 2 CPU / 4096 MB | 80 GB             |
| `skynet-corp-svr` | Ubuntu Server 24.04     | 1 CPU / 2048 MB | 25 GB             |
| `skynet-attacker` | Kali Linux 2024       | 1 CPU / 2048 MB | 55 GB             |

## Hosts

| Hostname \[`skynet-…`\]           | IP Address                 | Function                              |
|--------------------------------------|-----------------------------|----------------------------------------|
| -dc (corp.skynet-dc.com)          | 10.0.0.5                   | Domain Controller (DNS, DHCP, SSO)     |
| -admin                               | 10.0.0.8                   | Corporate Server                        |
| -sec-box                             | 10.0.0.10                  | Dedicated Security Server              |
| -sec-work                            | 10.0.0.103 or (dynamic)    | Security Playground                    |
| -win-client                          | 10.0.0.100 or (dynamic)    | Windows Workstation                    |
| -linux-client                        | 10.0.0.101 or (dynamic)    | Linux Desktop Workstation             |
| attacker                             | dynamic                    | Attacker Environment                   |


## Accounts & Passwords

| Account                              | Password        | Host            |
|--------------------------------------|-----------------|-----------------|
| Administrator                        | password123!    | ...-dc          |
| John Doe          | password123!   | ...-win-client  |
| janed@linux-client                   | password123!   | ...-linux-client|
| skynet-sec-work                   | password123!   | ...-sec-work    |
| sec-work@sec-box                     | password123!   | ...-sec-box     |
| skynet-admin@corp-svr            | password123!   | ...-corp-svr    |
| attacker@attacker                   | attacker         | attacker        |
<br>

## 🛠️ Tools Used
  **🛡️ Enterprise Tools & Defense**
- **Microsoft Active Directory**  
  Centralized directory service for managing users, devices, and permissions in a Windows-based network environment.
- **Wazuh**  
  Open-source security platform offering intrusion detection, log monitoring, vulnerability detection, and compliance reporting.
- **MailHog**  
  Lightweight email testing tool that captures outgoing messages via a fake SMTP server. Emails are viewable through a web UI or API, without sending to real inboxes.

**⚔️ Offensive Security Tools**
- **Evil-WinRM**  
  Ruby-based WinRM client used for post-exploitation on Windows systems. Supports remote command execution and data extraction.
- **Hydra**  
  Fast, flexible tool for brute-force and dictionary attacks across various network services like SSH, HTTP, and FTP.
- **SecLists**  
  Curated collection of wordlists and payloads used during reconnaissance, brute-forcing, and exploitation stages.
- **NetExec**  
  Network exploitation tool that enables remote command execution via multiple protocols, aiding lateral movement and privilege escalation.
- **XFreeRDP**  
  Open-source RDP client used to remotely access and control Windows machines for recon and post-exploitation activities.
<br>


## Project Phases

### [Phase 1: Home Lab Setup & Configuration](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%201%3A%20Home%20Lab%20Setup%20%26%20Configuration)
### Phase 2: SIEM Alerts & Dashboards
### Phase 3: Incident Response & Analysis
<br>

## Challenges
*To be documented*

## Attack Simulations & Results
*To be documented*
