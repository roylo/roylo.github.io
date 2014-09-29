---
layout: post
title: "GC overhead limit exceeded in Eclipse"
date: 2014-09-19 14:22:44 +0800
comments: true
categories: [eclipse,android]
---

今天在測試公司的 android project 的時候，跑 demo app eclipse 一直掛點

最後會出現 `GC overhead limit exceeded in Eclipse`

查了一下發現是給 eclipse instance 的記憶體用量不夠

可以調整設定來 fix

設定檔的位置在 eclipse 安裝路徑裡面的 `eclipse.ini`

找一下就可以找到

```
-startup
plugins/org.eclipse.equinox.launcher_1.3.0.v20130327-1440.jar
--launcher.library
plugins/org.eclipse.equinox.launcher.gtk.linux.x86_64_1.1.200.v20140116-2212
-product
org.eclipse.epp.package.jee.product
--launcher.defaultAction
openFile
-showsplash
org.eclipse.platform
--launcher.XXMaxPermSize
256m
--launcher.defaultAction
openFile
--launcher.appendVmargs
-vmargs
-Dosgi.requiredJavaVersion=1.6
-XX:MaxPermSize=256m
-Xms40m
-Xmx512m
```

- `xms` 指的是一開始 init 給的記憶體用量
- `xmx` 指的是最多可以用到的記憶體用量
- `xx` 原文是 Permanent Generation defines the memory allocated to keep compiled class files , 其實不太了解

最後我調整 `Xms512m`, `Xmx1024m`, `XX:MaxPermSize=1024m`, 這樣再去 run demo program 就可以囉~
