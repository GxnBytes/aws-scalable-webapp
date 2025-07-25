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

### Step 2: Created Virtual Machines in VirtualBox

For each VM listed in my table, I followed these steps in VirtualBox:

1.  I **opened VirtualBox** and clicked **"New"** to start creating a new VM.
2.  I entered the **VM Name** exactly as specified (e.g., `skynet-dc`).
3.  I picked a **Folder** on my computer to save the VM's files.
4.  For **ISO Image**, I clicked the arrow and selected the downloaded ISO file for the correct OS.
5.  VirtualBox usually guessed the **Type** of OS. If not, I picked it manually (e.g., "Microsoft Windows" and "Windows 11 (64-bit)").
6.  I set the **Base Memory & Processors** according to the `Specs` in my table (e.g., `skynet-dc` got 4096 MB memory and 2 CPUs).
7.  For the **Hard Disk**, I chose "Create a virtual hard disk now" and **unchecked "Pre-allocate Full Size"** for dynamic allocation. I set the size to the `Storage (Minimum)` from my table (e.g., 50 GB for `skynet-dc`).
8.  **Important Network Setup**: After creating the VM, but **before starting it**, I went to its **Settings > Network**.
    * I set **Adapter 1** to **"NAT"** to give the VM internet access.
    * For VMs to talk to each other, I added extra adapters set to **"Internal Network"**, giving them a consistent name (e.g., `skynet-network`).
9.  I reviewed everything and then clicked **"Finish"** (or "Create").
10. To **Install the OS**, I selected the VM in VirtualBox Manager and clicked **"Start"**. Then, I just followed the on-screen installation prompts using the mounted ISO.

I repeated these steps for every VM I needed to set up.
