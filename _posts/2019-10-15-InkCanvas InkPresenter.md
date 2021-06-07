---
layout: post
title: "InkCanvas InkPresenter"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - WPF
    - InkCanvas
---

# InkCanvas InkPresenter

[InkCanvas官網實作](https://docs.microsoft.com/zh-tw/dotnet/framework/wpf/advanced/getting-started-with-ink)

``` c# =
 // 摘要:
        //     取得或設定色彩 System.Windows.Ink.Stroke。
        //
        // 傳回:
        //     色彩 System.Windows.Ink.Stroke。
        public Color Color { get; set; }
```

SolidColorBrush可透明作畫

<Window.Background>
        <SolidColorBrush Color="White" Opacity="0.01" />
    </Window.Background>
    
### 錯誤訊息
在xaml為RadialMenu命名name欄位，編譯後發生錯誤
```
錯誤	CS0426	類型名稱 'Controls' 不存在於類型 'RadialMenu' 中	windowsLauncher	D:\windowsLauncher\windows_launcher\RadialMenu.xaml	19		使用中
```
解決方法：因為使用了RadialMenu的類別，需存取不同名稱的xaml，更改名稱後即可使用

進入RadialMenuItem.xaml修改預設background的顏色
<Setter Property="Background" Value="AliceBlue"/>

![](https://i.imgur.com/WBxqW6B.png)
先取消先前參考後，再加入新的參考

透明度設為0，可穿透畫布