# 🧰 Installing VirtualBox on Ubuntu (From Official Site)

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

<br>

## ⬇️ Downloading and Setting Up VMs in VirtualBox

Here's how I downloaded the OS ISOs and set up the virtual machines in VirtualBox, following my defined specifications.

---

### Step 1: Downloaded Operating System ISOs

I made sure to get the official installation ISO files for each operating system:

* **Windows Server 2025**: I found and downloaded the evaluation ISO.
* **Windows 11 Enterprise**: I downloaded this through my Microsoft account.
* **Ubuntu 24.04 Desktop**: I downloaded it from the [Ubuntu Official Site](https://ubuntu.com/download/desktop).
* **Ubuntu Server 24.04**: I also got this from the [Ubuntu Official Site](https://ubuntu.com/download/server).
* **Security Onion**: I downloaded the ISO from the [Security Onion Official Site](https://securityonionsolutions.com/download/).
* **Kali Linux 2024**: I chose the "Installer Images" option from the [Kali Linux Official Site](https://www.kali.org/get-kali/#kali-virtual-machines) for a clean install.

---

### Step 2: Setting Up Virtual Machines in VirtualBox

Here’s how I set up each VM listed in the table:

1. **Open VirtualBox** and click on **"New"** to create a new VM.
2. Name your VM exactly as listed in the table (e.g., `skynet-dc`).
3. Choose a **Folder** on your computer to save the VM files.
4. For the **ISO Image**, click the arrow and select the OS you downloaded.
5. VirtualBox will usually guess the **OS Type** for you. If it doesn’t, manually select the correct one (e.g., "Microsoft Windows" and "Windows 11 (64-bit)").
6. Set the **Base Memory & Processors** according to the specs in the table (e.g., `skynet-dc` gets 4096 MB of RAM and 2 CPUs).
7. For the **Hard Disk**, select "Create a virtual hard disk now," then make sure to **uncheck "Pre-allocate Full Size"** for dynamic allocation. Set the disk size based on the **Storage (Minimum)** in the table (e.g., 50 GB for `skynet-dc`).
8. **Network Setup**: 
   - Once your VM is created, but **before starting it**, go to **Settings > Network**.
   - Set **Adapter 1** to **"NAT"** so the VM can access the internet.
   - If you need the VMs to communicate with each other, add extra network adapters set to **"Internal Network"** and give them a consistent name (e.g., `skynet-network`).
9. Click **"Finish"** to complete the setup.
10. To **install the OS**, select the VM, click **"Start"**, and follow the on-screen instructions using the mounted ISO.

Repeat this process for each VM you need to set up.

### VM Specifications:

| VM Name              | Operating System       | Specs           | Storage (Minimum) |
|----------------------|------------------------|-----------------|-------------------|
| `skynet-dc`          | Windows Server 2025    | 2 CPU / 4096 MB | 50 GB             |
| `skynet-win-client`  | Windows 11 Enterprise  | 2 CPU / 4096 MB | 80 GB             |
| `skynet-linux-client`| Ubuntu 24.04 Desktop   | 1 CPU / 3500 MB | 80 GB             |
| `skynet-sec-work`    | Security Onion         | 1 CPU / 2048 MB | 55 GB             |
| `skynet-sec-box`     | Ubuntu 24.04 Desktop   | 2 CPU / 4096 MB | 80 GB             |
| `skynet-corp-svr`    | Ubuntu Server 24.04    | 1 CPU / 2048 MB | 25 GB             |
| `skynet-attacker`    | Kali Linux 2024        | 1 CPU / 2048 MB | 55 GB             |
<br>

# 📦 Enabling Full Integration Features

## Purpose

To enable smooth VM usability by turning on:

- ✅ Full screen support  
- ✅ Shared clipboard (Host ↔ Guest)  
- ✅ Drag & drop (Host ↔ Guest)

Guest Additions were installed and configured for:

- Windows 11  
- Ubuntu Linux  
- Kali Linux  

---

## 🧰 General Process (All VMs)

1. Start the VM.
2. In the **VirtualBox menu bar**, go to:  

> 📸 **Devices → Insert Guest Additions CD image...** ![Insert Guest Additions CD image](img/insertcdimage.png)
3. Run the installer **inside the VM** when prompted.
4. Reboot the VM.
5. Enable integration features via:

> 📸 **Machine → Settings → General → Advanced → Shared Clipboard → Bidirectional
Devices → Drag and Drop → Bidirectional** ![Integration](img/integration.png)

---

## 🪟 Windows 11 VM

- Open the Guest Additions CD from **File Explorer**.
- Run `VBoxWindowsAdditions.exe` as Administrator.
- Follow the installer steps and reboot when finished.

---

## 🐧 Ubuntu & Kali Linux VMs

- After inserting the CD, open the file manager and run:  
 `VBoxLinuxAdditions.run`

> 📸 **(Right-click → Open in Terminal → Run with sudo if needed)** ![Open in Terminal](img/openterminal.png)

> 📸 ![Terminal](img/terminal.png)

     ```bash
     sudo ./VBoxLinuxAdditions.run

- You may need to install required packages beforehand:
     ```bash
     sudo apt update
     sudo apt install -y build-essential dkms linux-headers-$(uname -r)

- Reboot the VM after installation.

✅ Result

Once Guest Additions are installed and integration options are enabled:

- VMs can enter full-screen mode seamlessly.
- Clipboard and drag-and-drop work both ways between host and guest.
