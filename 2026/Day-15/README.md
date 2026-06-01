# PRACTICE LAB - PROJECT 101
## Introduction
> May 24th, 2026 - Day 15

This project is about everything you have learned up to this stage. It is important that you follow the STEPS carefully.

---

# Table of Contents

| Task | Title |
|------|--------|
| 1 | [Reading Exercise - Begin your Journey in IT](#task-1---reading-exercise---begin-your-journey-in-it) |
| 2 | [Reading Exercise - Understand What is a Local Repository](#task-2---reading-exercise---understand-what-is-a-local-repository) |
| 3 | [Reading Exercise - What is a Remote Repository](#task-3---reading-exercise---what-is-a-remote-repository) |
| 4 | [Reading Exercise - GIT Architecture](#task-4---reading-exercise---git-architecture) |
| 5 | [Operational Excellence using GIT](#task-5---operational-excellence-using-git) |

---

# Task 1 - Reading Exercise - Begin your Journey in IT

## NOTE: There are Two (2) Things You Have to Know

---

## (1) What is a Browser?

A web browser is a software application installed on your computer, phone, or tablet that acts as a window to the internet.

Its primary job is to fetch information from the World Wide Web and display it on your screen.

Examples of Browsers:

- Google Chrome
- Microsoft Edge
- Mozilla Firefox
- Safari

---

## (2) What is a File Folder?

In Windows, a folder (also called a directory) is a virtual container used to organize and store files on a computer.

Just like physical folders in an office, digital folders do not contain data themselves. Instead, they hold files such as:

- Documents
- Images
- Videos
- Music
- Other folders

Folders can also exist inside other folders.

A folder inside another folder is called a:

```text
Subfolder
```

---

## Windows File Path Example

Windows uses a file path to trace exactly where a file is stored.

Example:

```text
C:\Users\Nadeem\Documents\NIT_Academy\Lesson1.txt
```

---

## Questions

1. Are you clear about what a Browser is now?
2. Are you clear about what a File Folder is on your Windows Laptop?

---

# Task 2 - Reading Exercise - Understand What is a Local Repository

When you are sitting on your laptop, it is called your:

```text
LocalHost
```

The word "local" means the Laptop or Computer you are currently using.

When you create a file folder (directory) on your local machine, you are creating a:

```text
Local Repository (Repo)
```

---

## What is a Local Repository?

A local repository is a private storage space (directory) on a developer's own computer where Git tracks and saves the complete history of a project's files.

When you:

- Make changes
- Add code
- Save files
- Commit versions

all of this work happens inside your local repository.

---

## Important Note

A Local Repository:

- Exists on your own computer
- Does NOT require internet access
- Tracks file history locally
- Allows version control on your machine

---

## Question

Please explain in your own words:

```text
What is a Local Repository?
```

---

# Task 3 - Reading Exercise - What is a Remote Repository

A Remote Repository is a central archive stored in the cloud.

Examples include:

- GitHub
- GitLab
- Bitbucket

---

## Purpose of a Remote Repository

Once a developer is happy with their work, they can:

```text
Push (Upload)
```

their files and commits to the cloud.

This allows teammates to:

- View the code
- Download the code
- Edit the code
- Collaborate together

---

## Question

Explain the difference between:

```text
Local Repository vs Remote Repository
```

---

# Task 4 - Reading Exercise - GIT Architecture

The diagram below explains how a Local Repository fits into the modern software development workflow.

It also shows how data flows between:

- Developer Machine
- Git
- Remote Cloud Repository

---

<img src="../../.github/assets/2_how git works.jpg" width="350">

---

# Three Important Things to Understand

## 1. Complete Independence

Because the Local Repository exists entirely on the student's computer, students can:

- Track changes
- View old versions
- Create branches
- Work completely offline

---

## 2. The Hidden `.git` Folder

The hidden `.git` folder is the actual database that tracks project history.

When you run:

```bash
git init
```

Git creates a hidden folder named:

```text
.git
```

inside your repository.

---

## 3. Local vs Remote

### Local Save (Commit)

A Commit saves a snapshot only to the Local Repository on your computer.

---

### Global Share (Push)

A Push sends commits from the Local Repository to the Remote Repository (GitHub Cloud).

This allows teammates and collaborators to access your work.

---

# Questions

1. What does `git init` do?
2. What is the purpose of the hidden `.git` folder?
3. What is the difference between `commit` and `push`?
4. Why can Git work without internet access?

---

# Task 5 - Operational Excellence using GIT

<img src="../../.github/assets/4_cartoon.jpg" width="500">

---

# Reflection Questions

1. Why is Git important for developers?
2. Why is GitHub useful for teamwork?
3. Why should developers use version control?
4. What happens if code is not backed up properly?
5. Why is collaboration important in IT?

---

# Final Activity

## Write a Short Summary

Explain:

- What you learned about Git
- Difference between Local and Remote Repository
- Purpose of GitHub
- Why Git is important in modern IT environments

---

# Final Submission

Push your markdown practice files to your GitHub Repository.

Verify:

- Files appear on GitHub
- Commits are visible
- Repository is properly connected

---