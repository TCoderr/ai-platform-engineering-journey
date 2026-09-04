# Day 2 — Linux Users & Groups

## 🎯 Goal

Understand how Linux manages users and groups, how UID/GID values work, how primary and supplementary groups differ, and why production services should run with dedicated non-root service accounts.

---

## 📚 Topics Covered

- Linux users and usernames
- UID (User ID)
- GID (Group ID)
- Primary groups
- Supplementary groups
- Root user and UID 0
- `/etc/passwd`
- `/etc/shadow`
- `/etc/group`
- `whoami`, `id`, and `groups`
- `sudo` and `su`
- `useradd` vs `adduser`
- `usermod`
- `userdel`
- `groupadd` and `groupdel`
- `gpasswd`
- System and service users
- Principle of Least Privilege

---

## 1. User Identity

Linux identifies users internally using numerical UIDs.

```bash
whoami
id
groups
```

Example:

```text
uid=1050(airflow) gid=2000(data-platform) groups=2000(data-platform),998(docker),2100(ml-platform)
```

This means:

- Username: `airflow`
- UID: `1050`
- Primary group: `data-platform`
- Primary GID: `2000`
- Supplementary groups:
  - `docker` — GID `998`
  - `ml-platform` — GID `2100`

---

## 2. Root User

The `root` user is the Linux superuser.

```bash
id root
```

Example:

```text
uid=0(root) gid=0(root) groups=0(root)
```

The important identifier is:

```text
UID = 0
```

Commands can temporarily be executed with elevated privileges using:

```bash
sudo COMMAND
```

For example:

```bash
whoami
sudo whoami
```

Possible output:

```text
sinan
root
```

`sudo` does not permanently convert the current user into root. It executes the specified command with elevated privileges.

---

## 3. /etc/passwd

Linux user account information can be inspected through:

```bash
cat /etc/passwd
```

or:

```bash
getent passwd USER
```

Example:

```text
sinan:x:1000:1000::/home/sinan:/bin/bash
```

The seven fields are:

```text
username:x:UID:GID:GECOS:home:shell
```

Meaning:

1. Username
2. Password placeholder
3. UID
4. Primary GID
5. GECOS / user information
6. Home directory
7. Login shell

---

## 4. /etc/shadow

The `x` inside `/etc/passwd` indicates that password authentication information is stored separately in:

```text
/etc/shadow
```

Unlike `/etc/passwd`, `/etc/shadow` is heavily restricted.

For example:

```bash
cat /etc/shadow
```

as a normal user should result in a permission error.

Privileged inspection requires elevated permissions.

> Password hashes or `/etc/shadow` contents should never be shared publicly or committed to Git.

---

## 5. Groups

Group information can be inspected with:

```bash
cat /etc/group
```

or:

```bash
getent group GROUP
```

Example:

```text
sudo:x:27:sinan
```

The structure is:

```text
group_name:x:GID:members
```

---

## 6. Primary vs Supplementary Groups

Every Linux user has one primary group.

A user can additionally belong to multiple supplementary groups.

Example:

```text
uid=1050(airflow) gid=2000(data-platform) groups=2000(data-platform),998(docker),2100(ml-platform)
```

Primary group:

```text
data-platform
```

Supplementary groups:

```text
docker
ml-platform
```

The primary group is identified by the `gid=` field.

---

## 7. Creating Groups

Groups can be created using:

```bash
sudo groupadd ml-engineers
sudo groupadd platform-engineers
```

Verify them using:

```bash
getent group ml-engineers
getent group platform-engineers
```

---

## 8. useradd vs adduser

During the lab, users were created using both:

```bash
sudo useradd mluser
```

and:

```bash
sudo adduser platformuser
```

With the options used during the lab, `useradd` created the account but did not physically create:

```text
/home/mluser
```

The account still contained a configured home path.

`adduser` provided an interactive workflow and created the user's home directory automatically.

This demonstrated an important distinction between account metadata and the physical existence of a home directory.

---

## 9. Adding Users to Supplementary Groups

A user can be added to a supplementary group using:

```bash
sudo usermod -aG GROUP USER
```

Example:

```bash
sudo usermod -aG ml-engineers mluser
```

The important flags are:

```text
-a = append
-G = supplementary groups
```

Therefore:

```bash
sudo usermod -aG monitoring airflow
```

adds `airflow` to `monitoring` while preserving its existing supplementary groups.

---

## 10. The Danger of usermod -G

This command:

```bash
sudo usermod -G monitoring airflow
```

is different.

Without `-a`, the user's supplementary group list is replaced.

For example, if the user originally belongs to:

```text
docker
ml-platform
```

running:

```bash
sudo usermod -G monitoring airflow
```

can leave the user with only:

```text
monitoring
```

Therefore, accidentally forgetting `-a` can remove important access privileges.

---

## 11. Changing the Primary Group

The primary group can be changed using:

```bash
sudo usermod -g GROUP USER
```

Example:

```bash
sudo usermod -g ml-engineers mluser
```

After the change:

