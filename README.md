# 🚨 Threat Detection & Monitoring Lab  
![Status](https://img.shields.io/badge/status-In%20Development-yellow)

## 📝 Project Overview  
This project simulates a multi-VM enterprise environment to explore **threat detection**, **monitoring**, and **incident response** in a controlled lab setting.  

The lab integrates Windows and Linux systems with security tools such as **Wazuh**, **Security Onion**, and **MailHog**. Offensive security tools (e.g., **Hydra**, **Evil-WinRM**) are used to simulate real-world attacks, allowing detection and defence strategies to be tested and refined.  

### Key Features
- **Skynet**: A simulated enterprise network with Windows- and Linux-based systems.  
- **Future Goals**:  
  - Expand to a **hybrid on-premise/cloud infrastructure**.  
  - Enhance the **SOC (Security Operations Centre)** and detection capabilities.  
  - Build a dedicated **Security Analysis Lab**.  
  - Simulate a variety of **cyber attacks** for training and research.  

---

## 💡 Skills Developed
- Security monitoring and detection in a lab environment.  
- Configuring and tuning network traffic analysis tools.  
- Creating custom SIEM rules and alerts.  
- Investigating and responding to simulated incidents.  
- Collecting, parsing, and analysing logs.  

---

## 📅 Project Phases

- [**Phase 1: Enterprise Setup & Configuration**](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%201%3A%20Enterprise%20Setup%20%26%20Configuration)  
- [**Phase 2: SIEM Dashboards & Alerts**](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%202%3A%20SIEM%20Alerts%20%26%20Dashboards)  
- [**Phase 3: Incident Response & Analysis**](https://github.com/Genvarelli/Threat-Detection-Monitoring-Lab/tree/main/Phase%203%3A%20Incident%20Response%20%26%20Analysis)  

---

## 🖥️ Operating Systems
- **Windows Server 2025** – Domain Controller providing DNS, DHCP, and SSO.  
- **Windows 10 Enterprise LTSC** – Simulated corporate endpoint.  
- **Ubuntu 22.04 Desktop** – Linux workstation for end-user simulation.  
- **Security Onion** – IDS/IPS and log monitoring platform.  
- **Ubuntu 22.04 Server** – Hosts corporate services (mail, web, file share).  
- **Kali Linux** – Adversary simulation and penetration testing.  

---

## 🛠️ Tools Used

### 🛡️ Defensive
- **Microsoft Active Directory** – User, device, and policy management.  
- **Wazuh** – Intrusion detection and log monitoring.  
- **MailHog** – Safe testing of outbound email delivery.  

### ⚔️ Offensive
- **Evil-WinRM** – Post-exploitation framework for Windows targets.  
- **Hydra** – Password brute-force across multiple protocols.  
- **SecLists** – Wordlists for password cracking and fuzzing.  
- **NetExec** – Network exploitation and lateral movement.  
- **XFreeRDP** – Remote desktop access for post-exploitation.  

---

## 🖥️ VM Specifications  

| VM Name               | OS                        | CPU / RAM     | Storage |
|-----------------------|---------------------------|---------------|---------|
| `skynet-dc`           | Windows Server 2025       | 2 vCPU / 4GB  | 50 GB   |
| `skynet-win-client`   | Windows 10 Enterprise LTSC| 2 vCPU / 4GB  | 80 GB   |
| `skynet-linux-client` | Ubuntu 22.04 Desktop      | 1 vCPU / 3.5GB| 80 GB   |
| `skynet-sec-work`     | Security Onion            | 1 vCPU / 2GB  | 55 GB   |
| `skynet-sec-box`      | Ubuntu 22.04 Desktop      | 2 vCPU / 4GB  | 80 GB   |
| `skynet-corp-svr`     | Ubuntu 22.04 Server       | 1 vCPU / 2GB  | 25 GB   |
| `skynet-attacker`     | Kali Linux                | 4 vCPU / 2GB  | 80 GB   |

---

## 🔑 Accounts & Passwords  

| Account                       | Password       | Host             |
|-------------------------------|----------------|------------------|
| `Administrator`               | Mr.Robot1      | skynet-dc        |
| `johnd@corp.skynet-dc.com`    | @password123!  | skynet-win-client|
| `janed@linux-client`          | @password123!  | skynet-linux-client|
| `skynet-sec-work`             | @password123!  | skynet-sec-work  |
| `sec-work@sec-box`            | @password123!  | skynet-sec-box   |
| `skynet-admin@corp-svr`       | @password123!  | skynet-corp-svr  |
| `attacker@attacker`           | kali           | skynet-attacker  |

---

## 🌐 Hosts  

| Hostname                        | IP Address         | Role                                |
|---------------------------------|--------------------|-------------------------------------|
| `skynet-dc` (corp.skynet-dc.com)| 10.0.0.5           | Domain Controller (DNS, DHCP, SSO) |
| `skynet-admin`                  | 10.0.0.8           | Corporate Server                   |
| `skynet-sec-box`                | 10.0.0.10          | Security Analysis Workstation      |
| `skynet-sec-work`               | 10.0.0.103 (DHCP)  | Security Onion                     |
| `skynet-win-client`             | 10.0.0.100 (DHCP)  | Windows Client Endpoint            |
| `skynet-linux-client`           | 10.0.0.101 (DHCP)  | Linux Client Endpoint              |
| `skynet-attacker`               | Dynamic (DHCP)     | Attacker VM                        |
