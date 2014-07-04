---
layout: post
title: "Octopress 新手教學"
date: 2014-06-29 16:23:38 +0800
comments: true
categories: Octopress
---

會寫這篇純粹是給健忘的自己怎麼使用 Octopress, 至少把一些基礎寫出來免得老是忘記重看<br/>
首先從如何設定 Octopress 開始, 可以參考他們的[官網](http://octopress.org/)<br/>
讓可愛的小章魚教導你XD

<!-- more -->
## 1. Octopress Setup PreStage
> 首先安裝 [git](http://git-scm.com/)

> 安裝 Ruby 1.9.3 以上版本, 官網建議可以用 [rebnv](http://octopress.org/docs/setup/rbenv) 或是 [RVM](http://octopress.org/docs/setup/rvm)

印象中我在裝 Ruby 的時候遇到了一點麻煩, mac 本身也有內建 Ruby. 詳細怎麼解決我已經忘記了XD <br/>
反正要確保你有裝到 Ruby 就是了(挖鼻孔, 但是不用裝到 RoR

## 2. Octopress Setup
從 git 上把 octopress 抓下來
``` ruby
git clone git://github.com/imathis/octopress.git octopress
cd octopress
```

安裝一些 dependencies, 其實我還不太懂這些...很懶得研究
```
gem install bundler
rbenv rehash # If you use rbenv, rehash to be able to run the bundle command
bundle install
```

安裝 default 的 Octopress theme
```
rake install
```

## 3. 設定 Octopress Deploy
Octopress 的好處是他是純靜態的網頁, 所以我們可以輕易的將文章 Deploy 到別的機器<br/>
它可以是 Github page, 也可以是你自己 own 的 Web Server<br/>

官網上介紹了三種 Deploy 的方法：

1. [Github page](http://octopress.org/docs/deploying/github)
2. [Heroku](http://octopress.org/docs/deploying/heroku)
3. [Rsync](http://octopress.org/docs/deploying/Rsync)

後來自己選了 Github page, 滿容易設定也滿方便的! <br/>
畢竟身為一個偽 Nerd, 有個 Github 是基本

## 4. 設定 Octopress config
Octopress 本身的設定透過 Yml 檔來 config, 提供了相當多的參數可以調整<br/>
但是基於本人懶惰的個性, 只有稍微看了一下, 沒有多調, 等到以後有需要再說吧XD <br/>
設定的說明可以參考 [這裡](http://octopress.org/docs/configuring/)

## 5. 開始 Blog!!
其實我寫這篇的目的純粹是為了記錄寫 blog 的指令 = =a <br/>
但是我龜毛的個性促使我寫稍微完整一點 <br/>

blogging 相關的指令都靠 rake 來做, Octopress 已經將複雜的指令簡化 <br/>
所以記得下面這些就可以囉~

而 Octopress 可以使用 markdown 的語法來寫 blog <br/>
Markdown 的語法可以參考 [markdown 語法](http://markdown.tw/)

### New post
透過 rake_post 指令, Octopress 會自動產生好一個 markdown, 並且放在 _posts/ 資料夾下 <br/>
預設的 naming 會是 Y-m-d-title.markdown 的格式, 滿清楚的, 而且支援中文喔!!

```
rake new_post["Zombie Ninjas Attack: A survivor's retrospective"]
# Creates source/_posts/2011-07-03-zombie-ninjas-attack-a-survivors-retrospective.markdown
```
而這個檔名也會決定你網站的 Url, 譬如說上面這個 example 的路徑就會是
> http://site.com/blog/2011/07/03/zombie-ninjas-attack-a-survivors-retrospective/index.html

### New page
除了常用到的 blog uri 之外, 你也可以自己建立 page

```
rake new_page[super-awesome]
# creates /source/super-awesome/index.markdown
rake new_page[super-awesome/page.html]
# creates /source/super-awesome/page.html 
```

markdown 名稱若是 `abc.markdown`, Octopress 會 parse 建立成 `site.com/abc.html`<br/>
如果希望建立成 `site.com/abc/`, 就要把檔案弄成 `abc/index.markdown`

### 常用語法
`<!-- more -->`
可以在 content 裡面寫這個, 這樣在此行之下的內容就不會顯示在首頁

`rake generate`
將 `_posts/` 下面的 markdown parse 並放入`_public` 的資料夾內

`rake preview`
會在 local 端起一個 Server, 預覽文章

`rake watch`
可以監測 `source/` 和 `sass/` 資料夾下是否已異動, 有的話就做 regenerate

`rake deploy`
可以發佈到設定好的遠端 server 上

### Code Style
Octopress 最有特色的點就是易於 sharing code fragment, 而他也提供了非常多 syntax 的顯示方式 <br/>
詳細可以參考 [Octopress code syntax](http://octopress.org/docs/blogging/code/)

## 7. 結語
這第一篇文章只粗淺的介紹了 Octopress, 其實 Octopress 的功能是非常強大的<br/>
等以後有用到的話再來介紹吧~ <br/>

作為第一篇讓我練習寫的 blog 文章, 應該夠了 (其實是煩了XD
