
---
title : "personal blog with Hugo-1.Notions"
date : "2021-09-02"
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

## Notions

### hugo?

Hugo is static site generator. Commend-based program that help to create static site.

### static site Vs. dynamic site

dynamic site react dynamically. When you move your mouse on some banners, it gives changing picutures for attact you. However, static sites do not react with your mouse moveing. Static sites are for blog, journal, or reading. Dynamic sites are for shopping

### front matter

front matter is Hugo Term that verify your wrighting. It can be changed depend on custom Themes. Hugo provide 3 subjects such as title, date, draft in basic.

#### example

```
---
title: "My first wrighting"
date: 2021-03-31
draft: true
---
```

### Commend-based program

Instead of click some button, these programs are run by commend. In computer world, this is very common.

### terminal

Some program that will take your commend and run in windows, OS x, or Linux. For windows, there are a lot of custom terminals. I used the windows terminal.

### git?

Version control commend based program for programming. If you edit some code, git will record what, when, how you changed the code. 

### github?

The cloud program that will save git files. So, you can use and change code in any computers. 

### Hosting?

When you create web site, you need some place to save the files for the website. Thus, you can upload the files internet and host from the place. I will use github as the database. Thus, github will have my wrighting, pictures and hugo will change that to HTML. and HTML will show my website.

### Markdown

Markdown is lightweight markup language. In other word, you can change your wrightings size, colors and create table in word.
check below fore more details.
[markdown guide](https://www.markdownguide.org/getting-started/)

### ketax

This is for math wrighting. It will help to wright math symbols such as root, square, and fractions.

### Hugo structure

- archetypes :  default.md is there for front matter setting
- content :actual wrighting will be stay in this folder
- data : for saving data, static site will not show these files in the folder
- layouts : html files for design of you website.
- static : css, js, img files for connect with your website
- public: other folder files are HTML and Markdown files. Hugo will put all together and change HTML in this folder
