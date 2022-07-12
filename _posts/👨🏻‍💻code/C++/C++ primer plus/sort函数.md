---
categories:
  - "\U0001F468\U0001F3FB‍\U0001F4BBcode"
  - C++
  - C++ primer plus
---

sort函数默认从小到大排列，如需自定义需要额外写个函数
```cpp
static bool cmp(int a, int b) {
    return abs(a) > abs(b); // 返回绝对值大的
}
```
# 1 应用
## 1.1 按照绝对值从大到小排列，
```cpp
static bool cmp(int a, int b) {
    return abs(a) > abs(b);
```
## 1.2 从大到小排列：[[14.根据身高重建队列]]
```cpp
// 身高从大到小排（身高相同k小的站前面）
static bool cmp(const vector<int>& a, const vector<int>& b) {
        if (a[0] == b[0]) return a[1] < b[1];
        return a[0] > b[0];
    }
```

bool 值好像是规定的 #疑问 
```cpp
   sort(A.begin(), A.end(), cmp); // 第三个参数不用出入参数这是规则
```

[[static 关键字]]
