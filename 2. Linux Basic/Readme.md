# 🐧 Linux Basics — Revision Notes

---

## 1. What is Linux?

**Linux** is a free, open-source **operating system** based on Unix. It was created by **Linus Torvalds** in 1991.

- It manages your computer's **hardware and software resources**.
- It is widely used in **servers, cloud computing, DevOps, Android phones**, and supercomputers.
- Popular distributions (distros): **Ubuntu, CentOS, Red Hat, Debian, Fedora, Kali Linux**.

> 💡 Linux is **open-source** — anyone can view, modify, and distribute its source code for free.

---

## 2. Difference Between Linux and Windows

| Feature           | Linux                          | Windows                      |
| ----------------- | ------------------------------ | ---------------------------- |
| **Source**        | Open-source (free)             | Proprietary (paid license)   |
| **Security**      | More secure, less virus-prone  | More vulnerable to malware   |
| **Customization** | Highly customizable            | Limited customization        |
| **CLI Usage**     | Heavy use of terminal/commands | Mostly GUI-based             |
| **File System**   | ext4, xfs, btrfs               | NTFS, FAT32                  |
| **Used For**      | Servers, DevOps, development   | Desktop, gaming, office work |
| **Updates**       | User-controlled                | Forced updates               |
| **Cost**          | Free                           | Paid                         |

---

## 3. Software Remote Location Server Tools

These tools let you **connect to and manage remote servers**:

| Tool                   | Purpose                                                    |
| ---------------------- | ---------------------------------------------------------- |
| **SSH** (Secure Shell) | Securely connect to remote servers via terminal            |
| **PuTTY**              | SSH client for Windows                                     |
| **MobaXterm**          | Advanced remote terminal for Windows                       |
| **FileZilla**          | Transfer files between local and remote servers (FTP/SFTP) |
| **WinSCP**             | Secure file transfer for Windows                           |
| **TeamViewer**         | Remote desktop access with GUI                             |
| **Ansible**            | Automate tasks on multiple remote servers                  |

> 💡 Most common: `ssh user@server-ip` — connects you to a remote Linux server.

---

## 4. Kernel, Bootloader and Shell

### 🔹 Kernel

The **core of the OS** that directly communicates with hardware. It manages **memory, CPU, devices, and processes**.

### 🔹 Bootloader

The first program that runs when you **power on** the computer. It **loads the kernel** into memory.

- Examples: **GRUB**, LILO

### 🔹 Shell

The **interface between the user and the kernel**. You type commands in the shell, and it passes them to the kernel for execution.

- Types: **Bash** (most common), Zsh, Fish, Sh

```
User → Shell → Kernel → Hardware
```

---

## 5. Desktop Environment

A **Desktop Environment (DE)** provides the **graphical interface** (GUI) — windows, icons, taskbar, file manager, etc.

| Desktop Environment | Description                              |
| ------------------- | ---------------------------------------- |
| **GNOME**           | Default in Ubuntu, modern & clean        |
| **KDE Plasma**      | Feature-rich, highly customizable        |
| **XFCE**            | Lightweight, fast, low resource usage    |
| **LXDE**            | Very lightweight, for older hardware     |
| **Cinnamon**        | Default in Linux Mint, Windows-like feel |

> 💡 Linux servers usually run **without a DE** (headless mode) to save resources — only terminal/CLI is used.

---

## 6. Linux System Architecture

Linux architecture has **4 main layers**:

```
┌─────────────────────────┐
│     User Applications   │  ← Apps you use (browser, editor)
├─────────────────────────┤
│     Shell / CLI / GUI   │  ← Interface to interact with OS
├─────────────────────────┤
│        Kernel           │  ← Core: manages CPU, memory, devices
├─────────────────────────┤
│       Hardware          │  ← CPU, RAM, Disk, Network
└─────────────────────────┘
```

