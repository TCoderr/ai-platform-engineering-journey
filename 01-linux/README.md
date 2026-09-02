# Linux

Hands-on Linux fundamentals and system administration for the AI/ML Platform Engineering roadmap.

## Objectives

- Understand the Linux filesystem and command line
- Navigate and manage files and directories efficiently
- Manage Linux users, groups, permissions, and ownership
- Work with processes, jobs, services, and systemd
- Manage packages and shell environments
- Use terminal-based text editors
- Write practical Bash scripts
- Understand Linux networking and remote access
- Work with storage, logs, archives, and scheduled tasks
- Troubleshoot common Linux system problems
- Build the Linux foundation required for Docker, AWS, Kubernetes, and AI/ML infrastructure

---

## Progress

- [ ] Week 1 — Linux CLI, Filesystem & System Fundamentals
- [ ] Week 2 — Linux Administration, Networking & Bash

### Current Progress

- [x] Day 1 — Linux Fundamentals & Filesystem
- [ ] Day 2 — Users, Groups & Permissions
- [ ] Day 3 — Processes, Services & systemd
- [ ] Day 4 — Packages, Environment & Text Editors
- [ ] Day 5 — Bash Scripting
- [ ] Day 6 — Linux Networking, SSH & SCP
- [ ] Day 7 — Storage, Logs, Scheduling & Troubleshooting
- [ ] Day 8 — Production Final Lab & System Health Check

---

# Week 1 — Linux CLI, Filesystem & System Fundamentals

## Day 1 — Linux Fundamentals & Filesystem

### Topics

- Linux distributions and kernel fundamentals
- WSL 2 and Ubuntu environment
- Linux filesystem hierarchy
- Root and home directories
- Absolute and relative paths
- Files and directories
- File inspection
- Text processing
- Pipes and redirection
- Basic system inspection
- Basic log analysis

### Commands Practiced

```bash
whoami
pwd
uname
ls
cd
mkdir
touch
cp
mv
rm
rmdir
find
cat
less
head
tail
echo
grep
which
whereis
man
df
du
```

### Shell Concepts

```text
/     Root directory
~     User home directory
.     Current directory
..    Parent directory

>     Redirect output and overwrite
>>    Redirect output and append
|     Pipe output to another command
```

### Hands-On Lab

Created and managed the following environment:

```text
ai-platform-lab/
├── README.md
├── configs/
│   ├── app.conf
│   └── database.conf
├── data/
│   └── input.csv
├── logs/
│   ├── application.log
│   └── system.log
└── scripts/
    ├── deploy.sh
    └── health-check.sh
```

Practiced basic log investigation using:

```bash
grep "WARNING" logs/system.log
grep "ERROR" logs/system.log
grep "ERROR" logs/system.log | head -n 1
tail -n 3 logs/system.log
```

**Status:** ✅ Completed

---

## Day 2 — Users, Groups & Permissions

### Topics

- Linux users and groups
- User and group IDs
- root user
- sudo
- File ownership
- Group ownership
- Linux permission model
- Read, write, and execute permissions
- Symbolic and numeric permissions
- Default permissions
- umask

### Commands

```bash
id
groups
who
sudo
useradd
usermod
groupadd
passwd
chmod
chown
chgrp
umask
```

**Status:** ⏳ Not Started

---

## Day 3 — Processes, Jobs, Services & systemd

### Topics

- Processes
- Process IDs (PID)
- Parent processes
- Foreground and background processes
- Jobs
- Signals
- Process termination
- Process priorities
- Linux services
- systemd
- Service management
- System logs
- Service troubleshooting

### Commands

```bash
ps
top
jobs
bg
fg
kill
pkill
nice
renice
systemctl
journalctl
```

**Status:** ⏳ Not Started

---

# Week 2 — Linux Administration, Networking & Bash

## Day 4 — Packages, Environment & Text Editors

### Topics

- Linux package management
- APT
- Package repositories
- Installing and removing packages
- Environment variables
- PATH
- Shell configuration
- Aliases
- nano
- Vim fundamentals

### Commands

```bash
apt
apt update
apt install
apt remove
env
export
echo $PATH
alias
nano
vim
```

### Vim Fundamentals

