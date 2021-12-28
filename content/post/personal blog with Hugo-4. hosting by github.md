---
title : "personal blog with Hugo-4. hosting by github"
date : "2021-12-28"
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


### upload to github

#### create two repository on github
- 1st repository: actual Hugo code will be here
- 2nd repository: Hugo render the 1st repository data into HTML

The github will host 2nd repository to show on online. Thus the 2nd repository name must be username.github.io

username.github.io will be your website address

#### can I change the website address?
github provide free hosting and server. If you want to change the address, you will need to use other hosting site.


Then, open terminal
```
git remote add origin [1st repository git address]
git submodule add -b master [2nd repository git address] public
hugo -D
git add .
git commit -m "test"
git push origin master
cd public
git add .
git commit -m "test"
git push origin master
```



#### example of personal blog with blackburn theme
- github username: eunhanlee
- 1st repository name: myHugo
- 1st repository git address: https://github.com/eunhanlee/myHugo.git
- 2nd repository name: eunhanlee.github.io
- 2nd repository  git address: https://github.com/eunhanlee/eunhanlee.github.io.git public

```
git remote add origin https://github.com/eunhanlee/myHugo.git
git submodule add -b master https://github.com/eunhanlee/eunhanlee.github.io.git public
hugo -D
git add .
git commit -m "test"
git push origin master
cd public
git add .
git commit -m "test"
git push origin master
```
