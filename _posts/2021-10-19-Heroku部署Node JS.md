---
layout: post
title: "Heroku部署"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - Heroku
    - Node.js
---

# Heroku部署
```
git init
git add .
git commit -m “xxxxx”
heroku create(做一次就可)
git push heroku master/main(上傳到heroku的master/main分支)
heroku open(直接開啟專案在瀏覽器)

```

# mySQL雲端配置(非本地)

在Heroku專案上加入ClearDB，注意免費版本只有5MB的資料量
## [相關步驟參考](https://medium.com/@jedy05097952/node-js-mysql-%E9%83%A8%E7%BD%B2-heroku-f07a2d75e72f)

```
heroku addons:create cleardb:ignite
heroku config | grep CLEARDB_DATABASE_URL
或
heroku config | findstr CLEARDB_DATABASE_URL
```
![](https://i.imgur.com/pylt1Mo.png)

## [node程式中使用Config Vars](https://nodejs.dev/learn/how-to-read-environment-variables-from-nodejs)

Heroku上Config Vars變數名稱要與程式內env.HOST一致
![](https://i.imgur.com/qUXWWbr.png)
```javascript=+
mysql: {
    host: process.env.HOST,
    user: process.env.DATABASE_USER,
    password: process.env.DATABASE_PASSWORD,
    database: process.env.DATABASE
  },
  secret: process.env.MY_SECRET
```
