---
title : "personal blog with Hugo-5.add github action"
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

### add github action

I finished build github website with Hugo. But every time I add new post, I had to commend Hugo to generate new HTML. There is github action that commend Hugo for me.

### set github secret
1. create github token
[github token link](https://github.com/settings/tokens/new)

2. check repo only like blow picture
![](https://raw.githubusercontent.com/eunhanlee/img/main/0052.jpg)

3. random arpbets and numbers will show. This is Token. save somewhere and do not share with other people

4. now, go to your repository( in my case, myHugo)
 setting->secrets-> add secrets 
set name as TOKEN and put the Token into value.

### github action setting

Then, go to your repository( in my case, myHugo) and create .github/workflows/main.yml
the main.yml will contain some code. I used Arnab's code.
[source code from Arnab, Thank you Arnab!](https://ruddra.com/hugo-deploy-static-page-using-github-actions/)

```
name: CI
on: push
jobs:
  deploy:
    runs-on: ubuntu-18.04
    steps:
      - name: Git checkout
        uses: actions/checkout@v2

      - name: Update theme
        # (Optional)If you have the theme added as submodule, you can pull it and use the most updated version
        run: git submodule update --init --recursive

      - name: Setup hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: "0.64.0"

      - name: Build
        # remove --minify tag if you do not need it
        # docs: https://gohugo.io/hugo-pipes/minification/
        run: hugo --minify

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          personal_token: ${{ secrets.TOKEN }}
          external_repository: <username>/<username>.github.io
          publish_dir: ./public
          #   keep_files: true
          user_name: <username>
          user_email: <username@email.com>
          publish_branch: master
        #   cname: example.com
```

change `<username>` to your github username
change `<username@email.com>` to your github email

Now, when you create new markdown file on /content/post/, the github action will create html site automacally.
If you visit the github action, it will show in detail logs.

### .gitmodule setting issue

if you see blow error:

fatal: No url found for submodule path 'public' in .gitmodules
Error: Process completed with exit code 128.

you can solve error by fixing .gitmodule  file


[.gitmodule explanation](https://git-scm.com/docs/gitmodules)

```
[submodule "folder name"]
	path = folder path
	url = git address
```

example
```
[submodule "themes/blackburn"]
path = themes/blackburn
url = https://github.com/yoshiharuyamashita/blackburn.git
[submodule "public"]
path = public
url = git://github.com/eunhanlee/eunhanlee.github.io.git
```
you can check my [github](https://github.com/eunhanlee)