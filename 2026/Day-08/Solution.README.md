# Module 01 – Introduction to IT & Linux
## Solution Guide (Day 08)
> Saturday 16th May, 2026

---

# Task 1 - Student Introduction & Goal Setting

## Sample Answer

1. My name is John Doe  
2. I have a background in customer service and basic computer usage  
3. I joined Linux training to start a career in IT and Cloud Computing  
4. My career goal is to become a Linux System Administrator or DevOps Engineer  
5. I hope to learn Linux administration, networking, virtualization, and cloud technologies in the next 10–12 weeks

---

# Task 2 - Understanding the IT Ecosystem

## Answers

### Where is Linux used in the Real World?

Linux is used in:

- Uber and Lyft servers
- AWS Cloud
- Google servers
- Android phones
- Banking systems
- Web hosting servers
- Cybersecurity systems
- Supercomputers

---

### What is a Linux Distro?

A Linux Distro (Distribution) is a version of Linux that includes:

- Linux Kernel
- Software packages
- Desktop environment
- Package manager
- System utilities

Examples:

- Ubuntu
- Rocky Linux
- Debian
- Fedora

---

### What is Virtualization?

Virtualization is the process of creating virtual machines on a physical computer. It allows multiple operating systems to run on one physical server using software called a hypervisor.

---

### What is a Server?

A server is a computer that provides services to other computers or users on a network.

Examples:

- Web Server
- File Server
- Database Server
- Mail Server

---

### Why is RHCSA Important?

RHCSA is important because it validates Linux administration skills used in enterprise environments and helps students qualify for Linux jobs.

---

# Task 3 - Home Network Exploration

## Answers

### What is a LAN?

LAN stands for Local Area Network. It is a network inside a home, office, or building.

---

### What is a Gateway?

A gateway is the router that connects a local network to the internet.

---

### Public IP vs Private IP

| Public IP | Private IP |
|------------|------------|
| Visible on the internet | Used inside local network |
| Assigned by ISP | Assigned by router |
| Unique globally | Reused in many homes |

---

# Task 4 - Identify Server-Like Functions in Your Router

| Service | Purpose |
|----------|----------|
| DHCP | Assigns IP addresses automatically |
| DNS | Resolves domain names to IP addresses |
| NAT | Allows many devices to share one public IP |
| Firewall | Protects network from unwanted traffic |
| Port Forwarding | Opens ports for external access |

---

# Task 5 - Data Center and Server Concepts

## Answers

### What is a Server?

A server is a machine that provides services to clients over a network.

---

### Services a Server Can Provide

- Web hosting
- File sharing
- DNS
- DHCP
- Email
- Database hosting

---

### What is a Data Center?

A data center is a facility that contains servers, networking devices, storage systems, and cooling systems.

---

### AWS and Azure

AWS and Azure are cloud platforms that use massive global data centers to provide cloud services.

---

# Task 6 - Server vs Laptop Comparison

| Feature | Laptop/Desktop | Server |
|---------|-----------------|--------|
| Purpose | Personal use | Serve multiple users |
| Uptime | Limited | 24/7 operation |
| Hardware | Consumer-grade | Enterprise-grade |
| Storage | Lower capacity | High capacity |
| Reliability | Moderate | Very high |

---

# Task 7 - Server Hardware Identification

| Component | Purpose |
|------------|----------|
| CPU | Processes instructions |
| RAM | Temporary memory |
| Disk | Permanent storage |
| RAID | Disk redundancy and performance |
| NIC | Network connectivity |
| GPU | Graphics processing |
| iDRAC | Remote server management |

---

### Why is RAID Important?

RAID provides:

- Data redundancy
- Better performance
- Fault tolerance
- Protection against disk failure

---

# Task 8 - Understanding the Simplified Linux Boot Process

## Boot Sequence

1. BIOS starts hardware initialization  
2. POST checks hardware health  
3. Boot Loader loads operating system  
4. Kernel initializes hardware and services  
5. Operating System starts user environment

---

### Bonus Answer

Yes, the GRUB menu appears during boot and allows selection of operating systems or recovery mode.

---

# Task 9 - Research Linux History

