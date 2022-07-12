---
id: e21b2a82-20a3-4f7e-981e-d83e6df620a5
title: for 循环
categories:
  - "\U0001F468\U0001F3FB‍\U0001F4BBcode"
  - C++
  - C++ primer plus
tags: 函数
date: 2022-06-06 14:08:12
---


[ob](obsidian://advanced-uri?vault=Documents&uid=e21b2a82-20a3-4f7e-981e-d83e6df620a5)
# 1 遍历函数
操作到最后一个元素时不会取到最后一个下标的后一位(也就是长度)

```cpp
   for (int i = 0; i < prices.size(); i++){
            result += max(prices[i+1] - prices[i],0);// 用!=更好
        }
```


从后往前遍历：`for (int i = num.size () - 1; i > 0; i--)` 这个操作不了第一个元素(下标0)

从前往后遍历：`for(int i = 0 ; i < num.size(); i++)`，

# 2 数组求和
for (循环变量类型 循环变量名称 : 要被遍历的对象) 循环体
应用：对数组求和
	从第一个元素开始操作
```cpp
//A是数组，for循环对数组求和
int result = 0;
for (int a : A)  result += a; // a没有特殊的意义，只是指明循环变量的类型，“:”后只需数组名即可
```


#flashcards/代码随想录 
n%2 == 1什么意思 
?
n%2就是对n求：n除以2后的余数，这里余数只有两种情况就是0或者是1
eg：5%2=1
<!--SR:!2022-08-01,28,250-->



