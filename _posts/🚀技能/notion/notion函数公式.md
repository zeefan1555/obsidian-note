---
title: notion函数公式
date: '2022-06-15 13:26'
categories:
  - "\U0001F680技能"
  - notion
tags:
  - notion
---



notion函数公式

# 1 时间公式
```cpp
开始的后两位：toNumber(slice(prop("开始"),3))
结束的后两位：toNumber(slice(prop("结束"),3))

开始的前两位：toNumber(slice(prop("开始"),0,2))
结束的前两位：toNumber(slice(prop("结束"),0,2))


相减的分钟数：(toNumber(slice(prop("结束"),3))-toNumber(slice(prop("开始"),3)))
相减的小时数：(toNumber(slice(prop("结束"),0,2))-toNumber(slice(prop("开始"),0,2)))

小时+分钟：
floor((toNumber(slice(prop("结束"), 0, 2)) - toNumber(slice(prop("开始"), 0, 2)) + (toNumber(slice(prop("结束"), 3)) - toNumber(slice(prop("开始"), 3))) / 60) * 100) /100 


//不借位
if(toNumber(slice(prop("结束"), 3)) >= toNumber(slice(prop("开始"), 3)), floor((toNumber(slice(prop("结束"), 0, 2)) - toNumber(slice(prop("开始"), 0, 2)) + (toNumber(slice(prop("结束"), 3)) - toNumber(slice(prop("开始"), 3))) / 60) * 100) / 100, 0)

//借位
floor((toNumber(slice(prop("结束"), 0, 2))-1 - toNumber(slice(prop("开始"), 0, 2)) + (toNumber(slice(prop("结束"), 3))+60 - toNumber(slice(prop("开始"), 3))) / 60) * 100) /100


//时间计算总函数：已通过
if(toNumber(slice(prop("结束"), 3)) >= toNumber(slice(prop("开始"), 3)), floor((toNumber(slice(prop("结束"), 0, 2)) - toNumber(slice(prop("开始"), 0, 2)) + (toNumber(slice(prop("结束"), 3)) - toNumber(slice(prop("开始"), 3))) / 60) * 100) / 100, floor((toNumber(slice(prop("结束"), 0, 2)) - 1 - toNumber(slice(prop("开始"), 0, 2)) + (toNumber(slice(prop("结束"), 3)) + 60 - toNumber(slice(prop("开始"), 3))) / 60) * 100) / 100)

//时间范围改造函数
if(toNumber(slice(prop("结束"), 3)) >= toNumber(slice(prop("开始"), 3)), format((toNumber(slice(prop("结束"), 0, 2)) - toNumber(slice(prop("开始"), 0, 2)))+ "h" + format((toNumber(slice(prop("结束"),3))-toNumber(slice(prop("开始"),3)))) +"m" , "0")
```

时间范围
```cpp
format(toNumber(slice(prop("结束"), 3)) - toNumber(slice(prop("开始"), 3))) + "m"
//不借位
format(toNumber(slice(prop("结束"), 0, 2)) - toNumber(slice(prop("开始"), 0, 2))) + "h" + format(toNumber(slice(prop("结束"), 3)) - toNumber(slice(prop("开始"), 3))) + "m"

//借位
format(toNumber(slice(prop("结束"), 0, 2))-1 - toNumber(slice(prop("开始"), 0, 2))) + "h" + format(toNumber(slice(prop("结束"), 3))+60 - toNumber(slice(prop("开始"), 3))) + "m"
```



写notion公式的心得：把零件找出来，在组装