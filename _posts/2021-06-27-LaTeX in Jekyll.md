---
layout: post
title: "LaTeX in Jekyll"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - LaTeX
    - Jekyll
---

# LaTeX in Jekyll

## [How to do](http://www.iangoodfellow.com/blog/jekyll/markdown/tex/2016/11/07/latex-in-markdown.html)
add the line below in _layouts/post.html
```javascript=+
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
```

### Example
$$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$$

$$v=\sqrt{\left ( \frac{dx}{dt} \right )^{2}+\left ( \frac{dy}{dt} \right )^{2}+
  \left ( \frac{dz}{dt} \right )^{2}}$$