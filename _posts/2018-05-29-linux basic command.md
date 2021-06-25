---
layout: post
title: "linux basic command"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - shell
    - linux
---

# linux basic command
Linux上面安裝包大多用兩種：
* .deb
* .rpm

```shell=
ls 列出該目錄的檔案
dpkg --list(先列出有哪些軟體，這樣才知道軟體在Linux上面真正的名稱)
移除軟體：apt-get --purge remove SOFTWARE_NAME
安裝軟體：sudo dpkg -i SOFTWARE_NAME.deb
打包軟體：sudo dpkg -b DEBIAN母資料夾 OUTPUTNAME.deb

修改文檔：
vim 檔案名稱
:wq離開

```