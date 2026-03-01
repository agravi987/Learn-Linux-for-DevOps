# 🚀 Essential Linux Commands Cheat Sheet

**Quick refs for common sysadmin tasks. Run `man command` for full deets. Assumes Ubuntu/Debian (apt) unless noted.**

## 📋 System Info Commands

- **uname**  
  Shows kernel/system info.  
  `uname -a` → All details (kernel, OS, arch).  
  _Ex: Linux ubuntu 5.15.0-73-generic_

- **uptime**  
  System runtime + load avg.  
  `uptime` → "up 2 days, 3:45, 2 users, load 0.10"  
  _Great for monitoring server health._

- **date**  
  Current date/time.  
  `date` → "Sun Mar 1 10:09:00 IST 2026"  
  `date +%Y-%m-%d` → "2026-03-01" (custom format).

## 👥 User & Process Commands

- **who / whoami**  
  `who` → Logged-in users (list).  
  `whoami` → Your current username.  
  _Ex: whoami → ravi_

- **id**  
  User/group IDs.  
  `id` → "uid=1000(ravi) gid=1000(ravi) groups=..."  
  _Check perms fast._

- **which**  
  Path of executable.  
  `which ls` → "/bin/ls"  
  _Find where a command lives._

## 🔐 Admin Commands

- **sudo**  
  Run as superuser.  
  `sudo apt update` → Needs password.  
  _Prefix any command for root access._

## 💥 Power Commands (DANGER!)

- **shutdown**  
  Power off safely.  
  `sudo shutdown -h now` → Halt immediately.  
  `sudo shutdown -h +5` → In 5 mins.

- **reboot**  
  Restart system.  
  `sudo reboot` → Reboot now.  
  _Use `sudo init 6` as alt._

## 🛠️ Package Managers

| Command              | Distro         | Key Uses                                                                                   |
| -------------------- | -------------- | ------------------------------------------------------------------------------------------ |
| **apt**              | Debian/Ubuntu  | `sudo apt update`<br>`sudo apt install vim`<br>`sudo apt remove vim`<br>`apt search nginx` |
| **yum**              | RHEL/CentOS 7  | `sudo yum install vim`<br>`sudo yum update`<br>`yum search nginx`                          |
| **dnf**              | Fedora/RHEL 8+ | Like yum but faster: `sudo dnf install vim`                                                |
| **pacman**           | Arch Linux     | `sudo pacman -Syu` (update)<br>`sudo pacman -S vim`                                        |
| **portage** (emerge) | Gentoo         | `sudo emerge vim`<br>Compile-focused, advanced.                                            |

**Pro Tip:** Always `sudo` for installs. Check distro first: `cat /etc/os-release`.
