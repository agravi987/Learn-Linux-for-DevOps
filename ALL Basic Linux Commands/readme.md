# 🐧 Linux Basic Commands – Quick Reference Guide

> **Hey there, Reader! 👋**
> Don't worry — this is **not** a huge, scary document. Just focus, scroll through, and you'll pick up exactly what you need. Think of it as your **pocket cheat-sheet** for Linux! 🚀

---

## 📂 1. File & Directory Navigation

### `pwd` – Print Working Directory

Shows your current location in the file system.

```bash
pwd
```

📌 **Output example:**

```
/home/ravi/projects
```

---

### `ls` – List Files & Directories

```bash
ls          # basic listing
ls -l       # long listing format
ls -a       # show hidden files
ls -lh      # human-readable sizes
```

> [!TIP]
> `-l` → shows permissions, owner, size, date
> `-a` → reveals hidden files (those starting with `.`)

---

### `cd` – Change Directory

```bash
cd foldername
cd ..
cd ~
cd /
```

| Command | Meaning              |
| ------- | -------------------- |
| `cd ..` | Move one level up    |
| `cd ~`  | Go to home directory |
| `cd /`  | Go to root directory |

---

## 📁 2. Directory Management

### `mkdir` – Create Directory

```bash
mkdir test
mkdir -p parent/child/grandchild
```

> `-p` creates the **full path** if it doesn't exist yet.

---

### `rmdir` – Remove Empty Directory

```bash
rmdir foldername
```

> [!WARNING]
> Works **only** if the directory is empty.

---

### `rm` – Remove Files / Directories

```bash
rm file.txt        # remove a file
rm -r folder       # remove a directory recursively
rm -rf folder      # force remove without confirmation
```

| Flag | Purpose                               |
| ---- | ------------------------------------- |
| `-r` | Recursive (needed for directories)    |
| `-f` | Force delete (no confirmation prompt) |

> [!CAUTION]
> `rm -rf` is **powerful and dangerous**. Double-check before you run it! 🚨

---

## 📄 3. File Viewing Commands

### `cat` – Display File Content

```bash
cat file.txt
```

---

### `zcat` – Read Compressed File (`.gz`)

```bash
zcat file.gz
```

> Useful for reading compressed log files without extracting them.

---

### `head` – Show First Lines

```bash
head file.txt          # first 10 lines (default)
head -n 20 file.txt    # first 20 lines
```

---

### `tail` – Show Last Lines

```bash
tail file.txt          # last 10 lines (default)
tail -n 20 file.txt    # last 20 lines
```

#### 🔥 `tail -f` — Real-Time Log Monitoring

```bash
tail -f logfile.log
```

> [!IMPORTANT]
> This is one of the **most used commands** in production servers.
> It lets you watch logs update **live** in real-time. Press `Ctrl + C` to exit.

---

### `less` – Interactive File Viewer

```bash
less file.txt
```

- ✔ Scroll up / down freely
- ✔ Search with `/keyword`
- ✔ Quit with `q`

> Preferred over `more` (which has limited navigation).

---

## 📄 4. File Creation & Manipulation

### `touch` – Create an Empty File

```bash
touch file.txt
```

> Also updates the file's timestamp if it already exists.

---

### `cp` – Copy Files

```bash
cp file1 file2              # copy a file
cp -r folder1 folder2       # copy a directory recursively
```

---

### `mv` – Move or Rename

```bash
mv oldname.txt newname.txt      # rename
mv file.txt /home/ravi/         # move to another location
```

---

## 📊 5. Text Processing Commands

### `wc` – Word Count

```bash
wc file.txt        # lines, words, characters
wc -l file.txt     # lines only
wc -w file.txt     # words only
wc -c file.txt     # characters only
```

---

### `cut` – Extract Columns

```bash
cut -d "," -f1 file.csv
```

| Flag | Purpose                         |
| ---- | ------------------------------- |
| `-d` | Delimiter (separator character) |
| `-f` | Field / column number           |

> Very useful for **log parsing** and working with CSV data.

---

### `sort` – Sort Lines

```bash
sort file.txt           # alphabetical sort
sort -n numbers.txt     # numeric sort
sort -r file.txt        # reverse order
```

---

### `tee` – Output to Screen + File

```bash
ls | tee output.txt
```

> Displays output on screen **and** saves it to a file simultaneously. Super handy in scripting! 🛠️

---

