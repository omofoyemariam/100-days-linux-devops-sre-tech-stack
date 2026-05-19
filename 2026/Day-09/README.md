# Module 02 – Linux Filesystem
## Student Task Guide (Day 09)

> Based on Linux Filesystem class notes and lab discussions. 
> May 17th, 2026

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | [Understanding the Linux Filesystem](#task-1---understanding-the-linux-filesystem) |
| 2 | [Explore the Root Filesystem](#task-2---explore-the-root-filesystem) |
| 3 | [Understanding Linux Users and Prompts](#task-3---understanding-linux-users-and-prompts) |
| 4 | [Install and Use the tree Command](#task-4---install-and-use-the-tree-command) |
| 5 | [Linux Filesystem Layers](#task-5---linux-filesystem-layers) |
| 6 | [Practice the ls Command](#task-6---practice-the-ls-command) |
| 7 | [Understanding Metadata and Inodes](#task-7---understanding-metadata-and-inodes) |
| 8 | [Filesystem Snapshot Activity](#task-8---filesystem-snapshot-activity) |
| 9 | [Absolute vs Relative Paths](#task-9---absolute-vs-relative-paths) |
| 10 | [Linux Boot Process](#task-10---linux-boot-process) |
| 11 | [Explore the /boot Directory](#task-11---explore-the-boot-directory) |
| 12 | [BIOS vs UEFI](#task-12---bios-vs-uefi) |
| 13 | [POST and Hardware Checks](#task-13---post-and-hardware-checks) |
| 14 | [Bootloader and Kernel](#task-14---bootloader-and-kernel) |
| 15 | [Systemd Targets](#task-15---systemd-targets) |
| 16 | [Shutdown and Reboot Commands](#task-16---shutdown-and-reboot-commands) |
| 17 | [Understanding /home](#task-17---understanding-home) |
| 18 | [Understanding /dev](#task-18---understanding-dev) |
| 19 | [Block Devices vs Character Devices](#task-19---block-devices-vs-character-devices) |
| 20 | [TTY and Pseudo Terminals](#task-20---tty-and-pseudo-terminals) |
| 21 | [Disk Commands Practice](#task-21---disk-commands-practice) |
| 22 | [Sensors in Linux](#task-22---sensors-in-linux) |
| 23 | [Understanding /etc](#task-23---understanding-etc) |
| 24 | [Understanding /var](#task-24---understanding-var) |
| 25 | [Linux Logging System](#task-25---linux-logging-system) |
| 26 | [Understanding logrotate](#task-26---understanding-logrotate) |
| 27 | [Final Reflection](#task-27---final-reflection) |

---

# Task 1 - Understanding the Linux Filesystem

## Objective

Understand the Linux filesystem structure. Review the class notes.

## Instructions

Answer the following from the class notes:

1. What is a filesystem?
2. What is the root directory `/`?
3. Why is Linux called a hierarchical filesystem?
4. What is the purpose of directories?

---

# Task 2 - Explore the Root Filesystem

## Objective

Learn important Linux directories.

## Instructions


Review Notes to explain the purpose of:

- /boot
- /home
- /etc
- /dev
- /var
- /tmp
- /usr
- /proc

---

# Task 3 - Understanding Linux Users and Prompts

## Objective

Understand different types of users:
- root user
- sudo user
- regular/normal user

## Instructions

Observe the shell prompts "#" and "$"

Examples:

```bash
[root@hostname ~]#
[user@hostname ~]$ sudo
[tester@hostname ~]$ 
```

## Questions

1. Difference between root and regular user?
2. What is sudo?
3. Which symbol represents the root user?
4. Which symbol represents a normal user?

---

# Task 4 - Install and Use the tree Command

## Objective

Visualize directory structures.

## Instructions

Install tree:

```bash
dnf install tree -y
```

Run:

```bash
tree -d /boot
tree /boot
tree -a -L 2 -h -C
```

## Questions

1. What does `tree -d` show?
2. What does `-L 2` mean?
3. Why is the tree command useful?

---

# Task 5 - Linux Filesystem Layers

## Objective

Understand filesystem architecture.

## Instructions

Research the following:

1. Logical File System
2. Virtual File System (VFS)
3. Physical File System

## Questions

1. What is VFS?
2. Why is `/proc/cpuinfo` considered virtual data?


---

# Task 6 - Practice the ls Command

## Objective

Learn file listing commands.

## Instructions

Run:

```bash
ll
ls -l /
ls -ld /
ls -al /
ls -il /
```

## Questions

1. Difference between `ls -l /` and `ls -ld /`?
2. What does `-i` display?
3. What is metadata?

---

# Task 7 - Understanding Metadata and Inodes

## Objective

Understand how Linux tracks files.

## Instructions

Research:

- Metadata
- Inodes

## Questions

1. What information does an inode store?
2. Does an inode store file data?
3. Why are inodes important?

## Commands 
Run:
```bash
df -i
ls -il
stat /boot
```

---

# Task 8 - Filesystem Snapshot Activity

## Objective

Understand the Linux filesystem tree.

## Instructions

Draw the Linux filesystem hierarchy.

Include:

- /
- /boot
- /home
- /etc
- /dev
- /usr
- /var
- /tmp

---

# Task 9 - Absolute vs Relative Paths

## Objective

Understand navigation in Linux.

## Instructions

Practice:

```bash
pwd
cd /home
cd ..
cd .
```

## Questions

1. What is an absolute path?
2. What is a relative path?
3. Practice one example of each.

---

# Task 10 - Linux Boot Process

## Objective

Introduce where Boot system files are located. The booting process will be discussed in detail in a seperate "Linux Boot Process" class



## Question

What happens if the bootloader is corrupted? This is a real world problem. We will address this question when we learn about Boot Process in the future

---

# Task 11 - Explore the /boot Directory

## Objective

Understand boot-related files.

## Instructions

Run:

```bash
ls -l /boot
tree -d /boot
```

## Questions

Find and explain:

- grub.cfg
- initramfs
- vmlinuz
- System.map

---

# Task 12 - BIOS vs UEFI

## Objective

These slides were added to give you all clarity


---

# Task 13 - POST and Hardware Checks

## Objective

Understand POST.

## Questions

What does POST check?

- CPU
- RAM
- Storage
- Keyboard
- GPU

## Bonus

What happens if RAM fails during POST?

---

# Task 14 - Bootloader and Kernel

## Objective

We will learn in detail about GRUB and Kernel.

---

# Task 15 - Systemd Targets

## Objective

We will learn later in this course about Linux targets and runlevels.

---

# Task 16 - Shutdown and Reboot Commands

## Objective

Practice power management commands.

## Instructions

Research the following:

```bash
systemctl reboot
shutdown -r now
systemctl poweroff

```

## Questions

1. Difference between reboot and poweroff?
2. What does `shutdown -c` do?

---

# Task 17 - Understanding /home

## Objective

Understand user home directories.

## Questions

1. What is the purpose of `/home`?
2. Where does a user land after login?
3. Why are initialization files important?

---

# Task 18 - Understanding /dev

## Objective

Learn about device files.

## Instructions

Run:

```bash
ls /dev
ls -l /dev/sda1
```

## Questions

1. Why is everything treated as a file in Linux?
2. What is `/dev/sda`?
3. What is udev?

---

# Task 19 - Block Devices vs Character Devices

## Objective

Understand Linux device types.

## Questions

1. Just appreciate that there is a difference between block devices and character devices?
2. Hard Drives and block devices. 

---

# Task 20 - TTY and Pseudo Terminals

## Objective

Understand Linux terminals.

## Instructions

Run:

```bash
tty
w
who
ls /dev/pts
```

## Questions

1. What is tty1?
2. What is pts/0?
3. What does the `w` command display?

---

# Task 21 - Disk Commands Practice

## Objective

Practice storage commands.

## Instructions

Run:

```bash
df -hT
lsblk
fdisk -l
```


---

# Task 22 - Sensors in Linux

## Objective

Monitor hardware sensors.

## Instructions

Install sensors:

```bash
dnf install lm_sensors -y
```

Run:

```bash
sensors-detect
sensors
```

## Questions

1. What does lm_sensors do?
2. Why are sensors important in data centers?

---

# Task 23 - Understanding /etc

## Objective

Understand Linux configuration files.

## Instructions

Run:

```bash
ls /etc
```

## Questions

We will learn how User information is managed by Linux later in this course:

- /etc/passwd
- /etc/shadow
- /etc/group
- /etc/sudoers

## Bonus

Why should `/etc` always be backed up?

---

# Task 24 - Understanding /var

## Objective

Understand variable data storage.

## Instructions

Run:

```bash
ls /var
```

## Questions

Research:

- /var/log
- /var/cache
- /var/tmp
- /var/spool

## Question

Why can `/var` grow very large?

---

# Task 25 - Linux Logging System

## Objective

Understand Linux logs.

## Instructions

Run:

```bash
journalctl
tail -f /var/log/messages
```

## Questions

1. Difference between rsyslog and journald?
2. What does journalctl do?
3. Where are logs stored?

---

# Task 26 - Understanding logrotate

## Objective

Introduction to log management.

## Instructions

Run:

```bash
cat /etc/logrotate.conf
ls /etc/logrotate.d/
```

## Questions

1. What is logrotate?
2. Why is log rotation important?
3. What happens if logs are never rotated?

---

# Task 27 - Final Reflection

## Objective

Reflect on your learning.

## Instructions

Write a short paragraph answering:

- What did you learn in Module 02?
- Which Linux directory was most interesting?
- Which command was most useful?
- Which topic was difficult?
- What would you like to practice more?

---
