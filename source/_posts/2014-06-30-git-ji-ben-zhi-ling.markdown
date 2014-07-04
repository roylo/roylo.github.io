---
layout: post
title: "git 基本指令"
date: 2014-06-30 14:47:41 +0800
comments: true
categories: git
---
記錄一下工作上用到的 git 指令, 免得老是在查 Orz
<!-- more -->

``` sh
 # local 切出一個 branch
 git checkout <branch_name>

 # delete local 的 branch
 git branch delete -d <branch_name>

 # delete remote 的 branch
 git push origin --delete <branch_name>

 # 在 local 建立一個新的 branch
 git checkoutout -b <branch_name>

 # push local branch 到 remote server
 git push origin <branch_name>
```

+ 如何 checkout remote branch 回 local 端?
``` sh
 # after git version 1.6.6, 可以直接下
 git fetch
 git checkout <branch_name>

 # ==========================================

 # old git version
 git fetch origin
 # 查詢哪些 branch 可以 checkout
 git branch -v -a
 # checkout 回 local 端
 git checkout -b <branch_name> origin/<branch_name>
```
