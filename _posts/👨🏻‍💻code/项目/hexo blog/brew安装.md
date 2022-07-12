---
title: brew安装
tags:
  - mac下软件安装
published: true
hideInList: false
isTop: false
categories:
  - "\U0001F468\U0001F3FB‍\U0001F4BBcode"
  - 项目
  - hexo blog
date: 2022-05-28 15:16:24
feature:
---
![](https://s1.vika.cn/space/2022/05/28/0b3ffbfe5ad64d388d02bceff24ab6a0)


用官网安装出现以下错误：
```
curl: (7) Failed to connect to raw.githubusercontent.com port 443: Connection refused
```
原因是：**github 的一些域名的 DNS 解析被污染**，导致DNS 解析过程无法通过域名取得正确的IP地址

换成国内下载地址即可
```
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```

根据终端反应输入即可，过程中有中文提示