## Answers

### UNIX

UNIX was created at Bell Labs in 1969 and inspired modern operating systems.

---

### Linus Torvalds

Linus Torvalds created the Linux Kernel in 1991.

---

### GNU Project

The GNU Project provided free software tools used with Linux.

---

### Linux Kernel

The kernel is the core part of Linux that communicates with hardware.

---

### Why was Linux Revolutionary?

Linux was revolutionary because it was:

- Open source
- Free
- Portable
- Community driven

---

### Why was Rewriting UNIX in C Important?

Writing UNIX in C made it portable across different hardware platforms.

---

# Task 10 - Linux Distribution Research

## Light Weight Distros

| Distro | Lightweight? |
|---------|--------------|
| Red Hat | No |
| Rocky Linux | Moderate |
| Ubuntu | Moderate |
| Debian | Yes |
| Fedora | Moderate |
| SUSE | Moderate |

---

# Task 11 - Linux Shell Exploration

## Commands

```bash
cat /etc/shells
echo $SHELL
ps $$
date
whereis date
```

---

## Answers

### What is a Shell?

A shell is a command-line interpreter that allows users to interact with the operating system.

---

### What shell are you using?

Usually:

```bash
/bin/bash
```

---

### What does `ps $$` display?

It shows the process ID (PID) of the current shell session.

---

# Task 12 - Run Basic Linux Commands

## Commands and Meanings

| Command | Purpose |
|---------|----------|
| uname -a | Shows complete system information |
| uname -r | Shows kernel version |
| lscpu | Displays CPU information |
| free -m | Shows RAM usage |
| df -h | Displays disk space |
| ip a | Shows network interfaces |
| pwd | Shows current directory |

---

# Task 13 - Using Help Commands in Linux

## Commands

```bash
uptime --help
man date
```

---

## Answers

### What does the `man` command do?

It displays the manual/help page for Linux commands.

---

### Why are help systems important?

They help administrators learn commands and troubleshoot problems quickly.

---

# Task 14 - Keyboard Shortcut Practice

| Shortcut | Function |
|----------|-----------|
| Ctrl + C | Interrupt process |
| Ctrl + D | Exit shell |
| Ctrl + L | Clear screen |
| Ctrl + U | Clear current line |
| Ctrl + Z | Stop process |
| Tab | Auto complete command |

---

# Task 15 - Provisioning vs Configuration

## Answers

### What is Provisioning?

Provisioning is creating and preparing a machine with CPU, RAM, disk, and operating system.

---

### What is Configuration?

Configuration means customizing the machine settings after provisioning.

---

### Example of Provisioning

Creating a Virtual Machine with Rocky Linux installed.

---

### Example of Configuration

Setting a static IP address or firewall rules.

---

## Difference Between Reboot, Shutdown, and Poweroff

| Command | Meaning |
|----------|----------|
| Reboot | Restart the machine |
| Shutdown | Safely stop the operating system |
| Poweroff | Completely turn off the machine |

---

# Task 16 - Virtualization Concepts

## Answers

### What is Virtualization?

Virtualization allows multiple virtual machines to run on one physical machine.

---

### Why do Companies Use Virtualization?

- Better hardware utilization
- Cost savings
- Scalability
- Isolation
- Easier management

---

### Type 1 vs Type 2 Hypervisors

| Type 1 | Type 2 |
|---------|--------|
| Runs directly on hardware | Runs on operating system |
| Faster | Slightly slower |
| Enterprise use | Desktop/lab use |

Examples:

- Type 1: VMware ESXi, Xen
- Type 2: VirtualBox

---

### Why do we use VirtualBox?

VirtualBox allows students to create and manage Linux virtual machines on personal computers.

---

### Why Rocky Linux or Red Hat?

They are enterprise Linux distributions widely used in production environments.

---

# Task 17 - Final Reflection

## Sample Reflection

In Module 01, I learned about Linux, servers, virtualization, networking, and the Linux boot process. The most interesting topic was virtualization because it allows multiple systems to run on one machine. The Linux commands were initially difficult, but practicing helped improve my understanding. I want to improve my Linux administration and networking skills further.

---