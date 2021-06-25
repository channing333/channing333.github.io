---
layout: post
title: "Check Update"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - Qt
    - Inno Setup
---

# Check Update

### uninstall automatically
[修改iss相關參考](https://stackoverflow.com/questions/2000296/inno-setup-how-to-automatically-uninstall-previous-installed-version?answertab=oldest#tab-top)

[Code]
這是Inno Setup的section，代表程式語法的區塊

如何查看程式註冊碼：
開始-->直接輸入%systemroot%\syswow64\regedit

### Silent install
#### 方法1
[在Code Section加上very silent install](https://stackoverflow.com/questions/21575241/how-to-make-the-silent-installation-by-using-innosetup?answertab=votes#tab-top)

* Silent install：安裝progress會顯示
* Very silent install：安裝progress不會顯示

#### 方法2
* 直接在cmd："xxx.exe /VERYSILENT"