---
layout: post
title: "C# WixTool新增Custom Action"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - Custom Action
    - Wix
    - .msi
---

# C# WixTool新增Custom Action

## 步驟

1. 開啟VS
2. 新增C# Custom Action Project for WiX v3專案
3. 新增完成CustomAction後，按下建置編譯出CustomAction.xxxxx.CA.dll
4. 在xx.wxs下使用Custom Action並使用dll
    + 新增< Binary Id>
    + 新增< Custom Action>並帶入參數，< Custom Action="xx" After="InstallFinalize" />
