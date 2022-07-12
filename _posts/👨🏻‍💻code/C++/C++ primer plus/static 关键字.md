---
title: static 关键字
tags:
  - C++
published: true
hideInList: false
isTop: false
categories:
  - "\U0001F468\U0001F3FB‍\U0001F4BBcode"
  - C++
  - C++ primer plus
date: 2022-05-30 00:00:00
feature:
---
static 关键字有三种用法

1. static 修饰局部变量 → 静态局部变量
	1. 改变局部变量的生命周期，下次使用该局部变量是上次使用完后的值，而不是初始值
2. static 修饰全局变量 →静态全局变量
	1. 只能在本文件内使用，不能在其他文件中访问，extern外边声明也不行(无static时默认是可以被外部访问的)
3. static 修饰函数 →静态函数
	1. 只能在本文件中**调用**，同2
