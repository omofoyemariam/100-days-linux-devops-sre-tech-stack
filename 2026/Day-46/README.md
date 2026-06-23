# RHCSA User Management and Permissions
---
> Date Created: JUNE 22ND, 2026
> Exam Created by: RHCSA Certified Instructor - Muhammed Khalid Khan
---
# RHCSA Objectives Covered
Here are questions that evaluate your capability by RHCSA Exam!
✅ User Creation
✅ User Deletion
✅ Group Creation
✅ Group Deletion
✅ Secondary Groups
✅ Non-Interactive Shells
✅ Password Assignment
✅ Password Aging
✅ Passwordless Sudo
✅ Ownership
✅ Standard Permissions
✅ ACLs
✅ SGID
✅ Sticky Bit
✅ umask
✅ Collaborative Directories
✅ File Access Control
✅ User and Group Verification

---

# Table of Contents

1. User and Group Management
2. Q3 – ACLs and Directory Permissions
3. Q4 – Users, Groups, Shells, Passwords, and Sudo
4. Q5 – SGID Collaborative Directory
5. Q14 – Secondary Group Membership
6. Q17 – ACL Permissions
7. Q18 – Sticky Bit
8. Q19 – SGID Directory
9. Q22 – User Creation with UID
10. Q30 – umask
11. Q31 – Password Aging and Sudo
12. Special Permissions Summary
13. Symbolic Mode Examples
14. RHCSA User Management Commands

---

# User and Group Management

## Delete User

```bash
userdel -r jerry
```

If the user is logged in:

```bash
pkill -KILL -u jerry
userdel -r jerry
```

Or force deletion:

```bash
userdel -rf jerry
```

---

## Delete Group

```bash
groupdel developers
```

---

## Remove User from Group

```bash
gpasswd -d username groupname
```

---

# Q3 – ACLs and Directory Permissions

## Requirements

Create:

```text
/share/dev
```

Ownership:

```text
devuser:devteam
```

Permissions:

- devteam members should have rwx.
- user john should have read-only access via ACL.

## Solution

```bash
groupadd devteam
useradd devuser
useradd john

mkdir -p /share/dev

chown devuser:devteam /share/dev

chmod g=rwx /share/dev

setfacl -m u:john:r-- /share/dev

getfacl /share/dev
```

Expected:

```text
user::rwx
user:john:r--
group::rwx
mask::rwx
other::r-x
```

---

# Q4 – Users, Groups, Shells, Passwords, and Sudo

## Create Group

```bash
groupadd sysadm
```

## Create Users

```bash
useradd -G sysadm harry
useradd -G sysadm natasha
```

## Create User with Non-Interactive Shell

```bash
useradd -s /sbin/nologin sarah
```

---

## Set Passwords

```bash
echo "password" | passwd --stdin harry

echo "password" | passwd --stdin natasha

echo "password" | passwd --stdin sarah
```

---

## Sudo Privileges

Edit sudoers:

```bash
visudo
```

Allow sysadm members to create users:

```text
%sysadm ALL=(ALL) NOPASSWD: /usr/sbin/useradd
```

Allow harry to change passwords without entering sudo password:

```text
harry ALL=(ALL) NOPASSWD: /usr/bin/passwd [A-Za-z]*,!/usr/bin/passwd root
```

Verify:

```bash
su - harry

sudo passwd natasha
```

---

# Q5 – SGID Collaborative Directory

## Requirements

Create:

```text
/shared/sysadm
```

Requirements:

- Group owner = sysadm
- Members have rwx
- Others have no permissions
- New files inherit sysadm group ownership

## Solution

```bash
mkdir -p /shared/sysadm

groupadd sysadm

chgrp sysadm /shared/sysadm

chmod 2770 /shared/sysadm
```

Result:

```text
drwxrws---
```

### Meaning

```text
2 = SGID
770 = rwxrwx---
```

---

# Q14 – Secondary Group Membership

Create group:

```bash
groupadd IT-Team
```

Create user:

```bash
useradd -G IT-Team alex
```

Verify:

```bash
id alex

getent group IT-Team

getent passwd alex
```

Expected:

```text
uid=1013(alex)
gid=1017(alex)
groups=1017(alex),1016(IT-Team)
```

