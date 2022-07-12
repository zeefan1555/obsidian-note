---
title: vector
date: '2022-06-07 10:30'
categories:
  - "\U0001F468\U0001F3FB‍\U0001F4BBcode"
  - C++
  - C++ primer plus
tags:
  - 函数
---
# 1 用法
## 1.1 初始化
**一维数组的初始化** 
 1. `vector<int> a(10)`; 默认是0
 2. `vector<int> a(10,1)`;(10个变量每个为1)
 3. `vector<int> a(b)`; //用b向量来创建a向量，整体复制性赋值
 4. `vector<int> a(b.begin(),b.begin+3)`; //定义了a值为b中第0个到第2个（共3个）元素
 5.  int b[7]={1,2,3,4,5,9,8}; `vector<int> a(b,b+7);` //从数组中获得初值
 
**二维数组的初始化**
初始化为0
```c
vector<vector<int>> vec(row, vector<int> (col,0));
```


返回值和使用时：必须用 dp[ i ]，不能用dp(i)


# 2 原理
普通数组 int a [10]，一旦定义了就不能改变了，这个数组最多只能放10个元素了
动态数组vector，不用关心初始的大小，可以随意的添加数据

**vector的底层实现也是普通数组**。

vector的大小有两个维度一个是size一个是capicity，
size就是我们平时用来遍历vector时候用的，例如：`for (int i = 0; i < vec.size(); i++)` 
而capicity是vector底层数组（就是普通数组）的大小，capicity可不一定就是size
当insert数据的时候，如果已经大于capicity，capicity会成倍扩容，但对外暴露的size其实仅仅是+1而已，剩下的位置还是空闲的


C++中vector（可以理解是一个动态数组，底层是普通数组实现的）如果插入元素大于预先普通数组大小，vector底部会有一个扩容的操作，即申请两倍于原先普通数组的大小，然后把数据拷贝到另一个更大的数组上，然后在释放原数组内存。
eg：
原vector中的size和capicity相同都是3，初始化为1 2 3，此时要push_back一个元素4。
那么底层其实就要申请一个大小为6的普通数组，并且把原元素拷贝过去，释放原数组内存，
**注意图中底层数组的内存起始地址已经变了**。
![vector原理|800](https://img-blog.csdnimg.cn/20201218185902217.png)

所以使用vector（动态数组）来insert，是费时的，插入再拷贝的话，单纯一个插入的操作就是O(n^2)了，甚至可能拷贝好几次，就不止O(n^2)了。

解决办法：可以采用链表来进行插入操作
	eg：`vector<vector<int>> que：[[7,0],[7,1]]` →`list<vector<int>> que：[7,0]→[7,1]`


# 3 参考
[C++ vector的用法（整理）_一个幽默且帅气的程序员的博客-CSDN博客_c++ vector](https://blog.csdn.net/wkq0825/article/details/82255984?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165701148116781683956725%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165701148116781683956725&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-82255984-null-null.142^v30^control,185^v2^control&utm_term=vector%2Bc%2B%2B%2B%E7%94%A8%E6%B3%95&spm=1018.2226.3001.4187)
