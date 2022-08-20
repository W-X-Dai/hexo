title: 數據分析學習筆記
author: W_X_Dai
tags:
  - math
  - 數據分析
  - 筆記
categories: math
math: true
date: 2022-02-15 19:14:21
banner_img:
---
# 前言:

在高中的數學課程中，我認為數據分析是挺硬的一個章節。因為他的公式特別多，而且大多數的公式都是人為定義出來的。不像是三角比，只需要記憶$\sin ,\cos ,\tan$等的定義就可以推導出一個三角的系統。因此，我想做一個數據分析的學習筆記，利用前不久學會使用的$L^AT_EX$語法，將數據分析的公式記錄下來。
此外，數據分析是未來資訊科技的主流之一。未來資訊科技的主流之一為人工智慧，而人工智慧的原理正式統計學，也就是數據分析。最主要的目標就是從一堆雜亂的資料中找出最佳直線，能夠最大程度的提升準確率。
以下便是我整理的內容

<!-- more -->

## 一維數據分析

### 算術平均數
- 假設$n$個數字$x_1,x_2,x_3,...,x_n$
- 算術平均數$\mu=\cfrac{1}{n}(x_1+x_2+x_3+...+x_n)$

### 加權平均數

- 假設$n$個數字$x_1,x_2,x_3,...,x_n$，其中$x_i$對應到的加權為$w_i$
- 加權平均數$W=\cfrac{x_1w_1+x_2w_2+...+x_nw_n}{w_1+w_2+...+w_n}$

### 幾何平均數

- 假設$n$個數字$x_1,x_2,x_3,...,x_n$
- 幾何平均數$G=\sqrt[n]{x_1\times x_2\times x_3\times ...\times x_n}$
- 應用:假設某物$n$年的成長率分別為$r_1,r_2,r_3,...r_n$，其平均成長率$x=\sqrt[n]{(1+r_1)\times (1+r_2)\times (1+r_3)\times ...\times (1+r_n)}-1$
- 證明:假設平均成長率為$x$，過了$n$年後，其總成長率為$(1+x)^n=(1+r_1)(1+r_2)(1+r_3)(1+r_4)$
- 經過化簡可得$x=\sqrt[n]{(1+r_1)\times (1+r_2)\times (1+r_3)\times ...\times (1+r_n)}-1$

### 百分位數

- 第$m$百分位數$P_m\;(1\le m\le 99)$:至少有$m\%$的數據$\le P_m$，至少有$(100-m)\%$的數據$\ge P_m$，
- 假設一筆升冪排序過後的資料有$n$個數據$x_1$~$x_n$
- $I=n\times \cfrac{m}{100}$
- $I\notin \mathbb{N},P_m=x_{\lceil I\rceil}$($\lceil I\rceil為>I$之最小整數)
- $I\in\mathbb{N},P_m=ave(x_I,x_{I+1})$

### 數據的離散程度

- 設$n$個數據$x_1,x_2,...,x_n$，其算術平均數為$\mu$
- 全距:一堆數據中，最大值與最小值的差
- 離均差:$x_i$之離均差為$x_i-\mu$，$\displaystyle\sum^n_{i=1}(x_i-\mu)=0$
- 變異數$\sigma^2=ave(\displaystyle\sum^n_{i=1}(x_i-\mu))$
- 標準差$\sigma :\;$離均差平方的平均之平方根(~~好饒舌~~)

### 數據的伸縮與平移

- 給定$n$個數據$x_1,x_2,x_3...,x_n$，其算術平均數為$\mu$，標準差$\sigma$
- 若$y_i=ax_i+b,$則$\mu_y=a\mu_x+b,\sigma_y=|a|\sigma_x$


### 標準化數據

- 將數據標準化後可得Z分數或是標準分數，可看出比原平均多/少幾個標準差
- $Z_i=\cfrac{x_i-\mu}{\sigma}$
- Z分數之特性
    1.$\mu_z=0$
    2.$\sigma_z=1$

## 二維數據分析

- 用以觀察兩種數據之間的關係
- $i.e.$ 睡眠時數與罹患慢性病的比例

### 相關係數

- 設有$n$筆資料$(x_1,x_2),(x_2,y_2),...,(x_n,y_n)$
- $x',y'$代表經標準化後的數據
- 相關係數$r=\cfrac{\displaystyle\sum^n_{i=1}x_i'y_i'}{n}$
- 若數據未經標準化，則相關係數$r=\cfrac{\displaystyle\sum^n_{i=1}(x_i-\overline{x})(y_i-\overline{y})}{\sqrt{\displaystyle\sum^n_{i=1}(x_i-\overline{x})^2\displaystyle\sum^n_{i=1}(y_i-\overline{y})^2}}$

### 迴歸直線

- 最小平方法:尋找最小的殘差平方和
- 迴歸直線方程式
- 標準化數據:$y'=rx',r:\;$相關係數
- 未經標準化:$y-\overline{y}=m(x-\overline{x})$
- $m=r\cdot\cfrac{\sigma_y}{\sigma_x}$
- 迴歸直線必過點$(\mu_x,\mu_y)=(\overline{x},\overline{y})$

### 迴歸直線公式整理

- 設$S_{xy}=\displaystyle\sum^n_{i=1}(x_i-\mu_x)(y_i-\mu_y),S_{xx}=\displaystyle\sum^n_{i=1}(x_i-\mu_x)^2$
- $y'=rx'$
- $y-\overline{y}=r\cdot\cfrac{\sigma_y}{\sigma_x}(x-\overline{x})$
- $y-\overline{y}=\cfrac{S_{xy}}{S_{xx}}(x-\overline{x})$