---
title: 'begin,end'
categories:
  - "\U0001F468\U0001F3FB‍\U0001F4BBcode"
  - C++
  - C++ primer plus
tags: 函数
date: 2022-06-07 11:20:13
---
```cpp
    int ia[] = {0,1,2,3,4,5,6,7,8,9};
    int *beg = begin(ia);
    int *last = end(ia);
```

begin函数返回指向数组的**首元素的指针**，end函数返回指向数组**尾元素的下一个位置的指针**，
这两个函数都被定义在iterator的头文件中。使用begin和end函数就可以很好地处理数组中的元素