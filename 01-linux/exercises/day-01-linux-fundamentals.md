# Day 01 — Linux Fundamentals

## Environment

- WSL 2
- Ubuntu 26.04 LTS
- Bash

## Topics Practiced

### Linux Environment

- Linux distribution and kernel basics
- WSL filesystem
- Linux home directory
- Root filesystem

### Navigation

- `pwd`
- `cd`
- `ls`
- `ls -l`
- `ls -la`

### Files and Directories

- `mkdir`
- `touch`
- `cp`
- `mv`
- `rm`
- `rmdir`
- `find`

### File Inspection

- `cat`
- `less`
- `head`
- `tail`

### Text Processing

- `echo`
- `grep`
- Pipes (`|`)
- Output redirection (`>`)
- Append redirection (`>>`)

### System Inspection

- `whoami`
- `uname`
- `which`
- `whereis`
- `man`
- `df`
- `du`

## Filesystem Lab

Created the following environment:

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

## Log Analysis Exercise

Example log:

```text
INFO Server started
INFO User connected
WARNING CPU usage high
ERROR Database timeout
INFO Request completed
WARNING Memory usage high
ERROR Service unavailable
INFO Server stopped
```

Practiced filtering and inspecting logs using commands such as:

```bash
grep "WARNING" logs/system.log
grep "ERROR" logs/system.log
grep "ERROR" logs/system.log | head -n 1
tail -n 3 logs/system.log
```

## Key Takeaways

- Understand the difference between absolute and relative paths.
- Use `~`, `.`, and `..` to navigate the filesystem.
- Use pipes to connect commands.
- Use `>` carefully because it overwrites existing content.
- Use `>>` to append content.
- Verify paths before deleting files with `rm`.
- Use `grep`, `head`, and `tail` for basic log investigation.
- Use `which` to locate executables available through the shell's `PATH`.
- Use `df` to inspect filesystem disk usage.
- Use `du` to inspect file and directory disk usage.

## Commands Practiced

```bash
whoami
pwd
uname -a
cat /etc/os-release

cd ~
cd /
cd ..
ls
ls -l
ls -la

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

## Shell Concepts Practiced

```text
/     Root directory
~     User home directory
.     Current directory
..    Parent directory

>     Redirect output and overwrite
>>    Redirect output and append
|     Pipe output to another command
```

## Final Challenge

The final exercise combined navigation, executable discovery, disk usage inspection, log filtering, and pipelines.

Example:

```bash
pwd
cd ~
du -sh ~/ai-platform-lab
which grep
grep "INFO" ai-platform-lab/logs/system.log | head -n 2
tail -n 3 ai-platform-lab/logs/system.log
```

## Learning Approach

**Learn → Build → Break → Debug → Document**

During the exercises, an incorrect relative path produced a `No such file or directory` error. The issue was identified by checking the current working directory and correcting the path.

This reinforced the difference between absolute and relative paths and demonstrated basic Linux troubleshooting.

## Status

**Completed**
