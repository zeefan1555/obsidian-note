---
title: c++中 - ‘0’ 以及 -'a' 的相减操作解释
date: '2022-06-15 11:10'
categories:
  - "\U0001F468\U0001F3FB‍\U0001F4BBcode"
  - C++
  - C++ primer plus
tags:
  - null
---


#flashcards/代码随想录/知识点 
c++中 - ‘0’ 以及 -'a' 的相减操作解释
?
# 1 将数字字符转为整形变量
```cpp
// 将str 字符串"1234"里的各个数字字符转成整型，存入整型数组x：
char str[]="1234";
int x[4] = 0;
for (int i=0; i<4; i++) x[i] = str[i] - '0'; 
```
>数字字符减去‘0’就得到了该数字。减去字符0，也就是减去0的ASCII码值48。
# 2 将字母由小写转为大写
字母字符- 'a'得到 该字母下的下标
```cpp
// 把字符串中字母，小写变大写
char str[]="aBcxYz";
for (int i=0; i<strlen(str); i++)
if (str[i] >='a' && str[i] <='z') str[i] = str[i] -'a' + 'A';
```
## 2.1 取到字母字符对应的数字：a→0，b→1....
原理：a - 'a' = 0, b - 'a' = 1 .....
```cpp
int hash[27] = {0};
S = "ababcbacadefegdehijhklij"// S[0] - 'a'= 0
for (int i = 0; i < S.size(); i++) { 
            hash[S[i] - 'a'] = i; //
        }
```
[[19.划分字母区间#^dhg2oc]]
[01:03](file:///Users/yibeikongqiu/Desktop/ishot%E8%A7%86%E9%A2%91/%E8%B4%AA%E5%BF%83%E7%AE%97%E6%B3%95/19.%E5%88%92%E5%88%86%E5%AD%97%E6%AF%8D%E5%8C%BA%E9%97%B4(carl).mp4#t=63.222835) 
	S = "**a**babcbac**a**defegdehijhklij"
	将每一个字母的所对应的下标值放到了hash数组里了，相同字母的是更新的，因为 S[1] - 'a'= S[6] - 'a' = 0 



