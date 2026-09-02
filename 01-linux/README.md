# Linux

Hands-on Linux fundamentals and system administration for the AI/ML Platform Engineering roadmap.

The goal of this track is to build a practical Linux foundation for Docker, AWS, Kubernetes, EKS, Data Engineering, MLOps, and AI Platform Engineering.

---

## Objectives

- Understand Linux architecture, distributions, and the filesystem
- Work efficiently with the Linux command line
- Navigate and manage files and directories
- Manage users and groups
- Understand permissions and ownership
- Work with processes and background jobs
- Manage Linux services with systemd
- Inspect and troubleshoot system logs
- Manage packages and shell environments
- Use terminal-based text editors
- Write practical Bash scripts
- Understand Linux networking fundamentals
- Use SSH for remote system administration
- Work with storage and filesystems
- Schedule recurring tasks
- Archive and compress files
- Troubleshoot common Linux system problems
- Automate basic Linux system health checks

---

# Progress

## Week 1 — Linux Fundamentals & System Administration

- [x] Day 1 — Linux Fundamentals & Filesystem
- [ ] Day 2 — Users & Groups
- [ ] Day 3 — Permissions & Ownership
- [ ] Day 4 — Processes & Jobs
- [ ] Day 5 — Services & systemd
- [ ] Day 6 — Packages & Environment
- [ ] Day 7 — Text Editors & Week 1 Lab

## Week 2 — Bash, Networking & Linux Operations

- [ ] Day 8 — Bash Fundamentals
- [ ] Day 9 — Bash Control Flow
- [ ] Day 10 — Bash Automation & Error Handling
- [ ] Day 11 — Linux Networking
- [ ] Day 12 — SSH & Remote Operations
- [ ] Day 13 — Storage, Scheduling & Operations
- [ ] Day 14 — Production Final Lab & System Health Check

---

# Week 1 — Linux Fundamentals & System Administration

## Day 1 — Linux Fundamentals & Filesystem

### Topics

- Linux distributions
- Linux kernel fundamentals
- WSL 2
- Ubuntu environment
- Linux filesystem hierarchy
- Root directory
- Home directory
- Absolute paths
- Relative paths
- Files and directories
- File inspection
- Text processing
- Pipes
- Output redirection
- Basic log analysis
- Basic system inspection

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

Created and managed:

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

Practiced basic log investigation:

```bash
grep "WARNING" logs/system.log
grep "ERROR" logs/system.log
grep "ERROR" logs/system.log | head -n 1
tail -n 3 logs/system.log
```

**Status:** ✅ Completed

---

## Day 2 — Users & Groups

### Topics

- Linux users
- Linux groups
- UID and GID
- Primary groups
- Supplementary groups
- root user
- sudo
- User information
- Creating users
- Creating groups
- Adding users to groups
- Password management
- User account fundamentals

### Commands

```bash
whoami
id
groups
who
sudo
useradd
usermod
userdel
groupadd
groupdel
passwd
getent
```

### Hands-On Goals

- Inspect the current user
- Inspect UID and GID information
- Create test users
- Create test groups
- Add users to supplementary groups
- Inspect group membership
- Understand root vs normal users
- Practice safe sudo usage

**Status:** ⏳ Not Started

---

## Day 3 — Permissions & Ownership

### Topics

- Linux permission model
- File ownership
- Group ownership
- Read permission
- Write permission
- Execute permission
- User / Group / Other
- Symbolic permissions
- Numeric permissions
- Changing ownership
- Changing group ownership
- Default permissions
- umask
- Directory permissions

### Commands

```bash
ls -l
chmod
chown
chgrp
umask
stat
```

### Permission Model

```text
r = read
w = write
x = execute

u = user
g = group
o = others
a = all
```

### Hands-On Goals

- Read Linux permission strings
- Modify permissions symbolically
- Modify permissions numerically
- Change file ownership
- Change group ownership
- Understand permissions on directories
- Experiment with umask

**Status:** ⏳ Not Started

---

## Day 4 — Processes & Jobs

### Topics

