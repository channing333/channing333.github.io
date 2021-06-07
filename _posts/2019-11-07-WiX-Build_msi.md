---
layout: post
title: "Wix- From .exe to .msi"
categories: "blog"
header-img: "img/bg.jpg"
tags:
    - Wix
    - .exe
    - .msi
---

# WiX-Build .msi

### Install WiX and .NET framwork v3.5.1
> [Wix官網](https://wixtoolset.org)
> [.NET framwork v3.5.1](https://www.microsoft.com/zh-tw/download/details.aspx?id=25150)-安裝WiX必須的環境

### Build .msi with WiX
> [WiX Tutorial](https://www.codeproject.com/Tips/105638/A-quick-introduction-Create-an-MSI-installer-with)

> WiX相關命令加入環境變數![](https://i.imgur.com/PvEhlVy.png)

> PowerShell產生GUID
> 
【基礎知識】：
heat.exe：用於多層資料夾結構，可使用該程式直接產生目錄對應的.wxs
candle.exe：編譯.wxs產生.wixobj檔
light.exe：將.wixobj輸出產生.msi檔
powerShell視窗輸入[guid]::NewGuid()，可取得GUID，這是一組唯一識別碼
![](https://i.imgur.com/MtczpFo.png)

[實際WiX對於非VisualStudio專案的打包](https://jimmylin212.github.io/post/0005_create_msi_by_wix/)
該網站最下方，會下載到下面兩個檔案
HeatTransform.xslt：用來產生wxs樣板用
Makefile_win.ps1：作者已將heat.exe、lighe.exe、candle.exe執行等相關步驟寫成shell，用power shell執行後，可直接產生.msi檔案
![](https://i.imgur.com/nGGVxhx.png)


以下修改都是修改.ps1檔案，因為這樣改，才可一勞永逸，不用每次都去手動更改wxs檔案
自行修改相關版號與程式名稱，並新增下方使用的$gMsiVersion(原先作者沒寫到)
![](https://i.imgur.com/V3xD3Rg.png)

拿掉公司名稱：
![](https://i.imgur.com/xJVWZFX.png)
![](https://i.imgur.com/lGcJ9EK.png)

[安裝圖示問題](https://wixtoolset.org/documentation/manual/v3/howtos/ui_and_localization/configure_arp_appearance.html)
![](https://i.imgur.com/LuMSTgU.png)

要在wxs的Product屬性裡面加上
'''
<Icon Id="icon.ico" SourceFile="1.Files/Teach Infinity II.ico"/>
	<Property Id="ARPPRODUCTICON" Value="icon.ico" /> 
'''

所以在.ps1加上
![](https://i.imgur.com/YSHSxQv.png)
更改後：
![](https://i.imgur.com/LXO4hWD.png)

安裝完成後，沒有複製.exe到桌面：
[WiX複製.exe到桌面教學](https://stackoverflow.com/questions/11868499/create-shortcut-to-desktop-using-wix)
加上Component與Feature的element

![](https://i.imgur.com/UxoPDzB.png)
![](https://i.imgur.com/r86dH30.png)

確認有無安裝過同樣版本或是不一樣版本的.msi：
![](https://i.imgur.com/eYvUkHE.png)

加入Condition後，安裝同版本執行檔會顯示
![](https://i.imgur.com/4yDZay5.png)

安裝不同版本會顯示
![](https://i.imgur.com/GWU4edx.png)

以上修改完成後，之後只要覆蓋1.Files、改一下.ps1裡面版本號及檔名，就可執行.ps1，直接產生新的.msi

【後記】：打包過程發生一些一次性的問題，已解決，以後不用再處理
發現有兩個檔案檔名有些問題，而該檔名有奇怪的符號，將符號刪除即可，該圖片檔是裁切圖片的右上角圖示
![](https://i.imgur.com/VrDCN5Q.png)

```
<File Id="fil3A1E49F7222409E8C918D8060F185DDF" KeyPath="yes" Source="$(var.Dist)\Environment\images\64_64\⁯IDR_IMAGECUT_RIGHTTOP.png" />
把該亂碼刪除

<File Id="filC5C0577D7BD61F33473DD8007816D7C2" KeyPath="yes" Source="$(var.Dist)\plugin\userdata\lang\Qt 系统gui.ts" />
改一下名字 改成Qt System gui.ts
```

.ttf字型問題，看起來那兩項名稱都不是字型名稱，看起來也沒用到，但是怕說會有其他問題，故就先放著不管
![](https://i.imgur.com/TJfArG1.png)

Jeff從NAS下載測試安裝，發生以下問題，但用USB直接給他，就沒問題！
重包一次，再下載一次，也沒問題了
![](https://i.imgur.com/9G8fRRu.png)
