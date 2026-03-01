# 📂 Linux File Management & Permissions Guide

Welcome to the quick reference guide for essential Linux commands related to file permissions, compression, and file transfer. This guide helps you manage files effectively and securely! 🚀

---

## 🔐 File Permission Commands

These commands help you manage who can read, write, or execute files and directories.

| Command  | Description                                                                                                | Example                    |
| :------- | :--------------------------------------------------------------------------------------------------------- | :------------------------- |
| `umask`  | Sets the default permissions for newly created files and directories.                                      | `umask 022`                |
| `ls -l`  | Lists files and directories in long format, displaying their current permissions, owner, and group.        | `ls -l report.txt`         |
| `chmod`  | **Ch**ange **mod**e. Modifies the read, write, and execute permissions of a file or directory.             | `chmod +x script.sh`       |
| `chown`  | **Ch**ange **own**er. Changes the user ownership of a file or directory.                                   | `chown alice file.txt`     |
| `chgrp`  | **Ch**ange **gr**ou**p**. Changes the group ownership of a file or directory.                              | `chgrp admins shared/`     |
| `stat`   | Displays detailed status of a file or file system, including precise permission octals and timestamps.     | `stat file.txt`            |
| `chattr` | **Ch**ange **attr**ibutes. Changes advanced file attributes on a Linux file system (e.g., make immutable). | `chattr +i important.conf` |
| `lsattr` | **L**i**s**t **attr**ibutes. Lists the advanced attributes of a file.                                      | `lsattr important.conf`    |

---

## 🗜️ Compression & Archiving Commands

Use these commands to bundle multiple files together and compress them to save space.

| Command   | Description                                                                                                                              | Example                               |
| :-------- | :--------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------ |
| `zip`     | Packages and compresses files into a `.zip` archive.                                                                                     | `zip archive.zip file1.txt file2.txt` |
| `gzip`    | Compresses a file, typically replacing it with a `.gz` file.                                                                             | `gzip backup.tar`                     |
| `gunzip`  | Decompresses files compressed with `gzip`.                                                                                               | `gunzip archive.gz`                   |
| `tar`     | **T**ape **ar**chive. Bundles multiple files and directories into a single archive file (often called a tarball). Can also extract them. | `tar -cvf backup.tar /var/log/`       |
| `tar -xf` | Extracts the contents of a `.tar` archive (often informally referred to as "untarring").                                                 | `tar -xf archive.tar`                 |
| `unzip`   | Extracts compressed files from a `.zip` archive.                                                                                         | `unzip archive.zip`                   |
| `bzip2`   | Compresses files using a block-sorting algorithm, often achieving better compression than `gzip`. Outputs a `.bz2` file.                 | `bzip2 largefile.txt`                 |
| `bunzip2` | Decompresses files that were compressed with `bzip2`.                                                                                    | `bunzip2 archive.bz2`                 |
| `xz`      | Compresses files yielding very high compression rates. Outputs an `.xz` file.                                                            | `xz database.sql`                     |
| `unxz`    | Decompresses files that were compressed with `xz`.                                                                                       | `unxz database.sql.xz`                |

---

## 🔄 File Transfer Commands

These commands let you securely transfer files between different machines over a network.

| Command | Description                                                                                                                       | Example                                   |
| :------ | :-------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------- |
| `scp`   | **S**ecure **C**o**p**y. Copies files securely between hosts on a network using SSH.                                              | `scp file.txt user@192.168.1.10:/tmp/`    |
| `rsync` | **R**emote **Sync**. Efficiently synchronizes and transfers files/directories locally and remotely, copying only the differences. | `rsync -avz folder/ user@server:/backup/` |
| `sftp`  | **S**ecure **F**ile **T**ransfer **P**rotocol. Interactive, secure file transfer program, similar to typical FTP clients.         | `sftp user@192.168.1.10`                  |
| `wget`  | Non-interactive network downloader. Great for downloading files directly from the web to your server.                             | `wget https://example.com/file.zip`       |
| `curl`  | Command line tool for transferring data with URLs. Highly versatile.                                                              | `curl -O https://example.com/file.zip`    |
