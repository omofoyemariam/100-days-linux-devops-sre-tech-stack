# Downloading Visual Studio Code on Windows, Chromebook, and Mac
 > Wednesday 13th May, 2026 - DAY 5
---
## DO ONLY ONE TASK BASED ON YOUR MACHINE!
# Table of Contents

| Task | Title |
|------|--------|
| 1 | [Installation for Windows](#task-1---installation-for-windows) |
| 2 | [Installation for Chrome Book](#task-2---installation-for-chrome-book) |
| 3 | [Installation for Mac](#task-3---installation-for-mac) |

---

# Task 1 - Installation for Windows

## Step 1: Open the VS Code Website

Go to:

https://code.visualstudio.com/

You will see a large blue download button.

---

## Step 2: Download VS Code for Windows

Click:

**Download for Windows**

This downloads the `.exe` installer.

---

## Step 3: Run the Installer

1. Open the downloaded file  
2. Click **Next**  
3. Accept the license agreement  
4. Keep clicking **Next**  
5. Click **Install**

### Recommended Options

- Add to PATH
- Create desktop icon

---

## Step 4: Launch VS Code

After installation:

1. Click **Finish**
2. VS Code opens automatically

You can also search:

```text
Start Menu → Visual Studio Code
```

---

# Task 2 - Installation for Chrome Book

## Step 1: Enable Linux on Chromebook

1. Open **Settings**
2. Go to **Developer**
3. Turn ON **Linux Development Environment**

---

## Step 2: Open the Linux Terminal

After Linux installs:

1. Open **Launcher**
2. Search for **Terminal**
3. Open it

---

## Step 3: Install VS Code

Run these commands one by one:

```bash
sudo apt update
sudo apt install wget gpg -y
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
sudo apt update
sudo apt install code -y
```

---

## Step 4: Launch VS Code

1. Open **Launcher**
2. Search for:

```text
Visual Studio Code
```

3. Open it

---

# Task 3 - Installation for Mac

## Step 1: Open the VS Code Website

Visit:

https://code.visualstudio.com/download

Click:

**Download for Mac**

Choose:

- Apple Silicon
OR
- Intel Chip

---

## Step 2: Open the Downloaded ZIP File

1. Open **Downloads**
2. Double-click the ZIP file
3. Extract Visual Studio Code

---

## Step 3: Move VS Code to Applications

Drag:

```text
Visual Studio Code.app
```

into:

```text
Applications
```

---

## Step 4: Open VS Code

1. Open **Applications**
2. Click **Visual Studio Code**

If prompted:

```text
Click Open
```

---