```text
uid=1001(mluser) gid=1001(ml-engineers) groups=1001(ml-engineers)
```

Here:

```text
ml-engineers
```

is now the primary group of `mluser`.

---

## 12. Removing a User from a Supplementary Group

A supplementary group membership can be removed using:

```bash
sudo gpasswd -d USER GROUP
```

Example:

```bash
sudo gpasswd -d platformuser platform-engineers
```

Verification:

```bash
id platformuser
getent group platform-engineers
```

---

## 13. Group Deletion Dependencies

An important behavior was observed during the lab.

`ml-engineers` was configured as the primary group of `mluser`.

Attempting:

```bash
sudo groupdel ml-engineers
```

resulted in:

```text
groupdel: cannot remove the primary group of user 'mluser'
```

Linux prevented the deletion because the group was still being used as a user's primary group.

This demonstrates an important dependency:

```text
mluser
   |
   | primary GID
   v
ml-engineers
```

The dependency must be removed before the group can be safely deleted.

---

## 14. Deleting Users

A user can be deleted with:

```bash
sudo userdel USER
```

Example:

```bash
sudo userdel mluser
```

This removes the user account but does not necessarily remove all related filesystem data or groups.

To remove the user and their home directory:

```bash
sudo userdel -r USER
```

Example:

```bash
sudo userdel -r platformuser
```

After deletion:

```bash
id platformuser
```

returned:

```text
id: 'platformuser': no such user
```

and:

```bash
ls -ld /home/platformuser
```

returned:

```text
ls: cannot access '/home/platformuser': No such file or directory
```

This confirmed that both the account and home directory had been removed.

---

## 15. Deleting Groups

Groups can be deleted using:

```bash
sudo groupdel GROUP
```

Example:

```bash
sudo groupdel ml-engineers
```

Verification:

```bash
getent group ml-engineers
```

If no output is returned, the group no longer exists.

---

## 16. Service Users

Production services should generally not run as `root`.

Instead, dedicated service users should be created.

Example:

```text
mlflow:x:991:991:MLflow Service:/var/lib/mlflow:/usr/sbin/nologin
```

This service account:

- Has its own UID
- Has its own GID
- Has a dedicated service directory
- Cannot normally open an interactive login shell

Service accounts often use shells such as:

```text
/usr/sbin/nologin
```

or:

```text
/bin/false
```

---

## 17. Principle of Least Privilege

A core production security principle is:

> Give users and services only the permissions they actually need.

Running every service as root dramatically increases the potential impact of a vulnerability.

Instead:

```text
Application
    ↓
Dedicated Service User
    ↓
Only Required Permissions
```

If the service is compromised, the attacker's access is constrained by the permissions of that service account.

This reduces the system's potential blast radius.

This concept is important for:

- Linux servers
- Docker containers
- Kubernetes workloads
- CI/CD runners
- MLflow
- Airflow
- Model serving systems
- Data pipelines
- Production AI/ML platforms

---

## 🧪 Commands Practiced

```bash
whoami
id
groups

cat /etc/passwd
cat /etc/group

getent passwd USER
getent group GROUP

sudo whoami

sudo useradd USER
sudo adduser USER

sudo groupadd GROUP

sudo usermod -g GROUP USER
sudo usermod -aG GROUP USER

sudo gpasswd -d USER GROUP

sudo userdel USER
sudo userdel -r USER

sudo groupdel GROUP
```

---

## 🔑 Key Takeaways

- Linux identifies users internally using UIDs.
- Linux identifies groups internally using GIDs.
- Every user has one primary group.
- Users can belong to multiple supplementary groups.
- `/etc/passwd` contains account information.
- Password authentication information is protected in `/etc/shadow`.
- `/etc/group` contains group information.
- UID `0` represents the root user.
- `sudo` allows controlled execution of privileged commands.
- `usermod -aG` preserves existing supplementary groups.
- `usermod -G` can replace existing supplementary group memberships.
- A group cannot normally be deleted while it is still someone's primary group.
- `userdel -r` can remove both the account and its home directory.
- Production services should use dedicated non-root service users.
- Least privilege reduces the blast radius of a compromised service.

---

## 🔗 AI/ML Platform Engineering Connection

Users and groups are foundational concepts for production AI/ML infrastructure.

The same ideas appear later in:

```text
Linux Users / Groups
        ↓
File Permissions
        ↓
Service Accounts
        ↓
Docker Non-Root Containers
        ↓
CI/CD Runners
        ↓
Kubernetes Security Contexts
        ↓
Production ML Platforms
```

Understanding UID, GID, service users, and least privilege is therefore not just Linux administration knowledge — it is part of building secure production AI/ML systems.

---

## ✅ Day 2 Completed

**Linux Users & Groups**

Next:

**Day 3 — Permissions & Ownership**

Topics:

- `r`, `w`, `x`
- User / Group / Others
- `chmod`
- Numeric permissions (`755`, `644`, `600`)
- `chown`
- `chgrp`
- `umask`
- Permission troubleshooting
