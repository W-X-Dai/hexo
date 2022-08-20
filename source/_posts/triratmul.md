title: 三角比結合乘法公式
author: W_X_Dai
tags:
  - math
  - 三角比
  - 乘法公式
categories: math
math: true
date: 2022-02-05 00:11:05
---
# 前言:
一道相當有趣的題目，主要是利用三角比得知未知數間的關係，再利用乘法公式解題。
<!--more-->

## 題目敘述:

- 設 $\sin^3\theta+\cos^3\theta=1$,求下列各值
    - $\sin\theta+\cos\theta$
    - $\sin^4\theta+\cos^4\theta$
- 想法:出現了$a^3+b^3$以及三角比，可以利用三角比得到更多$a$和$b$的關係，再利用乘法公式解題

### 子題組1
-  $\sin\theta+\cos\theta= \;?$
-  想法:將乘法公式結合三角比的關係進行運算
-  題解:
 為書寫方便，我們先假設$a=\sin\theta,b=\cos\theta,t=\sin\theta+\cos\theta$
 $a^2+b^2=0,a\times b=\cfrac{t^2-1}{2}$(證明$P1$)
 又$a^3+b^3=(a+b)^3-3ab(a+b)$(證明$P2$)
 接下來依次帶入得$a^3+b^3=t^3-\frac{t^2-1}{2}\times t=1$
 整理$t^3-3t+2=0$，觀察可以發現t=1為其中一解
 $t^3-3t+2=(t-1)^2(t+2),t=1\lor-2(不合)$
 $Ans.\sin\theta+\cos\theta= \;1$
 
### 子題組2
- $\sin^4\theta+\cos^4\theta=\; ?$
- 想法:將子題組1的結果帶入進行運算
- 題解:
 設$a=\sin\theta,b=\cos\theta,t=\sin\theta+\cos\theta$
 由子題組一，我們知道$a+b=1,a\times b=0,a^3+b^3=1$
 $\begin{split} (a^3+b^3)(a+b)=(a^4+b^4)+ab(a^2+b^2)a^4+b^4\\=(a^3+b^3)(a+b)-ab(a^2+b^2) \end{split}$
 $Ans.\sin^4\theta+\cos^4\theta=1\times 1+0\times 1=1$
 
### 證明

- P1

$(a+b)^2=a^2+b^2+2ab$
$\begin{split}2ab=&(a+b)^2-(a^2+b^2)\\=&(a+b)^2-1\end{split}$
$ab=\cfrac{(a+b)^2-1}{2}=\cfrac{t^2-1}{2}$

- P2

$\begin{split}(a+b)^3=&a^3+3a^2b+3ab^2+b^3\\=&a^3+b^3+3ab(a+b)\end{split}$
$a^3+b^3=(a+b)^3-3ab(a+b)$

# 原文

> [點此前往](https://hackmd.io/@myheartway/BkvWa25pF)