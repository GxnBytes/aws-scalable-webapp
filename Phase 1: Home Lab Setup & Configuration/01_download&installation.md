# 🛠️ Host Machine Setup: Native Linux with VirtualBox

## Why I Switched from Windows

I removed Windows from my machine because it felt bulky and inefficient for my cybersecurity homelab. Running a native Linux system (Ubuntu) gave me better performance, more control, and easier access to open-source security tools. It also helped me sharpen my Linux skills, which are essential in real-world cybersecurity environments.

---

<br>

## 🧰 Installing VirtualBox on Ubuntu (Downloaded from Official Site)

I installed **VirtualBox version 7.0.26r168464** by downloading the `.deb` package directly from the official Oracle VirtualBox website.

### Installation Steps:

1. **Go to the official download page**  
   👉 [https://www.virtualbox.org/wiki/Linux_Downloads](https://www.virtualbox.org/wiki/Linux_Downloads)

2. **Download the Debian package** for your Ubuntu version (e.g., `Ubuntu 20.04`, `22.04`, etc.)

3. **Install the package using your terminal**
   ```bash
   cd ~/Downloads
   sudo dpkg -i virtualbox-7.0_*.deb

4. **Fix any missing dependencies (if needed)**
   ```bash
   sudo apt --fix-broken install

5. **Verify the installation**
   ```bash
   virtualbox --help

VirtualBox is now ready for use. I use it to run virtual machines as part of my cybersecurity homelab setup.
   ```
   ✅ Version installed: VirtualBox 7.0.26r168464 on Ubuntu Linux
   ``` 

## ⬇️ Downloading and Setting Up VMs in VirtualBox

I've outlined the process I followed to download the necessary operating system ISOs and create the virtual machines in VirtualBox, based on the specifications I defined.

**Step 1: I Downloaded Operating System ISOs**

I made sure to download the installation ISO files for each operating system listed, always using official sources to ensure authenticity and security:

* **Windows Server 2025:** I searched for and acquired the appropriate evaluation version ISO since I don't have a volume licensing account.
* **Windows 11 Enterprise:** I downloaded this through my Microsoft account, which provides access to Enterprise editions.
* **Ubuntu 24.04 Desktop:** I got this directly from the [Ubuntu Official Site](https://ubuntu.com/download/desktop).
* **Ubuntu Server 24.04:** This was also downloaded from the [Ubuntu Official Site](https://ubuntu.com/download/server).
* **Security Onion:** I downloaded the ISO from the [Security Onion Official Site](https://securityonionsolutions.com/download/).
* **Kali Linux 2024:** I chose the "Installer Images" option from the [Kali Linux Official Site](https://www.kali.org/get-kali/#kali-virtual-machines) to perform a clean installation.

**Step 2: I Created Virtual Machines in VirtualBox**

For each VM specified in my table, I followed these general steps within VirtualBox:

1.  I **opened VirtualBox** and clicked **"New"** to initiate the creation of a new virtual machine.
2.  For the **Name**, I entered the `VM Name` exactly as specified (e.g., `skynet-dc`).
3.  I selected a specific **Folder** on my disk to store the VM's files.
4.  For the **ISO Image**, I clicked the arrow next to the field and navigated to select the downloaded ISO file corresponding to the operating system.
5.  VirtualBox typically detected the **Type** of OS automatically. If not, I manually selected it (e.g., "Microsoft Windows" and "Windows 11 (64-bit)" or "Linux" and "Ubuntu (64-bit)").
6.  I adjusted the **Base Memory & Processors** settings according to the `Specs` column in my table (e.g., for `skynet-dc`, I set "Base Memory" to 4096 MB and "Processors" to 2 CPU).
7.  For the **Hard Disk**, I chose "Create a virtual hard disk now" and made sure the "Pre-allocate Full Size" box was **NOT** checked, opting for dynamic allocation to save space. I set the size to the `Storage (Minimum)` value from the table (e.g., for `skynet-dc`, I set it to 50 GB).
8.  **Network Configuration was Crucial:** After creating each VM but **before starting it for the first time**, I went to the VM's **Settings > Network**.
    * I set **Adapter 1** to **"NAT"**. This allowed the VM to access the internet.
    * For internal communication between VMs, I added additional network adapters, setting them as **"Internal Network"** and naming them consistently (e.g., `skynet-network`).
9.  I reviewed all my settings and then clicked **"Finish"** (or "Create").
10. Finally, to **Install the Operating System**, I selected the newly created VM in the VirtualBox Manager and clicked **"Start"**. I then followed the on-screen prompts to install the operating system using the mounted ISO.

I repeated these steps for every virtual machine required for my setup.
