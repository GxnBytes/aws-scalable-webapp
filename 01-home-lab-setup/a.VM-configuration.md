# Home Lab Setup: Virtual Machine Configuration

### Prerequisites:
- VMware Workstation or VirtualBox installed on your machine.
- A minimum of 8 GB of RAM and 100 GB of free disk space.

### Steps to Create Virtual Machines:

1. **Create a Windows 10 VM:**
   - Download Windows 10 ISO from the official website.
   - Follow the wizard to set up the virtual machine with at least 2 GB of RAM and 20 GB of storage.
   - Install **Winlogbeat** and **Sysmon** for log forwarding to Splunk.

2. **Create an Ubuntu Server VM:**
   - Download Ubuntu Server ISO from the official website.
   - Set up Ubuntu with 2 GB of RAM and 20 GB of storage.
   - Install required security tools (e.g., ELK stack, filebeat).

3. **Create a Kali Linux VM:**
   - Download Kali Linux ISO.
   - Configure Kali with 2 GB of RAM and 20 GB of storage.
   - Install Hydra, Metasploit, and other tools for simulating attacks.

4. **Configure Networking:**
   - Use NAT or Host-Only networking to ensure the VMs are isolated for testing.

### Notes:
- Ensure all VMs have unique IP addresses.