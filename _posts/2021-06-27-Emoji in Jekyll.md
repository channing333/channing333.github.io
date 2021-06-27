---
layout: post
title: "Emoji in Jekyll"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - Emoji
    - Jekyll
---

# Emoji in Jekyll

## [How to do](https://github.com/jekyll/jemoji)

### 1. Modify Gemfile
Add the following to your site's Gemfile
```javascript=+
gem 'jemoji'
```

### 2. Run with Ruby cmd
```javascript=+
gem install emoji
```

### 3. Run cmd in project
```javascript=+
bundle install
```

### 4. add the following to your site's _config.yml
```javascript=+
plugins:
  - jemoji
```

### 5. See the results
```javascript=+
bundle exec jekyll serve
```

### Example
:smile_cat: :money_mouth_face: :robot:
