# 👥 Linux User & Group Management Commands

**Complete guide for managing users/groups. Always use `sudo` for admin tasks!**

## 🔐 Core Admin Commands

- **sudo**  
  Run commands as superuser/root.  
  `sudo command` → Execute with root privileges.  
  `sudo -u username command` → Run as specific user.  
  _Ex: `sudo apt update`_

## 🆕 User Management

- **useradd**  
  Create new user account.  
  `sudo useradd -m -s /bin/bash ravi` → Create user with home dir & bash shell.  
  `-m` = make home, `-s` = set shell.  
  _Check: `cat /etc/passwd | grep ravi`_

- **whoami**  
  Shows current username.  
  `whoami` → "ravi"  
  _Quick identity check._

- **passwd**  
  Change user password.  
  `sudo passwd ravi` → Set password for ravi.  
  `passwd` → Change your own password.  
  _Forces interactive input._

- **userdel**  
  Delete user account.  
  `sudo userdel -r ravi` → Delete user + home dir.  
  `-r` = remove home/mail.  
  _⚠️ Irreversible!_

## 👥 Group Management

- **groupadd**  
  Create new group.  
  `sudo groupadd developers` → New group "developers".  
  _Check: `cat /etc/group`_

- **gpasswd**  
  Manage group passwords/members.  
  `sudo gpasswd -a ravi developers` → Add ravi to developers.  
  `sudo gpasswd -d ravi developers` → Delete ravi from group.  
  `sudo gpasswd -M user1,user2 dev` → Set multiple members.  
  _`-a` = add, `-d` = delete, `-M` = members._

- **groupdel**  
  Delete group.  
  `sudo groupdel developers` → Remove group entirely.  
  _⚠️ Remove users first!_

## 🔍 Useful Helpers

| Command                  | Purpose                | Example                      |
| ------------------------ | ---------------------- | ---------------------------- |
| `id username`            | Show user/group IDs    | `id ravi`                    |
| `groups username`        | List user's groups     | `groups ravi`                |
| `usermod -aG group user` | Add to secondary group | `sudo usermod -aG sudo ravi` |
| `cat /etc/passwd`        | View all users         | Lists all accounts           |
| `cat /etc/group`         | View all groups        | Lists all groups             |
