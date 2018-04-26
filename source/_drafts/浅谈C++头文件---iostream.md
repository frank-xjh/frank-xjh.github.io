---
title: 浅谈C++头文件---<iostream>
date: 2018-3-17 23:07:30
tags: 
- 头文件
- C++
categories: 
- C++
- 头文件
---

## 1 前言

在刷题时看人家c++的题解，大部分前面都用了这个头文件：{% label info@#include<iostream> %}（输入输出流）。虽然我们经常使用这个easy的头文件，可是否有探究过这个头文件呢？让我们来看看吧！

## 2 功能

### 2.1 cin

这个单词读作：see-in。用来读取数据，称为标准输入，与c中的scanf效果相仿，在使用setw是要调用<iomanip>噢！

### 2.2 cout

这个单词读作：see-out。用来输出数据，称为标准输出，与c中的printf效果相仿噢！

<div class="note info"><p>

换行有三种方式：

'\n'

"\n"

endl

</p></div>

### 2.3 其它

经实验，发现max函数和min函数也包括在内，是不是很兴奋呀？

