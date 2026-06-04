# Linux Lab 23 – Understanding Inodes and Inode Exhaustion

> May 31st, 2026

## Objective

In this lab, you will learn:

1. What an inode is.
2. How to view inode usage on a Linux filesystem.
3. The difference between disk space usage and inode usage.
4. How a filesystem can run out of inodes while still having free disk space.
5. How to safely simulate inode exhaustion in a lab environment.

---

# Background

Every file and directory in Linux has an associated **inode**.

An inode stores metadata about a file, including:

- File ownership
- Permissions
- File size
- Creation and modification times
- Location of data blocks on disk

The inode does **not** store the filename itself. The filename is stored in the directory entry.

### Important Concept

A filesystem can have:

- Plenty of free disk space
- Zero free inodes

When this happens, users cannot create new files even though disk space appears available.

---

# Task 1 – View Disk Space Usage

## Objective

Check available disk space on the system.

### Run

```bash
df -h
```

### Questions

1. What filesystems are displayed?
2. Which filesystem contains the root (`/`) directory?
3. How much disk space is available?

---

# Task 2 – View Inode Usage

## Objective

Check inode usage on the system.

### Run

```bash
df -i
```

### Questions

1. How many inodes are available?
2. How many inodes are currently in use?
3. What percentage of inodes are being used?

---

# Task 3 – Compare Disk Usage and Inode Usage

## Objective

Understand the difference between storage blocks and inodes.

### Run

```bash
df -h
```

and

```bash
df -i
```

### Observation

- `df -h` displays disk space usage.
- `df -i` displays inode usage.
- A filesystem may have free disk space but no free inodes.

### Questions

1. What does `df -h` show?
2. What does `df -i` show?
3. Why are both commands important?

---
# Review Questions

1. What is an inode?
2. What information is stored in an inode?
3. Does an inode store the filename?
4. What command displays disk space usage?
5. What command displays inode usage?
6. Can a filesystem have free disk space but no free inodes?
7. What happens when all inodes are consumed?
8. Why does Linux display "No space left on device" when no inodes remain?
9. Why do administrators monitor both disk usage and inode usage?
10. What command can be used to check inode utilization on a filesystem?

---

# Lab Summary

Write a short paragraph explaining:

- What you learned about inodes.
- The difference between disk space and inode usage.
- Why a system can report "No space left on device" even when free disk space exists.
- Which command was most useful during this lab.