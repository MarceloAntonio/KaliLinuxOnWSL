# Installing Kali Linux on WSL with Graphical Interface

This guide explains how to install **Kali Linux** on Windows Subsystem for Linux (WSL), set up the graphical interface, and enable remote access.
---

## Installation Steps

### 1. Enable WSL

1. Open **PowerShell** as administrator.
2. Run the command:

   ```bash
   wsl --install
   ```

3. Restart your computer.

### 2. Install Kali Linux

1. After restarting, run the following command in **PowerShell**:

   ```bash
   wsl --install kali-linux
   ```

2. During installation, you will be prompted to create a UNIX user:

   ```bash
   Enter new UNIX username: celo
   ```

3. Set and confirm a password:

   ```bash
   New password:
   Retype new password:
   ```

4. If everything is correct, you will see the message:

   ```bash
   Installation successful!
   ```

---

## 3. Update Packages and Install Graphical Interface

### 3.1 Update Packages

1. Log in as root:

   ```bash
   sudo apt update
   ```

2. Upgrade installed packages:

   ```bash
   sudo apt upgrade -y
   ```

### 3.2 Install XFCE Graphical Interface

1. Install the graphical environment:

   ```bash
   sudo apt install kali-desktop-xfce -y
   ```

2. Install XRDP to enable remote access:

   ```bash
   sudo apt install xrdp -y
   ```

3. Install additional dependencies for remote access:

   ```bash
   sudo apt install -y dbus-x11
   ```

4. Start the XRDP service (you will need to run this command after each reboot):

   ```bash
   sudo /etc/init.d/xrdp start
   ```

---

## 4. Configure Remote Access

1. Find the IP address of the WSL machine using:

   ```bash
   ifconfig
   ```

   Example output:

   ```bash
   inet 192.168.1.1  netmask 255.255.255.255  broadcast 192.168.1.1
   ```

2. Copy the address shown after `inet` (in this example, **192.168.1.1**).

3. On Windows:
   - Press `Win + R`.
   - Type `mstsc` and click **OK**.
   - Paste the IP address and connect.

4. Log in with the user and password you created earlier.

---

## 5. Final Result

If all steps are followed correctly, you will have **Kali Linux** installed and configured on WSL with a graphical interface and functional remote access.

---

## 6. Credits

- [Kali Linux Docs](https://www.kali.org/docs/).
- [Kali Linux XFCE](https://www.kali.org/docs/general-use/xfce-with-rdp/).
- [Thaly Lima](https://www.instagram.com/th4litalima?igsh=MW9hZ2Exc2sxbm4zeQ==).

---