### `diff` – Compare Two Files

```bash
diff file1 file2
```

> Shows differences **line by line**. Heavily used in DevOps & version control.

---

## 🔗 6. Links in Linux

### `ln` – Hard Link

```bash
ln file1 hardlink1
```

- Shares the **same inode** as the original
- If the original is deleted → **hard link still works** ✅

---

### `ln -s` – Soft (Symbolic) Link

```bash
ln -s file1 symlink1
```

- **Points to** the original file's path
- If the original is deleted → **link breaks** ❌

> 🔎 Check inodes with: `ls -li`

---

## 📝 7. `vi` Editor _(Very Important!)_

### Modes in `vi`:

| Mode        | Purpose                   |
| ----------- | ------------------------- |
| **Normal**  | Default mode (navigation) |
| **Insert**  | Type / edit text          |
| **Command** | Save, quit, etc.          |

### Opening a file:

```bash
vi file.txt
```

### Essential Commands:

| Action               | Command |
| -------------------- | ------- |
| Enter Insert mode    | `i`     |
| Save                 | `:w`    |
| Quit                 | `:q`    |
| Save & Quit          | `:wq`   |
| Force Quit (no save) | `:q!`   |

> Press **`Esc`** to return to Normal mode anytime.

---

## 🔐 8. Remote Access

### `ssh` – Secure Shell

```bash
ssh user@server_ip
```

**Example:**

```bash
ssh ubuntu@192.168.1.10
```

> Widely used for connecting to **cloud servers** like AWS EC2 instances.

---

## 💾 9. Disk Usage Commands

### `df` – Disk Free

```bash
df -h
```

> Shows disk usage of all **mounted file systems** in a human-readable format.

---

### `du` – Disk Usage (Directory Size)

```bash
du -sh foldername
```

| Flag | Purpose                     |
| ---- | --------------------------- |
| `-s` | Summary (total size only)   |
| `-h` | Human-readable (KB, MB, GB) |

---

## ⚙ 10. Process Management

### `ps` – Process Status

```bash
ps          # your processes
ps aux      # all running processes (detailed)
```

---

### `top` – Live Process Monitor

```bash
top
```

Shows in real-time:

- 🖥️ CPU usage
- 🧠 Memory usage
- 📋 Running processes

> Press `q` to quit.

---

### `kill` – Kill a Process

```bash
kill PID
kill -9 PID     # force kill (SIGKILL)
```

> Find the PID using `ps aux` or `top` first.

---

### `fuser` – Find Process Using a Port

```bash
fuser 8080/tcp
```

> Super useful when a **port is already in use** and you need to find out why.

---

### `nohup` – Run in Background

```bash
nohup python app.py &
```

> Keeps the process running **even after you logout**. Perfect for long-running scripts.

---

### `free` – Memory Usage

```bash
free -h
```

> Shows total, used, and available **RAM** in a readable format.

---

### `vmstat` – System Performance Stats

```bash
vmstat
```

> Shows CPU, Memory, and I/O statistics at a glance.

---

## 🧹 Bonus: `clear`

```bash
clear
```

> Clears your terminal screen. A fresh start! ✨

---

## 🧪 Recommended Hands-On Practice Plan

Try this step-by-step to build muscle memory:

1. 📂 Create a test directory with `mkdir`
2. 📄 Create some files inside with `touch`
3. 🔄 Practice `cp`, `mv`, and `rm`
4. 🔗 Create hard & soft links with `ln`
5. 👀 Monitor a log file using `tail -f`
6. 🏃 Run a background process with `nohup`
7. 🔪 Kill it using `kill`
8. 💾 Check memory & disk usage with `free -h` and `df -h`

---

## 🎯 Must-Know Commands for Cloud / DevOps

If you're aiming for **Cloud Engineering**, focus deeply on these:

| Command              | Why It Matters                 |
| -------------------- | ------------------------------ |
| `ssh`                | Connect to remote servers      |
| `ps`, `top`, `kill`  | Manage running processes       |
| `df`, `du`           | Monitor disk space             |
| `tail -f`            | Real-time log monitoring       |
| `ln`                 | Understand file linking        |
| `cut`, `sort`, `tee` | Parse and process text/logs    |
| `nohup`              | Run persistent background jobs |

> These commands are **heavily used on production servers** every single day. Master them! 💪

---

> _Happy Learning! 🐧✨ — You've got this!_
