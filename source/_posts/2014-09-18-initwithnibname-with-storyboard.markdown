---
layout: post
title: "initWithNibName with Storyboard"
date: 2014-09-18 15:57:20 +0800
comments: true
categories: [ios]
---

在過去 ios 的開發還是使用 xib 來做 UI 的時候

常常會在 `initWithNibName` 去做一些 initialization, 但是到 storyboard 的時候
就不會去呼叫這個 function , 那個該寫什麼來取代呢?

舊的寫法(當使用 xib)：
``` objc
- (id) initWithNibName: (NSString *)nibNameOrNil bundle:(NSBundle *)nibBundleOrNil
{
    self = [super initWithNibName:nibNameOrNil bundle:nibBundleOrNil];
    if (self) {
        ....
    }

    return self;
}
```
新的寫法(當使用 storyboard)：
``` objc
- (id)initWithCoder:(NSCoder *)aDecoder
{
    self = [super initWithCoder:aDecoder];
    if (self) {
        ....
    }

    return self;
}
```

