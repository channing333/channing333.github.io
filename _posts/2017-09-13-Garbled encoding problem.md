---
layout: post
title: "Garbled encoding problem"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - Qt
---

# Garbled encoding problem

有些特殊符號因為作業系統語言不同，導致編碼語系不同而產生亂碼

### 解決方法
在.cpp開頭加上
```
#pragma execution_character_set("utf-8")
```