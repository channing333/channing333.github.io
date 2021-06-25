---
layout: post
title: "Bézier curve"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - Qt
    - draw
---

# 貝茲曲線(Bézier curve)

貝茲曲線於1962年，由法國工程師皮埃爾·貝茲（Pierre Bézier）所廣泛發表，他運用貝茲曲線來為汽車的主體進行設計

## API Reference

#### void QPainterPath::lineTo(const QPointF &endPoint)
    lineTo()因為貝茲曲線的最後一筆會是直線，故將最後一筆畫省略，導致客戶以為少了一點

#### void QPainterPath::quadTo(const QPointF &c, const QPointF &endPoint)
    Adds a quadratic Bezier curve between the current position and the given endPoint with the control point specified by c