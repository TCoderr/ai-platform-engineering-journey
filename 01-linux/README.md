# Linux

Hands-on Linux fundamentals and system administration for the AI/ML Platform Engineering roadmap.

## Objectives

- Understand the Linux filesystem and command line
- Manage files, directories, users, groups, and permissions
- Work with processes and system services
- Manage packages and shell environments
- Write practical Bash scripts
- Understand Linux networking and remote access
- Perform basic storage and system administration
- Troubleshoot common Linux system problems
- Build the Linux foundation required for Docker, AWS, Kubernetes, and AI/ML infrastructure

## Progress

- [x] Day 1 — Linux Fundamentals & Filesystem
- [ ] Day 2 — Users, Groups & Permissions
- [ ] Day 3 — Processes, Services & systemd
- [ ] Day 4 — Packages, Environment & Text Editors
- [ ] Day 5 — Bash Scripting
- [ ] Day 6 — Linux Networking, SSH & SCP
- [ ] Day 7 — Storage, Logs, Scheduling & Troubleshooting
- [ ] Day 8 — Production Final Lab & System Health Check

## Day 1 — Linux Fundamentals & Filesystem

Topics:

- Linux distribution and kernel fundamentals
- Linux filesystem hierarchy
- Absolute and relative paths
- Files and directories
- File inspection
- Text processing
- Pipes and redirection
- Basic system inspection
- Basic log analysis

Commands practiced:

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

**Status:** ✅ Completed

## Day 2 — Users, Groups & Permissions

Topics:

- Linux users and groups
- root user
- sudo
- File ownership
- Linux permissions
- chmod
- chown
- chgrp
- umask

**Status:** ⏳ Not Started

## Day 3 — Processes, Services & systemd

Topics:

- Processes and PIDs
- ps
- top
- kill
- Signals
- Foreground and background jobs
- nice and renice
- systemd
- systemctl
- journalctl
- Service troubleshooting

**Status:** ⏳ Not Started

## Day 4 — Packages, Environment & Text Editors

Topics:

- apt
- Package repositories
- Environment variables
- PATH
- Shell configuration
- Aliases
- nano
- Vim fundamentals

**Status:** ⏳ Not Started

## Day 5 — Bash Scripting

Topics:

- Bash scripts
- Variables
- Arguments
- Exit codes
- stdin / stdout / stderr
- Conditions
- Loops
- Functions
- Error handling
- `&&` and `||`
- `2>` and `2>&1`

**Status:** ⏳ Not Started

## Day 6 — Linux Networking, SSH & SCP

Topics:

- Network interfaces
- IP addresses
- Ports and sockets
- DNS
- Connectivity troubleshooting
- SSH
- SCP

Commands and tools:

```bash
ip
ss
ping
curl
dig
ssh
scp
```

**Status:** ⏳ Not Started

## Day 7 — Storage, Logs, Scheduling & Troubleshooting

Topics:

- Disk and filesystem inspection
- lsblk
- mount / umount
- /etc/fstab fundamentals
- Logs
- cron / crontab
- tar
- gzip / gunzip
- System troubleshooting
- Disk troubleshooting
- Service troubleshooting
- Network troubleshooting

**Status:** ⏳ Not Started

## Day 8 — Production Final Lab

Production-style Linux troubleshooting scenario combining the skills learned throughout the Linux track.

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
- Processes
- Services
- Network connectivity
- System health thresholds
- Exit codes

The final lab will require diagnosing system, service, disk, log, and network problems without step-by-step instructions.

**Status:** ⏳ Not Started

## Learning Approach

**Learn → Build → Break → Debug → Document**

Each day includes hands-on exercises and is documented under:

```text
01-linux/exercises/
```

Final scripts and automation will be stored under:

```text
01-linux/scripts/
```

## Current Status

**Linux Track:** In Progress  
**Completed:** Day 1 / 8  
**Next:** Day 2 — Users, Groups & Permissions
