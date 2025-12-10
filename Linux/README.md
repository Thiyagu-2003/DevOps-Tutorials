---

# 🌐 **Linux Essentials – Complete Guide (Beginner → Advanced)**

<p align="center">
  <img src="https://img.shields.io/badge/Linux-Commands-blue?logo=linux" />
  <img src="https://img.shields.io/badge/SysAdmin-Essentials-green" />
  <img src="https://img.shields.io/badge/Level-Basic%20to%20Advanced-orange" />
  <a href="https://github.com/Thiyagu-2003">
    <img src="https://img.shields.io/badge/Made%20By-Thiyagu%20S-green?logo=github" />
  </a>
</p>

---

# 📑 **Table of Contents**

1. [📘 Overview](#-overview)
2. [📁 Linux File System Hierarchy](#-1-linux-file-system-hierarchy)
3. [📂 Basic Commands](#-2-basic-file--directory-commands)
4. [👤 Basic User & Group Commands](#-3-basic-user--group-commands)
5. [📦 Package Management](#-4-package-management)
6. [⚙ System Information](#-5-system-information)
7. [🟧 Intermediate Linux](#-intermediate-linux)
8. [🟥 Advanced Linux](#-advanced-linux)
9. [🟩 VI/VIM Cheat Sheet](#-vivim-cheat-sheet)
10. [❓ 20 Linux Interview Questions](#-20-important-linux-interview-questions)
11. [👤 Author](#-author)
12. [❤️ Footer](#-footer)

---

# 📘 **Overview**

This guide gives you a **complete Linux knowledge pack**:

✔ Beginner → Advanced
✔ Commands explained clearly
✔ Real admin-level usage
✔ 20 interview questions
✔ VI/VIM cheat sheet
✔ Visually clean, GitHub-ready format

No fluff. No filler. Pure practical Linux.

---

# 🟦 **1. Linux File System Hierarchy**

| Path            | Description                   |
| --------------- | ----------------------------- |
| `/`             | Root of entire system         |
| `/home`         | User home directories         |
| `/root`         | Admin/root user’s home        |
| `/etc`          | Config files                  |
| `/var`          | Logs and runtime data         |
| `/usr`          | Installed software/libraries  |
| `/bin`, `/sbin` | Essential binaries            |
| `/opt`          | Optional third-party software |
| `/tmp`          | Temporary files               |
| `/dev`          | Device files                  |
| `/proc`         | Virtual process info          |
| `/sys`          | Kernel/hardware info          |

---

# 📂 **2. Basic File & Directory Commands**

| Command        | Use                     |
| -------------- | ----------------------- |
| `ls`           | List files              |
| `ls -l`        | Show permissions        |
| `ls -a`        | Show hidden files       |
| `cd`           | Change directory        |
| `pwd`          | Print working directory |
| `mkdir dir`    | Create directory        |
| `rm file`      | Delete file             |
| `rm -r dir`    | Recursive delete        |
| `cp src dest`  | Copy                    |
| `mv src dest`  | Move/rename             |
| `touch file`   | Create empty file       |
| `cat file`     | View content            |
| `head file`    | First 10 lines          |
| `tail file`    | Last 10 lines           |
| `tail -f file` | Live log view           |

---

# 👤 **3. Basic User & Group Commands**

| Command    | Use          |
| ---------- | ------------ |
| `whoami`   | Current user |
| `id`       | UID/GID info |
| `sudo cmd` | Run as admin |

---

# 📦 **4. Package Management**

| Command                               | Purpose            |
| ------------------------------------- | ------------------ |
| `apt update` / `yum check-update`     | Refresh repo index |
| `apt install pkg` / `yum install pkg` | Install            |
| `apt remove pkg` / `yum remove pkg`   | Remove             |
| `apt upgrade` / `yum update`          | Update all         |

---

# ⚙️ **5. System Information**

| Command      | Purpose        |
| ------------ | -------------- |
| `uname -a`   | Kernel info    |
| `df -h`      | Disk usage     |
| `du -sh dir` | Folder size    |
| `free -h`    | RAM usage      |
| `uptime`     | Load average   |
| `top`        | Process viewer |

---

# 🟧 **INTERMEDIATE LINUX**

## 👥 **User & Group Management**

| Command                  | Use          |
| ------------------------ | ------------ |
| `useradd user`           | Create user  |
| `passwd user`            | Set password |
| `usermod -aG group user` | Add to group |
| `groupadd group`         | Create group |
| `userdel user`           | Delete user  |
| `chown user:grp file`    | Ownership    |
| `chmod 755 file`         | Permissions  |

---

## 📡 **Networking**

| Command       | Use             |
| ------------- | --------------- |
| `ip a`        | Show interfaces |
| `ip r`        | Routing         |
| `ping host`   | Connectivity    |
| `curl/wget`   | Fetch content   |
| `ss -tulpn`   | Ports           |
| `hostnamectl` | Hostname info   |

---

## 🔥 **Systemd & Services**

| Command                    | Use     |
| -------------------------- | ------- |
| `systemctl status svc`     | Status  |
| `systemctl start/stop svc` | Control |
| `systemctl restart svc`    | Restart |
| `systemctl enable svc`     | Enable  |
| `journalctl -u svc`        | Logs    |

---

## 🎛 Permissions & Processes

| Command          | Use           |
| ---------------- | ------------- |
| `chmod u+x`      | Add execute   |
| `chgrp grp file` | Change group  |
| `ps aux`         | All processes |
| `kill pid`       | Terminate     |

---

## 📦 Tar/Zip

| Command                 | Use            |
| ----------------------- | -------------- |
| `tar -cvf file.tar dir` | Create archive |
| `tar -xvf file.tar`     | Extract        |
| `zip file.zip dir`      | Zip            |
| `unzip file.zip`        | Extract        |

---

## 🐚 Shell Scripting

| Item          | Purpose         |
| ------------- | --------------- |
| `#!/bin/bash` | Interpreter     |
| `echo`        | Output          |
| `read var`    | Input           |
| `if [ ]`      | Conditions      |
| `for i in`    | Loops           |
| `$1 $2`       | Arguments       |
| `chmod +x`    | Make executable |

---

# 🟥 **ADVANCED LINUX**

## 🧩 Advanced File System & Disks

| Command               | Use             |
| --------------------- | --------------- |
| `fdisk -l`            | List partitions |
| `lsblk`               | Block devices   |
| `mount /dev/sdX /mnt` | Mount           |
| `fsck`                | Repair          |
| `mkfs.ext4`           | Format          |
| `lsof`                | Open files      |

---

## 📡 Advanced Networking

| Command          | Use            |
| ---------------- | -------------- |
| `tcpdump`        | Packet capture |
| `nmap host`      | Scan           |
| `netstat -tulpn` | Connections    |
| `scp`            | Remote copy    |
| `rsync`          | Fast sync      |

---

## 🔐 Security & ACLs

| Command          | Use          |
| ---------------- | ------------ |
| `ufw enable`     | Firewall     |
| `ufw allow port` | Open port    |
| `visudo`         | Edit sudoers |
| `setfacl`        | ACL perms    |

---

## 🧠 Performance & Debugging

| Command  | Use              |
| -------- | ---------------- |
| `htop`   | Advanced monitor |
| `dmesg`  | Kernel logs      |
| `vmstat` | Memory           |
| `iostat` | Disk stats       |
| `sar`    | Activity         |

---

## 🐧 Advanced Shell Scripting

| Command   | Use             |
| --------- | --------------- |
| `trap`    | Cleanup         |
| `set -e`  | Stop on error   |
| `awk`     | Text processing |
| `sed`     | Replace text    |
| `grep -r` | Search          |

---

# 🟩 **VI/VIM Cheat Sheet**

| Command         | Action       |
| --------------- | ------------ |
| `i`             | Insert       |
| `a`             | Append       |
| `o`             | New line     |
| `:w`            | Save         |
| `:q`            | Quit         |
| `:wq`           | Save & quit  |
| `:q!`           | Force quit   |
| `dd`            | Delete line  |
| `yy`            | Copy line    |
| `p`             | Paste        |
| `u`             | Undo         |
| `/word`         | Search       |
| `:%s/old/new/g` | Replace all  |
| `gg`            | Top          |
| `G`             | Bottom       |
| `:set number`   | Line numbers |

---

# ❓ **20 Important Linux Interview Questions**

1. Difference between systemd timers vs cron?
2. Hard link vs soft link?
3. Explain RWX permissions.
4. Meaning of `chmod 755`.
5. Role of `/etc/passwd` & `/etc/shadow`.
6. What is a runlevel?
7. `systemctl` vs `service`?
8. How DNS resolution works?
9. Linux boot process explanation.
10. Explain LVM components.
11. Difference between top & htop?
12. What is a zombie process?
13. What is a sticky bit?
14. What are inodes?
15. What is SELinux?
16. bash vs sh?
17. What is `/proc` filesystem?
18. How Linux handles swap?
19. What is a core dump?
20. Explain boot flow (BIOS → Kernel → systemd).

---

# 👤 **Author**

```
Name: Thiyagu S
Role: Cloud & DevOps Learner
Country: India 🇮🇳
```

---

# ❤️ **Footer**

<p align="center">
  <strong>Made with ❤️ by <a href="https://github.com/Thiyagu-2003">Thiyagu S</a></strong><br>
  Learning • Building • Improving
</p>

---
