---
title: linux 生成ssh密钥
tags:
  - linux命令
published: true
hideInList: false
isTop: false
categories:
  - "\U0001F468\U0001F3FB‍\U0001F4BBcode"
  - mac
date: 2022-05-27 16:29:02
feature:
---


linux命令
查看密钥是否生成：ls -l ~/.ssh

生成密钥：ssh-keygen -t rsa (一路回车)

密钥所在目录：
cd ~/.ssh


私钥：id_rsa
公钥：id_rsa.pub 
