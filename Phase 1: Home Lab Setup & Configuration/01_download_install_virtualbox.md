# 🛠️ Host Machine Setup: Native Linux with VirtualBox

## Why I Switched from Windows

I removed Windows from my machine because it felt bulky and inefficient for my cybersecurity homelab. Running a native Linux system (Ubuntu) provided better performance, more control over system resources, and seamless access to open-source security tools.

Using Linux as my primary OS also aligned with my goal of building real-world skills in a typical enterprise environment — where Linux is widely used for servers, security tooling, and infrastructure automation.

---

## 🧰 Installing VirtualBox on Ubuntu

I installed **VirtualBox version 7.0.26r168464** on my Ubuntu machine to manage and run isolated virtual environments for my lab.

### Step-by-Step Installation

1. **Update system packages**
   ```bash
   sudo apt update && sudo apt upgrade -y
   
2. **Install required dependencies**
   ```bash
   sudo apt install -y software-properties-common