---

# Q17 – ACL Permissions

Copy file:

```bash
cp /etc/fstab /var/tmp/
```

Requirements:

- Owner = root
- Group = root
- Natasha should have read/write.
- Harry should have no permissions.
- Others should have read permission.

## Solution

```bash
setfacl -m u:natasha:rw- /var/tmp/fstab

setfacl -m u:harry:--- /var/tmp/fstab

getfacl /var/tmp/fstab
```

Expected:

```text
user::rw-
user:harry:---
user:natasha:rw-
group::r--
mask::rw-
other::r--
```

---

# Q18 – Sticky Bit

## Requirements

Create:

```text
/shared/projects
```

Owner:

```text
alex
```

Prevent users from deleting each other's files.

## Solution

```bash
mkdir -p /shared/projects

chown -R alex /shared/projects

chmod 1777 /shared/projects
```

Result:

```text
drwxrwxrwt
```

### Meaning

```text
1 = Sticky Bit
777 = rwxrwxrwx
```

Only the file owner and root can delete files.

---

# Q19 – SGID Directory

Create:

```bash
mkdir -p /root/d1
```

Apply SGID:

```bash
chmod 2775 /root/d1
```

Result:

```text
drwxrwsr-x
```

### Meaning

```text
2 = SGID
775 = rwxrwxr-x
```

New files inherit group ownership.

---

# Q22 – Create User with Specific UID

```bash
useradd -u 2334 unilao
```

Set password:

```bash
echo "ablerate" | passwd --stdin unilao
```

Alternative:

```bash
echo "unilao:ablerate" | chpasswd
```

Complete syntax:

```bash
useradd \
-u 2334 \
-d /home/unilao \
-s /bin/bash \
-g developers \
unilao
```

Options:

| Option | Description |
|----------|-------------|
| -u | UID |
| -d | Home directory |
| -s | Login shell |
| -g | Primary group |
| -G | Secondary groups |

---

# Q30 – umask

## Requirements

Files:

```text
-r--------
```

Directories:

```text
dr-x------
```

## Solution

Edit:

```bash
vi /home/natasha/.bashrc
```

Add:

```bash
umask 0266
```

Reload:

```bash
source ~/.bashrc
```

Test:

```bash
touch testfile

mkdir testdir

ls -l
```

Expected:

```text
-r--------
dr-x------
```

---

# Q31 – Password Aging

Edit:

```bash
vi /etc/login.defs
```

Set:

```text
PASS_MAX_DAYS 20
```

Verify:

```bash
chage -l username
```

---

# Q31 – Passwordless Sudo

Edit:

```bash
visudo
```

Add:

```text
%admin ALL=(ALL) NOPASSWD: ALL
```

---

# Special Permissions Summary

| Permission | Numeric Mode | Symbolic Mode | Example |
|------------|--------------|---------------|---------|
| SUID | 4755 | u+s | -rwsr-xr-x |
| SGID | 2775 | g+s | drwxrwsr-x |
| Sticky Bit | 1777 | +t | drwxrwxrwt |

---

# SUID Example

Numeric:

```bash
chmod 4755 file
```

Symbolic:

```bash
chmod u+s file
```

Result:

```text
-rwsr-xr-x
```

---

# SGID Example

Numeric:

```bash
chmod 2775 directory
```

Symbolic:

```bash
chmod g+s directory
```

Result:

```text
drwxrwsr-x
```

---

# Sticky Bit Example

Numeric:

```bash
chmod 1777 directory
```

Symbolic:

```bash
chmod +t directory
```

Result:

```text
drwxrwxrwt
```

---

# Common RHCSA User Management Commands

## User Management

```bash
useradd
usermod
userdel
passwd
chpasswd
chage
id
who
whoami
groups
```

---

## Group Management

```bash
groupadd
groupmod
groupdel
gpasswd
newgrp
getent group
```

---

## Ownership

```bash
chown
chgrp
```

---

## Permissions

```bash
chmod
umask
```

---

## ACL Commands

```bash
setfacl
getfacl
```

---

## Sudo Commands

```bash
visudo
sudo
sudo -l
```

---

## Information Commands

```bash
id
getent passwd
getent group
ls -l
ls -ld
```

---

