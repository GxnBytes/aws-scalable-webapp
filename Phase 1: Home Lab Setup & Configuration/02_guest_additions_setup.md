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

**Devices → Insert Guest Additions CD image...**
> 📸 ![Insert Guest Additions CD image](04_snapshots/insertcdimage.png)
3. Run the installer **inside the VM** when prompted.
4. Reboot the VM.
5. Enable integration features via:

**Machine → Settings → General → Advanced → Shared Clipboard → Bidirectional
Devices → Drag and Drop → Bidirectional**

> 📸 ![Integration](04_snapshots/integration.png)

---

## 🪟 Windows 11 VM

- Open the Guest Additions CD from **File Explorer**.
- Run `VBoxWindowsAdditions.exe` as Administrator.
- Follow the installer steps and reboot when finished.

---

## 🐧 Ubuntu & Kali Linux VMs

- After inserting the CD, open the file manager and run:  
 `VBoxLinuxAdditions.run`

***(Right-click → Open in Terminal → Run with sudo if needed)***
> 📸 ***(Right-click → Open in Terminal → Run with sudo if needed)*** ![Open in Terminal](04_snapshots/openterminal.png)

> 📸 ![Terminal](04_snapshots/terminal.png)

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
