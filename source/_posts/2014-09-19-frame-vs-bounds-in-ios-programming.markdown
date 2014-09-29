---
layout: post
title: "frame vs. bounds in IOS programming"
date: 2014-09-19 10:07:06 +0800
comments: true
categories: [ios]
---

在學習 ios programming 的過程中, 對 frames & bounds 有點疑問
查了一下

- frames 是指對 superview 坐標系統的位置
- bounds 是指對 local 坐標系統的位置

可以看下面這張圖：
{% img center /images/Frame_bounds.png %}

- default bounds 的原點都是在 (0,0)
