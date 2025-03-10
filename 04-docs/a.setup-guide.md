# 📌 Resources Setup Guide  
🚀 *Follow this guide to set up all the required tools for your Security Monitoring Lab.*  

---

## 1️⃣ System Requirements  
Before setting up, ensure your machine meets these **minimum requirements**:  

- **CPU:** Quad-core (Intel i5/i7 or AMD equivalent)  
- **RAM:** **16GB+** (Recommended for running multiple virtual machines)  
- **Storage:** **100GB+** free space (Preferably SSD for better performance)  
- **Operating System:** Windows 10/11, macOS, or Linux  

> **💡 Note:** If your local machine is not powerful enough, consider using cloud-based virtualisation platforms such as **AWS, Azure, or Google Cloud**.  

---

## 2️⃣ Required Software & Downloads  

📥 **Download and install the following tools before proceeding:**  

| **Tool** | **Description** | **Download Link** |
|----------|---------------|-------------------|
| **VMware Workstation** / **VirtualBox** | Virtualisation software for running virtual machines | [VMware Workstation](https://www.vmware.com/go/downloadworkstation) / [VirtualBox](https://www.virtualbox.org/wiki/Downloads) |
| **Windows 10 ISO** | Windows VM for endpoint monitoring | [Download](https://www.microsoft.com/en-gb/software-download/windows10ISO) |
| **Ubuntu Server ISO** | Linux VM for ELK stack or additional security tools | [Download](https://ubuntu.com/download/server) |
| **Kali Linux ISO** | VM for ethical hacking & penetration testing | [Download](https://www.kali.org/get-kali/) |
| **Splunk Free** | SIEM tool for log analysis | [Download](https://www.splunk.com/en_gb/download.html) |
| **Zeek** | Network monitoring tool for network traffic analysis | [Download](https://zeek.org/get-zeek/) |
| **Suricata** | Intrusion Detection System (IDS) for network traffic monitoring | [Download](https://suricata.io/download/) |
| **Winlogbeat** | Log forwarding from Windows to Splunk | [Download](https://www.elastic.co/beats/winlogbeat) |
| **Sysmon** | Windows event logging tool | [Download](https://docs.microsoft.com/en-gb/sysinternals/downloads/sysmon) |

---

## 3️⃣ Virtual Machine (VM) Setup  
🎯 *Follow these steps to set up your virtual machines:*  

### 🔹 Install VMware Workstation or VirtualBox  
1. Download **VMware Workstation Pro/Player** or **VirtualBox**.  
2. Install it following the on-screen instructions.  

### 🔹 Create Virtual Machines  
- **Windows 10 VM:** *(For endpoint monitoring & event logging)*  
- **Ubuntu Server VM:** *(For ELK stack, additional security tools, and log collection)*  
- **Kali Linux VM:** *(For launching simulated attacks & penetration testing)*  

> ⚙️ *Ensure that networking is set to **NAT or Host-Only** to create an isolated lab environment.*  

---

## 4️⃣ Installing Security & Monitoring Tools  

### 🔹 Setting Up Splunk  
1. Install **Splunk Free** on the **Ubuntu Server VM**.  
2. Configure the Splunk Web Interface & enable log collection.  
3. Install **Winlogbeat** & **Sysmon** on the Windows 10 VM to forward logs to Splunk.  

### 🔹 Setting Up Zeek and Suricata  
1. Install **Zeek** and **Suricata** on the **Ubuntu Server VM**.  
2. Configure **Zeek** and **Suricata IDS** for network traffic monitoring.  
3. Ensure logs are being collected from **Zeek** and **Suricata** to your SIEM tool (e.g., Splunk).  

---

## 5️⃣ Verifying Log Collection & Connectivity  

✔ **Windows Event Logs, Sysmon logs, and Firewall logs** should appear in **Splunk**.  
✔ **Zeek and Suricata** should be **receiving network traffic logs**.  
✔ Create a **basic Splunk dashboard** to visualise incoming logs.

---

## 🎯 Next Steps: Proceed to Home Lab Setup  
Once all resources are installed and configured, move on to **[Home Lab Setup](../01-home-lab-setup/a.VM-configuration.md)** to begin setting up log sources and monitoring dashboards.  
