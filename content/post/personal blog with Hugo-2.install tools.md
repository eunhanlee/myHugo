--
title : "personal blog with Hugo-2.install tools"
date : "2021-09-08"
tags : [Installation,Hugo,CreateWebsite,Github]
topics : [Installation]
---

## Purpose

Create personal blog with Hugo and hosting with github at Windows 10.
For this purpose, you need knowledge of HTML, Markdown, and Hugo structure.
If you knwo golang, css, js, that will be better. But you do not have to.

### used tools

- install date : 03-31-2021
- hugo version : hugo v0.82.0
- git version : git version 2.31.1.windows.1
- windows : 10
- windows terminal: v1.7.572.0
- Chocolatey : v0.10.15

## install tools

### windows terminal

[Install and set up Windows Terminal](https://docs.microsoft.com/en-us/windows/terminal/get-started)

### sign up : github

[git hub link](https://github.com/)

### install hugo

[hugo install link](https://gohugo.io/getting-started/installing)
Since I used windows, I used Chocolatey

[Chocolatey install link](https://chocolatey.org/install)

1. windows terminal->right click-> run as Administer
   ![](https://raw.githubusercontent.com/eunhanlee/img/main/0046.jpg)
2. type `Get-ExecutionPolicy` and enter
3. if it showed `Restricted`, type
   `Set-ExecutionPolicy AllSigned` or
   `Set-ExecutionPolicy Bypass -Scope Process` 
4. type `Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))` and enter to install.
5. type `choco`to check Chocolatey installed
   ![](https://raw.githubusercontent.com/eunhanlee/img/main/0045.jpg)

Now, type `choco install hugo -confirm`and enter to install Hugo
![](https://raw.githubusercontent.com/eunhanlee/img/main/0047.jpg)
type `hugo version` and enter to check Hugo installed.

### intall git

[git intall link](https://git-scm.com/downloads)

after install, you should set your username and email. This can be any username and email. For avoiding confusion, I recommend to use same id and email from that you used for github sing up.

open terminel and type
```
git config --global user.name "name"
git config --global user.email "email"
```

you can check with typing as below

```
git config --list
```
