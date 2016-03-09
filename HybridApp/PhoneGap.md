# PhoneGap

* [概述](#概述)
* [调试](#调试)
* [构建](#构建)
* [参考资料](#参考资料)

## 概述

**PhoneGap是一个**用基于HTML，CSS和JavaScript的，**创建移动跨平台应用程序的快速开发平台**。

它使移动Web应用能够利用iPhone，Android，Palm，Symbian,WP7,WP8,Bada和Blackberry智能手机的核心功能——包括地理定位，加速器，联系人，声音和振动等。

此外PhoneGap还拥有丰富的插件可以调用。

业界很多主流的移动开发框架均源于PhoneGap。

较著名的有Worklight、appMobi、WeX5等。其中WeX5是国产的。

```
PhoneGap为HybridApp开发提供了强大的构建和调试平台。
```

## 构建

构建有离线和在线两种方式，推荐在线构建，简单方便。

####  在线构建

使用PhoneGap Build在线构建

PhoneGap Build是一款非常强大的在线构建工具，能够将Github上的PhoneGap移动Web项目在线编译成移动平台应用。

即在线将HTML编译成apk等。

#### 离线构建

在项目根目录路径下输入：

	cordova build android

生成的apk文件在platforms/android/build/outputs/apk文件夹下

```
更多操作见《cordova》
```

## 调试

在电脑上使用PhoneGap，打开项目，便会生成一个网站。

在手机上用PhoneGap Developer应用访问即可预览效果。

#### PhoneGap Developer

- iOS直接到App Store即可下载PhoneGap Developer。

- Android版从Google Play中下载PhoneGap Developer。

使用Google Play商店需要翻墙，**请使用lantern-android**，使用其他软件可能导致无法下载。

如果找不到官方的下载lantern-android的方法，可以使用百度云盘上的beta版备份。

#### GapDebug

一款针对PhoneGap移动开发的开发调试软件。

PhoneGap生成的APP在手机上运行时，连上电脑，打开该软件，能够看到源码，以及代码的实时动态。

## 参考资料

- [PhoneGap官网](http://phonegap.com/)
- [PhoneGap Build](https://build.phonegap.com/apps)
- [PhoneGap百度百科词条](http://baike.baidu.com/link?url=uPq1YgbpfeI6r2fKCGDk02GKxNczIkfPqw-fnaef45D0Sdl_ziUQLVhtwP53W3pAjMPNa5mQqXkS0qwnlkTEqK)

