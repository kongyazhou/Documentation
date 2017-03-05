# PhoneGap

* [概述](#概述)
* [调试](#调试)
* [构建](#构建)
* [PhoneGap事件](#PhoneGap事件)
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

## PhoneGap事件

#### deviceready 事件

在使用PhoneGap开发应用时，deviceready事件是非常常用的。这一事件在设备的本地环境和页面完全加载完成之后才触发

注意：此事件一般晚于jquery 的ready事件，jquery的ready事件是在DOM 完全加载完成后触发，deviceready则是设备的本地环境和页面完全加载完成之后才触发

PhoneGap包含两个基础，native和JavaScript，当native加载的时候，自定义的一些图片会被调用，而JavaScript需要在DOM加载后就会被加载。这是可能造成JavaScript在图片加载前就已经被调用了。使用deviceready事件可以很好的解决这类问题，他可以保证PhoneGap是在完全加载完成后，才会被触发。

#### pause  事件

当PhoneGap应用被置为后台时触发

#### resume事件

当PhoneGap应用重新从后台置为前台时触发

#### online事件

当PhoneGap应用连接因特网时触发

#### offline 事件

当PhoneGap应用断开因特网时触发

#### backbutton事件

当单击退回按钮时触发

#### menubutton 事件

当单击菜单按钮时触发

#### batterycritical事件

当PhoneGap应用监控到电池达到警告时触发（20%）

batterycritical的处理程序将会调用一个对象，该对象包含以下两个属性： 
•    level：电池剩余电量的百分比，取值范围是0-100。(数字类型) 
•    isPlugged：boolean型的值，表示设备是否接通电源。 

#### batterylow事件

在电量非常低的情况下触发（5%）
batterylow的处理程序将会调用一个对象，该对象包含以下两个属性： 
•    level：电池剩余电量的百分比，取值范围是0-100。(数字类型) 
•    isPlugged：boolean型的值，表示设备是否接通电源。 

#### batterystatus事件

PhoneGap应用监控到电池状态有改变时触发（每当电量变化1%的时候触发一次）

batterystatus的处理程序将会调用一个对象，该对象包含以下两个属性： level：电池剩余电量的百分比，取值范围是0-100。(数字类型) 
isPlugged：boolean型的值，表示设备是否接通电源。


## 参考资料

- [PhoneGap官网](http://phonegap.com/)
- [PhoneGap Build](https://build.phonegap.com/apps)
- [PhoneGap百度百科词条](http://baike.baidu.com/link?url=uPq1YgbpfeI6r2fKCGDk02GKxNczIkfPqw-fnaef45D0Sdl_ziUQLVhtwP53W3pAjMPNa5mQqXkS0qwnlkTEqK)

