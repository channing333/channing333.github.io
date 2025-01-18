---
layout: post
title: "Git ssh key generate"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - Git
---

# Git ssh key generate in Windows
```
ssh-keygen -t ed25519 -C "<comment>"
cat ~/.ssh/id_ed25519.pub | clip
貼到ssh key setting的地方
```

# Git ssh key generate in macOS
```
ssh-keygen -t ed25519 -C "<comment>"
cat ~/.ssh/id_ed25519.pub | pbcopy
貼到ssh key setting的地方
```



