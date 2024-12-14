# 42_Born2BRoot
# Born2BeRoot Project

The **Born2BeRoot** project is part of a system administration curriculum aimed at teaching fundamental server setup, configuration, and management skills. The objective is to configure a virtual machine to function as a secure server while adhering to strict guidelines and policies. This project provides an excellent opportunity to develop critical skills in Linux system administration, focusing on security, resource management, and automation.

As part of this project, I chose **Debian** as the operating system due to its stability and widespread adoption in server environments. The setup includes configuring partitions, SSH, a firewall, user management, sudo rules, and a custom monitoring script to display essential system metrics.

---

## Key Features and Configurations

### 1. **Operating System: Debian**
- Selected **Debian** for its stability, simplicity, and extensive community support.
- Configured **AppArmor** for enhanced security.

### 2. **Disk and Partition Management**
- Set up encrypted partitions using **LVM** for secure and flexible disk management.

### 3. **SSH Configuration**
- Configured SSH to run on **port 4242**.
- Disabled root login via SSH to enhance security.

### 4. **Firewall Setup**
- Installed and configured **UFW (Uncomplicated Firewall)**.
- Allowed only port 4242 for incoming connections and enabled the firewall at startup.

### 5. **User Management and Security**
- Created a new user with:
  - Membership in `sudo` and `user42` groups.
  - Strict **password policies**:
    - Passwords must expire every 30 days.
    - Minimum length of 10 characters, with complexity requirements (uppercase, lowercase, numbers).
    - Prohibited using usernames or repetitive characters in passwords.
- Enabled `pam_tally2` to limit failed login attempts and enforce account locks after 3 failures.

### 6. **Sudo Configuration**
- Restricted the number of sudo password attempts to 3.
- Configured logging of all sudo commands to `/var/log/sudo/`.
- Enabled TTY mode and restricted the environment for sudo commands.

### 7. **Monitoring Script**
- Created a Bash script, `monitoring.sh`, which:
  - Displays system stats every 10 minutes.
  - Outputs details such as CPU usage, memory, disk usage, LVM status, active connections, and running processes.
  - Uses `wall` to broadcast the information.

---

## Why Debian and APT?
I chose **Debian** for its stability, reliability, and simplicity, making it an ideal environment for system administration tasks. The **APT package manager** streamlines software installation and updates, ensuring dependency management is seamless. Additionally, Debian’s extensive documentation and active community provide excellent support for troubleshooting and learning.

---

This project demonstrates the essential skills of system administration, focusing on security, scalability, and automation. Feel free to explore and adapt the configurations provided in this repository!