- Linux processes
- Process IDs (PID)
- Parent processes (PPID)
- Foreground processes
- Background processes
- Jobs
- Process signals
- Terminating processes
- Process priority
- nice values

### Commands

```bash
ps
ps aux
top
jobs
bg
fg
kill
pkill
pgrep
nice
renice
```

### Hands-On Goals

- Inspect running processes
- Identify process IDs
- Start background jobs
- Move jobs between foreground and background
- Send signals to processes
- Terminate processes safely
- Inspect and modify process priority

**Status:** ⏳ Not Started

---

## Day 5 — Services & systemd

### Topics

- Linux services
- Daemons
- systemd
- Units
- Service lifecycle
- Starting services
- Stopping services
- Restarting services
- Enabling services at boot
- Service status
- systemd logs
- Service troubleshooting

### Commands

```bash
systemctl
journalctl
```

### Hands-On Goals

- Inspect running services
- Start and stop a service
- Restart a service
- Enable and disable services
- Inspect service status
- Investigate failed services
- Read service logs with journalctl

**Status:** ⏳ Not Started

---

## Day 6 — Packages & Environment

### Topics

- Linux package management
- APT
- Package repositories
- Package metadata
- Installing packages
- Removing packages
- Updating package indexes
- Environment variables
- PATH
- Shell configuration
- Aliases

### Commands

```bash
apt
apt update
apt install
apt remove
apt search
env
printenv
export
echo $PATH
which
alias
unalias
```

### Hands-On Goals

- Search for packages
- Install and remove packages
- Inspect environment variables
- Create temporary environment variables
- Understand PATH
- Create shell aliases

**Status:** ⏳ Not Started

---

## Day 7 — Text Editors & Week 1 Lab

### Text Editors

- nano
- Vim fundamentals
- Editing configuration files
- Saving files
- Searching text
- Exiting safely

### Commands

```bash
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

### Week 1 Lab

The Week 1 lab will combine:

- Filesystem navigation
- File operations
- Users
- Groups
- Permissions
- Processes
- Services
- Package management
- Environment variables
- Text editing

The goal is to solve a small Linux administration scenario without step-by-step instructions.

**Status:** ⏳ Not Started

---

# Week 2 — Bash, Networking & Linux Operations

## Day 8 — Bash Fundamentals

### Topics

- Bash scripts
- Shebang
- Script execution
- Variables
- Environment variables
- Command substitution
- User input
- Command-line arguments
- Quoting
- Basic script structure

### Concepts

```bash
#!/bin/bash

$0
$1
$2
$@
$#
```

### Hands-On Goals

- Create executable Bash scripts
- Work with variables
- Read command-line arguments
- Use command substitution
- Accept basic user input

**Status:** ⏳ Not Started

---

## Day 9 — Bash Control Flow

### Topics

- Conditional statements
- if / elif / else
- test expressions
- case statements
- for loops
- while loops
- Functions
- Return values

### Concepts

```bash
if
elif
else
fi

case
esac

for
while
do
done

function
```

### Hands-On Goals

- Build conditional scripts
- Validate input
- Process multiple files with loops
- Create reusable Bash functions
- Build simple automation logic

**Status:** ⏳ Not Started

---

## Day 10 — Bash Automation & Error Handling

### Topics

- Exit codes
- stdin
- stdout
- stderr
- Error redirection
- Command chaining
- Script failure handling
- Defensive Bash scripting
- Logging from scripts

### Shell Operators

```text
>       stdout overwrite
>>      stdout append
2>      stderr redirection
2>&1    stderr → stdout
&&      execute if previous command succeeds
||      execute if previous command fails
```

### Important Concepts

```bash
$?
set -e
set -u
```

### Hands-On Goals

- Inspect exit codes
- Redirect errors
- Combine stdout and stderr
- Chain commands based on success/failure
- Build safer automation scripts
- Generate script logs

**Status:** ⏳ Not Started

---

## Day 11 — Linux Networking

### Topics

- Network interfaces
- IP addresses
- IPv4 fundamentals
- Public and private IP addresses
- Routes
- Default gateway
- Ports
- TCP and UDP
- Network sockets
- DNS
- HTTP/HTTPS connectivity
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
```

