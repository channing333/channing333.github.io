---
layout: post
title: "Heroku Crash"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - Heroku
    - Node.js
    - mySQL
---

# MySQL Error: Connection lost. The server closed the connection

## [參考網址](https://medium.com/%E4%B8%80%E5%80%8B%E5%B0%8F%E5%B0%8F%E5%B7%A5%E7%A8%8B%E5%B8%AB%E7%9A%84%E9%9A%A8%E6%89%8B%E7%AD%86%E8%A8%98/nodejs-%E8%A7%A3%E6%B1%BAmysql-error-connection-lost-the-server-closed-the-connection%E7%9A%84%E6%96%B9%E6%B3%95-d374bdddf9c1)

![](https://i.imgur.com/sUGxRsS.png)
![](https://i.imgur.com/yDIhkJ3.png)

## 解決方法
```
Heroku restart 可解決
但透過下面指令發現真正問題是server closed
heroku logs --tail
```
