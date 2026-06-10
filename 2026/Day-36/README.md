# PRACTICE LAB
# Day 36 – Changing Date and Time on the Linux Command Line
## June 12th, 2026

> Based on Linux Date and Time Administration Concepts

---

# Objective

The objective of this lab is to learn how to:

1. Display the current date and time.
2. Understand the Linux system clock.
3. Display the current time in different formats.
4. Change the system date.
5. Change the system time.
6. Change both date and time together.
7. Verify changes made to the system clock.
8. Understand why incorrect system time can cause problems.
9. Practice safely changing date and time in a lab environment.
10. Restore the correct date and time.

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | [Display the Current Date and Time](#task-1---display-the-current-date-and-time) |
| 2 | [Display Date in Different Formats](#task-2---display-date-in-different-formats) |
| 3 | [Understand the System Clock](#task-3---understand-the-system-clock) |
| 4 | [Change the System Date](#task-4---change-the-system-date) |
| 5 | [Change the System Time](#task-5---change-the-system-time) |
| 6 | [Change Date and Time Together](#task-6---change-date-and-time-together) |
| 7 | [Verify the Changes](#task-7---verify-the-changes) |
| 8 | [Restore the Correct Date and Time](#task-8---restore-the-correct-date-and-time) |
| 9 | [Understanding Why Time Matters](#task-9---understanding-why-time-matters) |
| 10 | [Review Questions](#review-questions) |
| 11 | [Lab Summary](#lab-summary) |
| 12 | [Important Lesson](#important-lesson) |
| 13 | [Golden Rule](#golden-rule) |

---

# Introduction

## Why is Date and Time Important?

Linux uses date and time for:

- System logging
- Security auditing
- User authentication
- Scheduled tasks (cron jobs)
- Backups
- Monitoring systems
- Databases
- SSL Certificates
- Network troubleshooting

If the date and time are incorrect, many services may fail or behave unexpectedly.

---

# Task 1 - Display the Current Date and Time

## Objective

View the current system date and time.

### Run

~~~bash
date
~~~

### Example Output

~~~text
Fri Jun 12 10:45:22 AM CDT 2026
~~~

### Questions

1. What is today's date?
2. What is the current time?
3. What timezone is displayed?

---

# Task 2 - Display Date in Different Formats

## Objective

Display date and time using custom formats.

### Run

#### Display Only the Date

~~~bash
date +"%Y-%m-%d"
~~~

Example:

~~~text
2026-06-12
~~~

---

#### Display Only the Time

~~~bash
date +"%H:%M:%S"
~~~

Example:

~~~text
10:45:22
~~~

---

#### Display Full Date and Time

~~~bash
date +"%A %d %B %Y %H:%M:%S"
~~~

Example:

~~~text
Friday 12 June 2026 10:45:22
~~~

### Questions

1. Which format do you prefer?
2. Why might different date formats be useful?

---

# Task 3 - Understand the System Clock

## Objective

Verify the system clock.

### Run

~~~bash
date
~~~

### Notes

The Linux operating system maintains an internal system clock.

Most applications depend on this clock.

### Questions

1. What would happen if the clock was incorrect?
2. Which applications might be affected?

---

# Task 4 - Change the System Date

## Objective

Change only the date.

### Important Note

You must be logged in as root.

### Run

~~~bash
date +%Y%m%d -s "20260615"
~~~

### Verify

~~~bash
date
~~~

### Questions

1. Did the date change?
2. What remained unchanged?

---

# Task 5 - Change the System Time

## Objective

Change only the time.

### Run

~~~bash
date +%T -s "14:30:00"
~~~

### Verify

~~~bash
date
~~~

### Questions

1. Did the time change?
2. Did the date remain the same?

---

# Task 6 - Change Date and Time Together

## Objective

Modify both date and time in a single command.

### Run

~~~bash
date -s "2026-06-20 09:15:00"
~~~

### Verify

~~~bash
date
~~~

### Questions

1. What date is now displayed?
2. What time is now displayed?

---

# Task 7 - Verify the Changes

## Objective

Confirm that the system clock was updated successfully.

### Run

~~~bash
date
~~~

### Additional Verification

~~~bash
uptime
~~~

### Questions

1. Does the displayed date match the configured date?
2. Does the displayed time match the configured time?

---

# Task 8 - Restore the Correct Date and Time

## Objective

Return the system to the correct date and time.

### Method 1 - Set Manually

### Run

~~~bash
date -s "2026-06-12 10:45:00"
~~~

---

### Method 2 - Use Network Time Synchronization

### Run

~~~bash
timedatectl status
~~~

### Notes

Many Linux systems synchronize time automatically using NTP. To see the NTP servers your system is connected to
You can check which daemon (service) is actively running on your system:
~~~bash
systemctl status chronyd
~~~
Check the NTP server configuration file:
~~bash
cat /etc/chrony.conf
~~

~~~bash
chronyc sources -v
~~~
- The ^* symbol next to a server means it is the current active NTP source.
- The -v flag adds a helpful legend explaining what all the symbols mean.

### Run

~~~bash
timedatectl
~~~

### Questions

1. Is NTP enabled?
2. Why is automatic time synchronization useful?

---

# Task 9 - Understanding Why Time Matters

## Objective

Understand the importance of accurate system time.

### Run

~~~bash
ls -l /var/log
~~~

### Observation

Notice the timestamps on files.

### Discussion

Incorrect time can cause:

- Incorrect logs
- Backup failures
- Authentication failures
- Certificate errors
- Scheduled jobs running at the wrong time

### Questions

1. Why are timestamps important?
2. Why would a System Administrator care about accurate time?

---

# Real World Administrator Scenario

A user reports:

~~~text
I cannot access the company website.
~~~

You investigate and discover:

~~~text
SSL Certificate Not Yet Valid
~~~

The problem was:

~~~text
The server date was incorrect.
~~~

This demonstrates why accurate system time is critical.

---

# Review Questions

1. What command displays the current date and time?
2. Why is system time important?
3. Which command changes only the date?
4. Which command changes only the time?
5. Which command changes both date and time?
6. Why must a System Administrator verify changes?
7. What is NTP?
8. Why are timestamps important?
9. What problems can incorrect time cause?
10. How can you verify the current system time?

---

# Lab Summary

In this lab you learned how to:

- Display the current date and time
- Display custom date formats
- Understand the Linux system clock
- Change the system date
- Change the system time
- Change date and time together
- Verify time changes
- Restore correct time settings
- Understand NTP synchronization
- Troubleshoot date and time issues

---

# Important Lesson

Whenever troubleshooting a Linux system, always check:

~~~bash
date
timedatectl
uptime
~~~

Incorrect date and time can cause many issues that appear unrelated to the clock.

---

# Golden Rule

~~~text
Always Verify System Time Before Troubleshooting Complex Problems
~~~

---

# End of Lab

🐧 Happy Learning Linux Administration!
