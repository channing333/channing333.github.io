---
layout: post
title: "PHP Laravel Environment"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - PHP
---

# Installation

## 安裝PHP

到官網下載，若使用Apache，則選擇Thread Safe，下載完zip後，解壓縮到自己的目錄

## 安裝Composer

## 安裝Laravel

```
composer global require "laravel/installer=~1.1"
```

### Laravel問題
https://stackoverflow.com/questions/64686037/why-do-i-get-a-laravel-error-while-creating-a-new-project

```
composer global remove laravel/installer 
composer global require laravel/installer
```

https://stackoverflow.com/questions/29318709/how-can-i-resolve-your-requirements-could-not-be-resolved-to-an-installable-set

```
composer install --ignore-platform-reqs
composer update --ignore-platform-reqs
```