### Hands-On Goals

- Inspect network interfaces
- Identify local IP addresses
- Inspect routing information
- Inspect listening ports
- Test connectivity
- Perform DNS queries
- Test HTTP endpoints
- Diagnose basic network problems

**Status:** ⏳ Not Started

---

## Day 12 — SSH & Remote Operations

### Topics

- SSH
- Remote shell access
- SSH keys
- Public/private key authentication
- known_hosts
- SSH configuration
- Secure file transfer
- SCP
- Remote command execution
- Basic SSH troubleshooting

### Commands

```bash
ssh
ssh-keygen
ssh-copy-id
scp
```

### Hands-On Goals

- Understand SSH authentication
- Generate SSH keys
- Connect to a remote Linux environment
- Execute remote commands
- Transfer files securely
- Understand basic SSH security practices

**Status:** ⏳ Not Started

---

## Day 13 — Storage, Scheduling & Operations

### Storage

- Block devices
- Filesystems
- Disk usage
- Mount points
- Mounting
- Unmounting
- `/etc/fstab` fundamentals

### Scheduling

- cron
- crontab
- Recurring jobs

### Archives & Compression

- tar
- gzip
- gunzip
- zip/unzip fundamentals

### Logs & Operations

- System logs
- Application logs
- journalctl
- Disk troubleshooting
- Process troubleshooting
- Service troubleshooting
- Permission troubleshooting
- Network troubleshooting

### Commands

```bash
df
du
lsblk
mount
umount
crontab
tar
gzip
gunzip
journalctl
```

### Hands-On Goals

- Inspect storage devices
- Inspect disk usage
- Understand mount points
- Create scheduled jobs
- Create and extract archives
- Compress and decompress files
- Investigate system and application problems

**Status:** ⏳ Not Started

---

## Day 14 — Production Final Lab & System Health Check

The final day combines the entire Linux track in a production-style troubleshooting and automation scenario.

### Production Troubleshooting Lab

Diagnose a simulated Linux system containing problems such as:

- High disk usage
- Failed services
- Application errors
- Permission problems
- Process problems
- Network connectivity failures
- Log errors
- Misconfigured environment settings

The objective is to identify and resolve problems without step-by-step instructions.

---

## Final Project — System Health Check

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
- Warning conditions
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
+
Automation
```

**Status:** ⏳ Not Started

---

# Repository Structure

```text
01-linux/
├── README.md
├── exercises/
│   ├── day-01-linux-fundamentals.md
│   ├── day-02-users-groups.md
│   ├── day-03-permissions-ownership.md
│   ├── day-04-processes-jobs.md
│   ├── day-05-services-systemd.md
│   ├── day-06-packages-environment.md
│   ├── day-07-editors-week1-lab.md
│   ├── day-08-bash-fundamentals.md
│   ├── day-09-bash-control-flow.md
│   ├── day-10-bash-automation.md
│   ├── day-11-linux-networking.md
│   ├── day-12-ssh-remote-operations.md
│   ├── day-13-storage-operations.md
│   └── day-14-production-final-lab.md
└── scripts/
    └── system-health-check.sh
```

Files will be added progressively as each hands-on lab is completed.

---

# Learning Approach

**Learn → Build → Break → Debug → Document**

Each day combines concepts with hands-on terminal exercises.

The objective is not to memorize Linux commands. The objective is to understand how Linux systems behave, how to investigate problems, and how Linux is used in real cloud and platform engineering environments.

---

# Reference Curriculum

Primary reference:

**Linux Foundation — Introduction to Linux (LFS101)**

This track adapts the Linux Foundation curriculum for AI/ML Platform Engineering.

Desktop-oriented and low-priority topics are reduced, while greater emphasis is placed on:

- Command-line operations
- System administration
- Bash automation
- Networking
- Services
- Logs
- Remote administration
- Troubleshooting
- Production-oriented labs

---

# Current Status

**Track:** Linux  
**Duration:** 2 Weeks / 14 Days  
**Current Week:** Week 1  
**Completed:** Day 1 / 14  
**Current:** Day 2 — Users & Groups  
**Overall Status:** 🟡 In Progress
