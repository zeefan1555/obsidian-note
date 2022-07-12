---
title: insert函数
categories:
  - "\U0001F468\U0001F3FB‍\U0001F4BBcode"
  - C++
  - C++ primer plus
tags:
  - 函数
date: 2022-06-07 11:17:41
---


# 1 在字符串中插入
```cpp
#include <bits/stdc++.h>
using namespace std;
 
int main()
{
    string str("All that exists is what's ahead.");
    string a, b;
    a = str.insert(4,"sky");
    //在下标为4的位置，插入字符串sky
    cout << a << endl; //输出All skythat exists is what's ahead.
 
    str = "All that exists is what's ahead.";
    b = str.insert(4,5,'x');
    //在下标为4的位置，插入字符串5个字符x
    cout << b << endl; //输出 All xxxxxthat exists is what's ahead.
    return 0;
}
```

# 2 在数组下标处插入
```cpp
vector<vector<int>> que;
que.insert(que.begin() + position, people[i]);// 在下标position处插入people[i]
```

[[begin,end]]
