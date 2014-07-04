---
layout: post
title: "ack - better grep!"
date: 2014-07-03 22:51:36 +0800
comments: true
categories: [shell, unix, cmd]
---
Ack - 專門給 programmer 用的 grep !  
晚上隨便看看網頁吸收新知, 看到了這個 [ack](http://beyondgrep.com/) 感覺對工作上會很有幫助啊!!  
稍微試了一下, 感覺的確是滿不錯的, 取代 grep 的功能 ^o^  

下面就來看看怎麼使用 ack 吧~
<!-- more -->

## 安裝 ack
ack 提供很多種安裝的方式, 各種平台上幾乎都有 pkg  
以我自己而言, mac 上可以直接用 homebrew 安裝  
其他平台可以參考[這裡](http://beyondgrep.com/install/)
``` sh
brew install ack
```

另外 ack 也提供直接 curl 下載執行檔便於攜帶, 只要執行下面的指令 <br />
ack 就會放到 ~/bin/ack 囉~
``` sh
curl http://beyondgrep.com/ack-2.12-single-file > ~/bin/ack && chmod 0755 !#:3
```

## Why ack?
ack 看起來有幾個不錯的效果, 截取一些對我有吸引力的部分

+ 快! (最重要的事情
+ 自動省略一些像是 version control 的dir(還有一些其他的), 像 grep 每次搜尋 .svn 都讓我惱火
+ portable, ack 是純 perl, 只需要 perl5 就可以執行
+ 可以指定搜尋的 file type 還滿方便
+ 可以拿來找某個 type 的 file list
+ ack 三個字比 grep 四個字少打一個字XDDD, 官網的這項優點讓我笑了

## ack 簡易教學
功能太多, 列一些看到不錯的 <br />
詳細可以參考 [ack manual](http://beyondgrep.com/documentation/ack-2.12-man.html)
``` sh
# ack ignore CVS, .svn, .git, and other ignored directories
ack 'search string'

# 只搜尋某種 file type, ack --type string
ack --php test

# 列出將會搜尋的 filename, 但不真的 search
ack -f
# 搭配一下 --type 就可以拿來搜尋 filename, 或是做一些其他事情
# remove all files of type html
ack -f --html --print0 | xargs -0 rm -f

# 搜尋所有的檔案不要忽略
ack -a test
```

## Compare to GNU global
跟 global 相比, 我覺得用處上還是有些區別  
global 基本上是要建 index file  
這對 code base 很大的時候是相當有用的, 加快搜尋的速度  
但缺點也是因為他要建 index file, 有時候並不方便 (畢竟我不會到處去建 index)  

ack 對比之下更接近 grep 的用法, 可以隨時 search 會方便的多  
尤其在公司的 server 上不可能用 global, 這時候就是 ack 發揮效用的時候了!!  

## ack for VIM!
最後就是 ack 還有做 vim 的 plugin  
可以參考一下 [ack for vim](http://www.vim.org/scripts/script.php?script_id=2572)