```text
i       Insert mode
Esc     Normal mode
:w      Save
:q      Quit
:wq     Save and quit
:q!     Quit without saving
```

**Status:** ⏳ Not Started

---

## Day 5 — Bash Scripting

### Topics

- Bash scripts
- Shebang
- Variables
- Environment variables
- Command-line arguments
- Exit codes
- stdin
- stdout
- stderr
- Conditions
- Loops
- Functions
- Command substitution
- Error handling
- Command chaining

### Shell Operators

```text
>       stdout overwrite
>>      stdout append
2>      stderr redirection
2>&1    stderr → stdout
&&      run next command if successful
||      run next command if previous command fails
```

### Bash Concepts

```bash
#!/bin/bash

$?
$1
$2
$@
$#
```

**Status:** ⏳ Not Started

---

## Day 6 — Linux Networking, SSH & SCP

### Topics

- Network interfaces
- IP addresses
- Public and private IP concepts
- Ports
- TCP and UDP fundamentals
- Network sockets
- DNS
- Connectivity testing
- HTTP requests
- Remote server access
- SSH
- Secure file transfer
- Basic network troubleshooting

### Commands

```bash
ip
ip addr
ip route
ss
ping
curl
dig
nslookup
hostname
ssh
scp
```

**Status:** ⏳ Not Started

---

## Day 7 — Storage, Logs, Scheduling & Troubleshooting

### Storage

- Filesystems
- Block devices
- Disk usage
- Mount points
- Mounting and unmounting
- `/etc/fstab` fundamentals

### Logs

- Linux system logs
- Application logs
- Log investigation
- journalctl
- Filtering logs

### Scheduling

- cron
- crontab
- Scheduled tasks

### Archives & Compression

- tar archives
- gzip
- gunzip
- zip/unzip fundamentals

### Troubleshooting

- Disk troubleshooting
- Process troubleshooting
- Service troubleshooting
- Log investigation
- Network troubleshooting
- Permission troubleshooting

### Commands

```bash
df
du
lsblk
mount
umount
journalctl
cron
crontab
tar
gzip
gunzip
```

**Status:** ⏳ Not Started

---

## Day 8 — Production Final Lab & System Health Check

The final day combines the Linux skills learned throughout both weeks in a production-style troubleshooting scenario.

### Production Troubleshooting Lab

Diagnose a simulated Linux server containing problems such as:

- High disk usage
- Failed services
- Application errors
- Permission problems
- Process problems
- Network connectivity failures
- Log errors

The goal is to investigate and resolve the problems without step-by-step instructions.

### Final Project

Build:

```text
system-health-check.sh
```

The script will inspect:

- CPU usage
- Memory usage
- Disk usage
- System uptime
- Running processes
- Important services
- Network connectivity
- System health thresholds
- Exit codes

The project will combine:

```text
Linux
+
Bash
+
Processes
+
Services
+
Networking
+
Storage
+
Logs
+
Troubleshooting
```

**Status:** ⏳ Not Started

---

# Repository Structure

```text
01-linux/
├── README.md
├── exercises/
│   ├── day-01-linux-fundamentals.md
│   ├── day-02-users-permissions.md
│   ├── day-03-processes-services.md
│   ├── day-04-packages-environment.md
│   ├── day-05-bash-scripting.md
│   ├── day-06-linux-networking.md
│   ├── day-07-operations-troubleshooting.md
│   └── day-08-final-lab.md
└── scripts/
    └── system-health-check.sh
```

Files will be added progressively as each lab is completed.

---

# Learning Approach

**Learn → Build → Break → Debug → Document**

The goal of this Linux track is not only to learn commands, but to understand how Linux systems behave and how to investigate problems in practical cloud and platform engineering environments.

---

# Reference

Primary reference curriculum:

**Linux Foundation — Introduction to Linux (LFS101)**

The learning track is adapted for AI/ML Platform Engineering. Low-priority desktop-oriented topics are reduced, while practical system administration, troubleshooting, networking, services, Bash, and production-oriented exercises are emphasized.

---

# Current Status

**Track:** Linux  
**Week:** Week 1  
**Completed:** Day 1 / 8  
**Current:** Day 2 — Users, Groups & Permissions  
**Overall Status:** 🟡 In Progress
