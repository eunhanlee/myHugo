---
title : "install [git] to [windows 10]"
date : "2021-08-25"
tags : [Installation, git]
topics : [Installation]
---

# purpose

install [git] to [windows 10]

# What is git?

commend based program that is for tracking file changes. Origianlly, it invented for programming, thus, git file contains information of when did the file created, changed and moved.

# steps

### 1. downlad git
[official link](https://git-scm.com/)

### 2. install the program
### 3. installation settings

- Additional icons  > On the Desktop :  create shortcut
- Windows Exporer integration
	- Git Bash Here : Git Bash connection, any folder can connect with git right away
	- Git GUI Here : Git GUI connection, create some GUI on right click menu

- Git LFS (Large File Support) - origianlly git was for coding. Basically codes are just text files. If you check this, it can support other files too.
- Associate .git configuration files with the default text editor - you can open git file with default text editor
- Associate .sh files to be run with Bash - sh files(this file is for script language) is connected with git Bash
- Use a TrueType font in all console windows 
-  Check daily for Git for Windows updates 

### 4. Environment variable) setting
- Use Git from Git Bash only 
- Use Git from the Windows Command Prompt 
- Use Git and optional Unix tools from the Windows Command Prompt 

### 5. HTTPS transport backend setting

- Use the OpenSSL library - OpenSSL is open source library for encrypting connection between server and website
- Use the native Windows Secure Channel library 

### 6. conversions setting

- Checkout Windows-style, commit Unix-style line endings 
- Checkout as-is, commit Unix-style line endings 
- Checkout as-is, commit as-is 

1. Windows-style line endings is "\r\n"
2. Unix-style line endings is "\n"

Since git invented under Unix system, git cannot verify the "\r". If you are using windows and check the "Checkout as-is, commit as-is", it may cause line changing issue. If you use window, check the "Checkout Windows-style, commit Unix-style line endings"


### 7. terminal emulator setting

- Use MinTTY(the default terminal of MSYS2) - MinTTY terminal emulator
- Use Windows’ default console window 

### 8. extra option setting

- Enable file system caching - file will be saved in cach memory and it will work faster
- Enable Git Credential Manager -  Git Credential Manager for windows
- Enable symbolic links 

### 9. check installed

- git Bash and other coemmed will be added to right click menu
- you can cemmend "git --version" on cmd

### 10. set user name and email

git verify users with email and username. If you do not set, it will cause some issue when you upload online

#### set user name
```bash
git config --global user.name "[your id]"
```

#### set email

```bash
git config --global user.email "[your email]"
```

#### checking
you can cemmend "git config --list" on cmd for checking

```bash
git config --list
```