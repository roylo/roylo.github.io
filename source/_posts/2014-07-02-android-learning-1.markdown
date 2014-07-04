---
layout: post
title: "Android learning-1"
date: 2014-07-02 15:28:58 +0800
comments: true
categories: Android
---
android training 速寫筆記 - 1
<!-- more -->

## Android 相關
- acore: android core
- onXXXX function 都是 callback function, 僅會由 android 來呼叫
- ViewGroup class
   - 處理 layout
   - 使用相對的方式去做大小設定
- 透過 xml 的描述定義螢幕顯示

## 使用者介面實作
- xxx.xml
   - lowercase
   - no special character
   - number cna't be leading

- layout 大小
   - match parent (大)
      - 填滿 parent
   - wrap content (小)
      - 只要大小可以把內容包起來就好
