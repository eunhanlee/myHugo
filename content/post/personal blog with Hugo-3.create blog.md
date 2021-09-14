---
title : "personal blog with Hugo-3.create blog"
date : "2021-09-14"
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


### create blog

#### create static site

Go to any fodler that you want to and then run windows terminal.

folder-> right click-> windows terminal 실행 

*for me, I use folder as D:\github
![](https://raw.githubusercontent.com/eunhanlee/img/main/0049.jpg)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0048.jpg)


type blow to create folder and use with Hugo.
```
hugo new site myHugo
cd myHugo
```

`myHugo` is just folder name, you can change it.

#### Now, add git for the static site folder and set the theme that you want to use.

let's find theme under the Hugo site.

[Hugo Theme list](https://themes.gohugo.io/) 

```
cd myHugo
git init
git submodule add [git address] themes/[theme name]
```
#### example with blackburn
used hugo Theme: https://themes.gohugo.io/blackburn/
git address: https://github.com/yoshiharuyamashita/blackburn.git 
theme name: blackburn
```
cd myHugo
git init
git submodule add https://github.com/yoshiharuyamashita/blackburn.git themes/blackburn
```

#### edit config.toml
config.toml is the main file that has setting of your website.
set config.toml as theme maker recommended

Additionally, you will need to add to more.

1. baseURL
change baseURL = "https://example.com" to https://[gothub id].github.io/.
For example, `baseURL = "https://eunhanlee.github.io/"` for my case.

2. theme
set theme name what you used. I used theme, "blackburn"
theme = "blackburn"


#### create new post
basically, it made by markdown file under the content folder.
```
hugo new posts/my-first-post.md
```
you can use above commend or you can create md file under the content.

#### example of content
all of posts will be stay under the content folder. However, addtional folder may needed depend on themes. The 
blackburn used folder post. Thus, my post path is "myHugo/content/post/"
[check my github content](https://github.com/eunhanlee/myHugo/tree/master/content)

#### pre-view of site
```
Hugo server -D
```
use the commend and check [http://localhost:1313/]( http://localhost:1313/)

For exit, ctrl+c



