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

    ✅ Version installed: VirtualBox 7.0.26r168464 on Ubuntu Linux
