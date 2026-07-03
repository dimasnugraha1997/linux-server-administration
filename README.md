Linux Server Administration

My personal learning journey to understand Linux System Administration from the fundamentals.

📌 About This Repository

This repository contains my hands-on practice while learning Linux System Administration using a Virtual Machine.

The goal is not only to collect Linux commands, but to understand:

How Linux manages users and groups
Why permissions exist
How system administrators manage accounts
How to automate repetitive tasks using Bash scripts

Every script in this repository is created after understanding the manual process first.

Repository Structure
linux-server-administration/
│
├── README.md
├── user-management/
│   ├── create-user.sh
│   ├── delete-user.sh
│   └── backup-home.sh
Learning Roadmap

Linux User

Linux Group

User Permissions

User Management

Home Directory Backup

Bash Automation

Cron Job

File Permission

Process Management

Module 1 — Understanding Users
What is a User?

A user is an account that can log in to a Linux system.

Example:

root
dimas
postgres
www-data

Each user has:

Username
UID (User ID)
Primary Group
Home Directory
Login Shell

Useful commands:

whoami
id
echo $HOME
cat /etc/passwd
Module 2 — Understanding Groups

Linux uses groups to manage permissions more efficiently.

Instead of assigning permissions one user at a time, permissions are usually assigned to groups.

Examples:

sudo
docker
cdrom
www-data

Useful commands:

groups
groups dimas
id dimas
cat /etc/group
getent group sudo

Example:

sudo usermod -aG docker dimas

Meaning:

usermod → Modify an existing user
-a → Append (don't remove existing groups)
-G → Secondary Group
docker → Group name
dimas → User
Module 3 — Create User

Manual command:

sudo adduser budi

What happens?

Create a new user
Create UID
Create GID
Create Home Directory
Copy default files from /etc/skel
Create password entry

Verification:

id budi
groups budi
ls -ld /home/budi
Module 4 — Backup Home Directory

Example:

sudo tar -czvf backup-budi.tar.gz /home/budi

Meaning:

Option	Description
sudo	Execute as root
tar	Archive utility
-c	Create archive
-z	Compress using gzip
-v	Show process
-f	Output filename
backup-budi.tar.gz	Backup file
/home/budi	Source directory

Check archive:

tar -tzf backup-budi.tar.gz
Module 5 — Delete User

Delete user only:

sudo deluser budi

Delete user including home directory:

sudo deluser --remove-home budi

Recommended workflow:

Create User
      ↓
User uses the system
      ↓
Backup Home Directory
      ↓
Verify Backup
      ↓
Delete User
Key Concepts Learned
User

A user is an identity used to log in to Linux.

Root

Root has unrestricted access to the entire system.

sudo

Allows a regular user to execute specific commands with root privileges.

Group

Groups are used to organize permissions.

A user may belong to multiple groups.

Examples:

dimas
sudo
docker
cdrom
Useful Commands
whoami
id
groups
groups dimas
cat /etc/passwd
cat /etc/group
getent group sudo
Practice Scripts

This repository will include:

create-user.sh
delete-user.sh
backup-home.sh

Each script is built from manual administration practices before being automated.

Future Learning
Bash Scripting
File Permission (chmod)
Ownership (chown)
Group Management
Cron Jobs
Process Management
SSH Administration
Service Management
Package Management
Log Management
Notes

This repository is part of my Linux System Administration learning portfolio.

Every topic is tested inside a VirtualBox virtual machine before being documented here.
