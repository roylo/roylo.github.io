---
layout: post
title: "Android Learning-0"
date: 2014-07-02 09:45:04 -0800
comments: true
categories: Android
---
android training 速寫筆記 - 0
<!-- more -->

## 相關知識
### Android 四大元件
- 透過 Intent 去操作各個元件
- Acitvity
   - 控制 UI
   - 控制程式狀態 (active)
   - Fragment (替換螢幕上的 component)
- Service
   - Start/Stop
   - onBind
   - 不會因為退到背景或是關上螢幕而暫停
- Broadcast Receiver
   - GCM (google cloud message)
   - APN, WPN
- Content Provider
   - 提供 App 之間資源交換
   - Intent 不會直接來驅動

### Eclipse notation
- 綠C => class
- 紫I => interface
- A => abstract
- F => Final
- S => Static
- member function => method (實心)
- member variable => field (空心)
- 實心三角形 Override (parant class)
- 空心三角形 Override (interface method)

### developement env setup
- 下載 android ADT from [ADT download](http://developer.android.com/sdk/index.html)
- 解壓縮, 開啟資料夾內的 Eclipse
- 點選右上角的 open perspective, 開啓 Java
- 開啓左上角的 Android SDK manager 下載需要的 SDK tools

### 資料夾相關
- in ~/adt/sdk/
   - tools -> 版本無關 (sqlite3
   - platform-tools -> 版本相關 (adb

### new project
- Min SDK: Device 最早版本
   - in AndroManifest.xml
- Target SDK: Device 預期版本
   - in AndroManifest.xml
- compile with: SDK binary
   - with Eclipse 專案 (選用穩定的 release

### Hello World
1. layout (XML) => hello World
2. Main Activity extends Activity
3. Activity load layout
4. add to AndroManifest.xml

### ADB
``` sh
 # 查看 adb 有哪些 devices
 adb devices

 # 移除 app (ex. com.mycompany.myapp
 adb uninstall <pkg name>
```
### eclipse
####常用快捷鍵
organize input: command + shift + o
Line Comments: command + /
Line Move: 選取block , alt + up/ alt + down
Auto format: command + shift + f

#### 小技巧
- type hierarchy
   - 可以看到 class 的 hierarchy
- auto complete -> content assist
- 按住 command + 左鍵點 class name -> 打開對應的 class src code

### Other knowledge
- CPU
   - A (application)
   - B (binary)
   - I (interface)
通常會有 armv7a, intel.x86, (mips from 大陸)

- ADT: Android developement Tool
- ADB: Android Debug Briedge
- AVD: Android Virtual Device

- 每一個 app 都是 apk 檔
   - 壓縮檔, 解開會是 dir
   - /myapp 裡有 AndroManifest.xml, 裡面寫有 app 相關的設定
      - package -> unique name
- genymotion
   - android 模擬器
   - x86 架構, 在 mac 上面跑快很多 orz