- **Hardware** — Physical components (CPU, RAM, HDD).
- **Kernel** — Talks to hardware, manages resources.
- **Shell** — Takes user commands and sends to kernel.
- **Applications** — Software that users interact with.

---

## 7. Information About Hardware

Useful commands to check **hardware info** in Linux:

| Command               | What It Shows                      |
| --------------------- | ---------------------------------- |
| `lscpu`               | CPU details                        |
| `free -h`             | RAM usage                          |
| `df -h`               | Disk space usage                   |
| `lsblk`               | Block devices (disks & partitions) |
| `lspci`               | PCI devices (GPU, network card)    |
| `lsusb`               | USB devices                        |
| `uname -a`            | Kernel & OS info                   |
| `cat /etc/os-release` | Linux distro info                  |
| `top` / `htop`        | Live CPU & memory usage            |

---

## 8. Linux File System

The Linux file system is organized in a **tree structure** starting from the **root `/`**.

| Directory | Purpose                          |
| --------- | -------------------------------- |
| `/`       | Root — top of the file system    |
| `/home`   | User home directories            |
| `/etc`    | Configuration files              |
| `/var`    | Logs, variable data              |
| `/tmp`    | Temporary files                  |
| `/bin`    | Essential user commands (ls, cp) |
| `/sbin`   | System admin commands            |
| `/usr`    | User programs & libraries        |
| `/opt`    | Optional/third-party software    |
| `/dev`    | Device files                     |
| `/boot`   | Bootloader & kernel files        |
| `/root`   | Home directory of root user      |

---

## 9. Difference Between File System and Directory

|             | File System                                                      | Directory                                           |
| ----------- | ---------------------------------------------------------------- | --------------------------------------------------- |
| **What**    | The **method/structure** used to organize and store data on disk | A **folder** that holds files and other directories |
| **Example** | ext4, xfs, NTFS                                                  | `/home`, `/etc`, `/var`                             |
| **Role**    | Defines **how data is stored & retrieved**                       | Provides **logical organization** of files          |
| **Analogy** | The **blueprint** of a library                                   | A **shelf** inside the library                      |

> 💡 File system = **how** data is stored. Directory = **where** data is organized.

---

## 10. Difference Between Linux and Unix

| Feature          | Linux                            | Unix                              |
| ---------------- | -------------------------------- | --------------------------------- |
| **Source**       | Open-source                      | Mostly proprietary                |
| **Cost**         | Free                             | Usually paid                      |
| **Developed By** | Linus Torvalds (1991)            | AT&T Bell Labs (1969)             |
| **Examples**     | Ubuntu, CentOS, Fedora           | Solaris, AIX, HP-UX, macOS        |
| **Usage**        | Servers, cloud, desktops, mobile | Enterprise servers, mainframes    |
| **Hardware**     | Works on any hardware            | Usually tied to specific hardware |

> 💡 Linux is **inspired by Unix** but is **not Unix** — it was written from scratch.

---

## 11. States of Processes in Linux

A **process** is a running program. It can be in the following states:

| State        | Symbol | Meaning                                                                                           |
| ------------ | :----: | ------------------------------------------------------------------------------------------------- |
| **Running**  |  `R`   | Currently executing on the CPU                                                                    |
| **Sleeping** |  `S`   | Waiting for an event (e.g., user input, I/O)                                                      |
| **Stopped**  |  `T`   | Paused by a signal (e.g., `Ctrl+Z`)                                                               |
| **Zombie**   |  `Z`   | Process finished but still has an entry in the process table (parent hasn't read its exit status) |
| **Dead**     |  `X`   | Process completely terminated                                                                     |

**Useful commands:**

- `ps aux` — List all running processes
- `top` / `htop` — Live process monitoring
- `kill PID` — Terminate a process
- `kill -9 PID` — Force kill a process

```
New → Running ⇄ Sleeping → Stopped → Zombie → Dead
```

---

> 📅 Last Updated: February 2026
