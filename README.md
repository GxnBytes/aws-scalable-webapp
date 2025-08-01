# 🚨 Threat Detection & Monitoring Lab  
![Status](https://img.shields.io/badge/status-In%20Development-yellow)

## 📝 Project Overview  
This project simulates a multi-VM enterprise infrastructure to explore **threat detection**, **monitoring**, and **incident response** in a controlled lab environment. It includes various Windows and Linux systems, integrated with security tools like **Wazuh**, **Security Onion**, and **MailHog**. The lab simulates real-world attack scenarios using offensive tools (e.g., **Hydra**, **Evil-WinRM**) to test detection capabilities and improve defensive strategies.

### Key Features:
- **Skynet**: Simulated enterprise environment with Windows-native systems.
- **Future Goals**:  
  - Build a **hybrid on-premise/cloud infrastructure**.
  - Expand the **SOC (Security Operations Centre)** and **Threat Detection** capabilities.
  - Develop a **dedicated Security Analysis Lab**.
  - Simulate various **cyber-attacks** for testing and training purposes.

---

## 💡 Skills Learned
- Security monitoring in a lab environment
- Configuring network traffic analysis tools
- Creating custom SIEM rules and alerts
- Investigating simulated security incidents
- Log collection, parsing, and analysis

---

## 📅 Project Phases

### [Phase 1: Enterprise Setup & Configuration](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%201%3A%20Home%20Lab%20Setup%20%26%20Configuration)
### [Phase 2: SIEM Alerts & Dashboards](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%202%3A%20SIEM%20Alerts%20%26%20Dashboards)
### [Phase 3: Incident Response & Analysis](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%203%3A%20Incident%20Response%20%26%20Analysis)

---

## 🖥️ Operating Systems
- **Windows Server 2025**: Central domain controller for enterprise services (DNS, DHCP, SSO).
- **Windows 11 Enterprise**: Simulates a corporate desktop environment.
- **Ubuntu Desktop 24.04**: Software development workstation for a Linux environment.
- **Security Onion**: Monitoring platform for intrusion detection and log analysis.
- **Ubuntu Server 24.04**: Hosts internal services like mail and databases.
- **Kali Linux**: Used for penetration testing and ethical hacking.

---

## 🛠️ Tools Used

### 🛡️ Defence Tools
- **Microsoft Active Directory**: Manages users, devices, and permissions.
- **Wazuh**: Intrusion detection and log monitoring.
- **MailHog**: Captures and tests outgoing emails in a controlled environment.

### ⚔️ Offensive Security Tools
- **Evil-WinRM**: Post-exploitation tool for Windows systems.
- **Hydra**: Brute-force tool for various protocols.
- **SecLists**: Curated wordlists for brute-forcing and exploitation.
- **NetExec**: Network exploitation tool for lateral movement.
- **XFreeRDP**: Remote access for post-exploitation.

---

## 🖥️ VM Specifications  

| VM Name               | OS                        | CPU / RAM   | Storage (Min) |
|-----------------------|---------------------------|-------------|---------------|
| `skynet-dc`           | Windows Server 2025       | 2 CPU / 4GB | 50 GB         |
| `skynet-win-client`   | Windows 10 Enterprise LTSC     | 2 CPU / 4GB | 80 GB         |
| `skynet-linux-client` | Ubuntu 22.04 Desktop      | 1 CPU / 3.5GB | 80 GB         |
| `skynet-sec-work`     | Security Onion            | 1 CPU / 2GB | 55 GB         |
| `skynet-sec-box`      | Ubuntu 22.04 Desktop      | 2 CPU / 4GB | 80 GB         |
| `skynet-corp-svr`     | Ubuntu Server 22.04       | 1 CPU / 2GB | 25 GB         |
| `skynet-attacker`     | Kali Linux 2024           | 1 CPU / 2GB | 55 GB         |

---

## 🔑 Accounts & Passwords

| Account                       | Password        | Host            |
|-------------------------------|-----------------|-----------------|
| `Administrator`                | Mr.Robot1       | ...-dc          |
| `johnd@corp.skynet-dc.com`     | @password123!    | ...-win-client  |
| `janed@linux-client`           | @password123!    | ...-linux-client|
| `skynet-sec-work`              | @password123!    | ...-sec-work    |
| `sec-work@sec-box`             | @password123!    | ...-sec-box     |
| `skynet-admin@corp-svr`        | @password123!    | ...-corp-svr    |
| `attacker@attacker`            | attacker        | attacker        |

---

## 🌐 Hosts

| Hostname                       | IP Address       | Function                             |
|---------------------------------|------------------|--------------------------------------|
| `skynet-dc` (corp.skynet-dc.com) | 10.0.0.5         | Domain Controller (DNS, DHCP, SSO)  |
| `skynet-admin`                 | 10.0.0.8         | Corporate Server                     |
| `skynet-sec-box`               | 10.0.0.10        | Security Server                      |
| `skynet-sec-work`              | 10.0.0.103 (or dynamic) | Security Testing Workstation     |
| `skynet-win-client`            | 10.0.0.100 (or dynamic) | Windows Workstation              |
| `skynet-linux-client`          | 10.0.0.101 (or dynamic) | Linux Workstation                 |
| `skynet-attacker`              | Dynamic          | Attacker VM                         |
