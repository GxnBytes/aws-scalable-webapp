# 🚨 Threat Detection & Monitoring Lab 
![Status](https://img.shields.io/badge/status-In%20Development-yellow)

## Project Overview
This project is a multi-VM cyber security lab designed to simulate enterprise infrastructure and explore threat detection, monitoring, and incident response in a controlled environment.

The lab includes Windows and Linux systems running Active Directory, Wazuh, Security Onion, and MailHog. Realistic attack scenarios are simulated using offensive tools such as Hydra, Evil-WinRM, NetExec, and XFreeRDP to test detection capabilities. Custom SIEM rules and alerts are developed to identify brute-force attempts, privilege escalation, and lateral movement. Logs are analysed, and incidents documented to improve blue team techniques and defensive visibility.
<br>

## Skills Learned
- Gained hands-on experience in security monitoring within a lab environment
- Configured and deployed network traffic analysis tools
- Created alerts and rules for detecting suspicious activity
- Investigated simulated security incidents and developed response procedures
- Explored log collection, parsing, and analysis for threat detection and insights

## Project Phases

### [Phase 1: Home Lab Setup & Configuration](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%201%3A%20Home%20Lab%20Setup%20%26%20Configuration)
### [Phase 2: SIEM Alerts & Dashboards](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%202%3A%20SIEM%20Alerts%20%26%20Dashboards)
### [Phase 3: Incident Response & Analysis](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%203%3A%20Incident%20Response%20%26%20Analysis)
<br>

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
