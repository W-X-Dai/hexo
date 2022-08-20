title: 如何在hexo網站中加入數學公式
author: W_X_Dai
tags:
  - 教學
  - 筆記
  - 心得
  - Hexo
categories: Hexo
date: 2022-02-02 23:07:12
---
# 緣起:
最近心血來潮，利用hexo結合github架設了一個網站，想用以紀錄我學習的歷程。然而第一天就遇到了一個問題:我要如何新增數學公式?數學是我學習中佔極大比例的學科，若是無法新增數學公式，網站的效益便會降低許多。在實驗了無數次，重新架站十幾次(真的)，爬了幾十篇文章後，終於能夠如願以償在網站中加入數學公式。以防忘記，先寫一篇文章記錄下來。
<!--more-->

# 前言
首先，必須先了解數學公式的來源。因為本人是使用[hackmd](https://hackmd.io/)起家，因此我所熟悉的數學公式寫法為[LaTeX](https://www.latex-project.org/)語法。而hexo所支援的語法有[MathJax](https://www.mathjax.org/)、[KaTeX](https://katex.org/)以及比較新的[hexo-math](https://github.com/hexojs/hexo-math)(需要hexo 5.0以上)。KaTeX在安裝上雖然比較簡單，但是有部分的LaTeX公式不支援，而hexo-math是比較新的東西，他的語法我不太習慣，而且說明文件大多英文，在實作上不停碰壁，無法完成。因此我選擇了其中安裝上比較麻煩的MathJax。

# 安裝準備
MathJax在開始使用前我們需要先做三件事情，這三件事情都可以在terminal中完成，由於卸載原有的渲染器以及安裝新的渲染器可以在同一個路徑的cmd完成，因此放在一起講。以下三者的順序其實沒有關係，但是為了方便，我稍稍調換了一下操作的順序。
- 卸載原有的渲染器
- 安裝新的渲染器
- 安裝新的選染器的驅動程式

## 安裝新的渲染器的驅動程式

首先在桌面左下角的搜尋中輸入"cmd"，然後右鍵點選"以系統管理員身分執行"，或是在右邊選擇"以系統管理員身分執行"
<iframe src="https://drive.google.com/file/d/1T638przJX95XE4CoGGryHVRCqL06SOA7/preview" width="640" height="480" allow="autoplay"></iframe>

接著輸入以下指令:
``` yml
choco install pandoc
```
按下Enter，系統就會自動幫你安裝pandoc了。

## 安裝新的渲染器並解卸載舊的

接著將終端機導向你部落格的根目錄，比如說我的是在d槽，並且名稱叫做"myblog"
``` yml
d:
cd myblog
```
然後輸入以下指令:
``` yml
npm uninstall hexo-renderer-marked --save
npm install hexo-renderer-pandoc --save
```
上面兩行指令中的第一行是卸載另一個版本的渲染器，以免與新的發生碰撞，下面的是安裝新的渲染器。這裡要注意的是，假使你有安裝過hexo-math，請再加上這一行:
``` yml
npm uninstall hexo-math --save
```
將hexo-math的渲染器移除。

## 修改網站設定檔

首先進入根目錄中的_config.yml檔案中，找到markdown，將其修改成這樣。如果原本沒有markdown，就在最底部加上以下程式碼:
```yml
markdown:
  plugins:
    - markdown-it-footnote
    - markdown-it-sup
    - markdown-it-sub
    - markdown-it-abbr
    - markdown-it-emoji
    - hexo-math
```
~~其實我也不知道沒有加會怎樣，也懶得嘗試。反正加了沒毛病，不加白不加~~😳


接下來修改**主題資料夾**中的_config.yml，注意不是根目錄裡面的那個。打開後找到關於math的內容，將其修改。不同主題的可能不一樣，不過一定要將enable設定成true，engine設定成mathjax，這樣才可以。
比如我的主題是fluid:
<iframe src="https://drive.google.com/file/d/1S_Is530qFjqnl8uG36nOW_nVn-hqFu6C/preview" width="640" height="480" allow="autoplay"></iframe>
其中將specific設定成true，這樣渲染器啟動的時機就只有在文章設定要開啟的時候啟動，不會造成資源浪費的問題。

## 設定文章
最後，來針對文章部分進行設定。**我的主題是fluid，使用的是MathJax**，<u>**不同主題、工具的可能會有所不同**</u>
從根目錄的source資料夾中開啟_posts資料夾，找到你想要加入數學的那一篇文章，在頂部(三條槓以上的地方)加入以下指令:
``` yml
math: true
```
要注意冒號後面要有一個空白，不然會噴警告。
然後重新啟動網站，就會發現已經成功渲染出數學公式了😁

# 參考資料
- [官方文件(簡體中文)](https://hexo.fluid-dev.com/docs/guide/)
- [Hexo問題集合](https://pxxyyz.com/posts/hexo-problem/)