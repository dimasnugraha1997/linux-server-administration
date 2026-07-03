<div align="center">

# 🐧 Linux Server Administration

### My Linux System Administration Learning Portfolio

Learning Linux from the fundamentals through hands-on practice using Ubuntu Virtual Machine.

<img src="https://img.shields.io/badge/Linux-Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white">
<img src="https://img.shields.io/badge/Bash-Scripting-121011?style=for-the-badge&logo=gnu-bash&logoColor=white">
<img src="https://img.shields.io/badge/Status-Learning-success?style=for-the-badge">

</div>

---

# 📖 About

This repository documents my journey in learning Linux System Administration.

The objective is **not only to memorize commands**, but to understand how Linux works internally through real-world practice.

Topics covered include:

* User Management
* Group Management
* Linux Permissions
* Home Directory Backup
* Bash Automation
* File Management
* System Administration

---

# 📂 Repository Structure

```text
linux-server-administration/
│
├── README.md
│
└── user-management/
    ├── create-user.sh
    ├── delete-user.sh
    └── backup-home.sh
```

---

# 🎯 Learning Progress

| Module             | Status |
| ------------------ | :----: |
| Linux User         |    ✅   |
| Linux Group        |    ✅   |
| User Permission    |    ✅   |
| Create User        |    ✅   |
| Backup Home        |    ✅   |
| Delete User        |    ✅   |
| Bash Automation    |   🔄   |
| File Permission    |    ⏳   |
| Cron Job           |    ⏳   |
| Process Management |    ⏳   |

---

# 👤 Module 1 — Linux Users

A Linux user is an account that can authenticate and interact with the operating system.

### Useful Commands

```bash
whoami
id
echo $HOME
cat /etc/passwd
```

### Every user has

* Username
* UID
* Primary Group
* Home Directory
* Login Shell

---

# 👥 Module 2 — Linux Groups

Groups simplify permission management by allowing multiple users to share the same privileges.

### Examples

```text
sudo
docker
cdrom
www-data
```

### Useful Commands

```bash
groups
groups dimas
id dimas
cat /etc/group
getent group sudo
```

### Example

```bash
sudo usermod -aG docker dimas
```

Meaning

| Option  | Description          |
| ------- | -------------------- |
| usermod | Modify existing user |
| -a      | Append               |
| -G      | Secondary Group      |
| docker  | Group name           |
| dimas   | Username             |

---

# ➕ Module 3 — Create User

### Create a User

```bash
sudo adduser budi
```

### Verification

```bash
id budi
groups budi
ls -ld /home/budi
```

### Linux Automatically Creates

* User Account
* UID
* Primary Group
* Home Directory
* Password Entry
* Default Files from `/etc/skel`

---

# 💾 Module 4 — Backup Home Directory

### Backup Command

```bash
sudo tar -czvf backup-budi.tar.gz /home/budi
```

### Explanation

| Option             | Meaning            |
| ------------------ | ------------------ |
| sudo               | Run as root        |
| tar                | Archive utility    |
| -c                 | Create archive     |
| -z                 | Compress with gzip |
| -v                 | Verbose output     |
| -f                 | Output filename    |
| backup-budi.tar.gz | Backup archive     |
| /home/budi         | Source directory   |

### Verify Backup

```bash
tar -tzf backup-budi.tar.gz
```

---

# ❌ Module 5 — Delete User

Delete user only

```bash
sudo deluser budi
```

Delete user and home directory

```bash
sudo deluser --remove-home budi
```

### Recommended Workflow

```text
Create User
      │
      ▼
Use System
      │
      ▼
Backup Home Directory
      │
      ▼
Verify Backup
      │
      ▼
Delete User
```

---

# 📚 Key Concepts

| Concept        | Description                               |
| -------------- | ----------------------------------------- |
| User           | Identity used to log in                   |
| Root           | Full administrative privileges            |
| sudo           | Execute commands as root                  |
| Group          | Collection of permissions shared by users |
| Home Directory | Personal workspace for each user          |

---

# 🛠 Practice Scripts

| Script         | Description                    |
| -------------- | ------------------------------ |
| create-user.sh | Create a new Linux user        |
| delete-user.sh | Delete an existing user        |
| backup-home.sh | Backup a user's home directory |

---

# 🚀 Future Topics

* Bash Scripting
* chmod
* chown
* chgrp
* ACL
* Cron Job
* SSH Administration
* Service Management
* Package Management
* Log Management

---

<div align="center">

### ⭐ If you find this repository useful, feel free to leave a star.

**Learning by Doing • Linux System Administration**

</div>
