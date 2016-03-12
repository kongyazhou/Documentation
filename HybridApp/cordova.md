# Cordova

```
Cordova提供了一组设备相关的API，通过这组API，移动应用能够以JavaScript访问原生的设备功能，如摄像头、麦克风等。
```

[cordova插件官方查询页面](http://cordova.apache.org/plugins/)


## 常用命令

- 安装 Cordova

	npm install -g cordova

- 创建项目

	cordova create MyApp

- 添加支持的平台

	cordova platform add <platform name>

- 添加插件

	cordova plugin add <plugin name>

- 运行你的app

	cordova run <platform name>

- 构建你的app

	cordova build <platform name>

## 常用插件介绍

#### 推送插件phonegap-plugin-push

[谷歌GCM推送插件phonegap-plugin-push](https://www.npmjs.com/package/phonegap-plugin-push)，实现推送消息，可惜谷歌被墙不能用

[ 跨平台移动开发phonegap/cordova 3.3全系列教程-百度云推送push](http://blog.csdn.net/mansai/article/details/19073913)，这什么年代的了

[百度云推送官网](http://push.baidu.com/)，并没有phonegap插件。

[Android版添加phonegap--百度云插件教程](https://www.douban.com/note/530249993/?type=like)，是最近的，可是看不懂

[极光推送jPush](https://github.com/jpush/jpush-phonegap-plugin)，一直在维护，这个可以有

另外还有个[极光IM](https://github.com/jpush/jmessage-phonegap-plugin)，强

#### websocket插件

[cordova-plugin-websocket-server](https://www.npmjs.com/package/cordova-plugin-websocket-server)

[cordova-plugin-websocket](https://www.npmjs.com/package/cordova-plugin-websocket)

## 自己动手制作cordova插件

```
由于有the Great Fire Wall的存在，而国内phonegap相关支持非常薄弱，所以有时不得不自己去做插件才能满足需求。
```

[官方制作说明](http://cordova.apache.org/docs/en/latest/guide/hybrid/plugins/index.html)

```
这部分是个大工程，我们一步一步来。
```

#### plugin.xml

[官网详解plugin.xml](http://cordova.apache.org/docs/en/latest/plugin_ref/spec.html)

The plugin repository must feature a top-level plugin.xml manifest file.

	<?xml version="1.0" encoding="UTF-8"?>
    <plugin xmlns="http://apache.org/cordova/ns/plugins/1.0"
            id="cordova-plugin-device" version="0.2.3">
        <name>Device</name>
        <description>Cordova Device Plugin</description>
        <license>Apache 2.0</license>
        <keywords>cordova,device</keywords>
        <js-module src="www/device.js" name="device">
            <clobbers target="device" />
        </js-module>
        <platform name="ios">
            <config-file target="config.xml" parent="/*">
                <feature name="Device">
                    <param name="ios-package" value="CDVDevice"/>
                </feature>
            </config-file>
            <header-file src="src/ios/CDVDevice.h" />
            <source-file src="src/ios/CDVDevice.m" />
        </platform>
    </plugin>

The top-level **plugin tag's** id attribute uses the same reverse-domain format to identify the plugin package as the apps to they're added. 

The **js-module tag** specifies the path to the common JavaScript interface. 

The **platform tag** specifies a corresponding set of native code, for the ios platform in this case. 

The **config-file tag** encapsulates a feature tag that is injected into the platform-specific config.xml file to make the platform aware of the additional code library. 

The **header-file and source-file tags** specify the path to the library's component files.

#### The JavaScript Interface

The JavaScript provides the front-facing interface, making it perhaps the most important part of the plugin. 

You can structure your plugin's JavaScript however you like, but you need to call cordova.exec to communicate with the native platform, using the following syntax:

    cordova.exec(function(winParam) {},
                 function(error) {},
                 "service",
                 "action",
                 ["firstArgument", "secondArgument", 42, false]);

Here is how each parameter works:

- function(winParam) {}: A success callback function. Assuming your exec call completes successfully, this function executes along with any parameters you pass to it.

- function(error) {}: An error callback function. If the operation does not complete successfully, this function executes with an optional error parameter.

- "service": The service name to call on the native side. This corresponds to a native class, for which more information is available in the native guides listed below.

- "action": The action name to call on the native side. This generally corresponds to the native class method. See the native guides listed below.

- [/* arguments */]: An array of arguments to pass into the native environment.

#### Sample JavaScript

This example shows one way to implement the plugin's JavaScript interface:

    window.echo = function(str, callback) {
        cordova.exec(callback, function(err) {
            callback('Nothing to echo.');
        }, "Echo", "echo", [str]);
    };

In this example, the plugin attaches itself to the window object as the echo function, which plugin users would call as follows:

    window.echo("echome", function(echoValue) {
        alert(echoValue == "echome"); // should alert true.
    });

Look at the last three arguments to the cordova.exec function. The first calls the Echo service, a class name. The second requests the echo action, a method within that class. The third is an array of arguments containing the echo string, which is the window.echo function's the first parameter.

The success callback passed into exec is simply a reference to the callback function window.echo takes. If the native platform fires the error callback, it simply calls the success callback and passes it a default string.


#### Native Interfaces

Once you define JavaScript for your plugin, you need to complement it with at least one native implementation. Details for each platform are listed below, and each builds on the simple Echo Plugin example above:

Android Plugins
iOS Plugins
BlackBerry 10 Plugins
Windows Phone 8 Plugins
Windows Plugins

#### Publishing Plugins

Once you develop your plugin, you may want to publish and share it with the community. You can publish your plugin to any npmjs-based registry, but the recommended one is the NPM registry. Please read our publishing plugins to npm guide.

**NOTE**: Cordova plugin registry is moving to a read-only state. publish/ unpublish commands have been removed from plugman, so you'll need to use corresponding npm commands.

Other developers can install your plugin automatically using either plugman or the Cordova CLI. (For details on each development path, see Using Plugman to Manage Plugins and The Command-Line Interface reference.)

To publish a plugin to NPM registry you need to follow steps below:

- create package.json file for your plugin:

	$ plugman createpackagejson /path/to/your/plugin
- publish it:

	$ npm adduser # that is if you don't have an account yet
	$ npm publish /path/to/your/plugin
That is it!

Running plugman --help lists other available registry-based commands.

## 通过Cordova调用系统功能

#### 摄像头

#### 麦克风

#### 

## 存储

WebSQL

[W3C WebSQL介绍](http://dev.w3.org/html5/webdatabase/)

## 事件

**Event Types**

- deviceready
- pause
- resume
- backbutton
- menubutton
- searchbutton
- startcallbutton
- endcallbutton
- volumedownbutton
- volumeupbutton

**Events added by cordova-plugin-battery-status**

- batterycritical
- batterylow
- batterystatus

**Events added by cordova-plugin-network-information**

- online
- offline


## 图标和启动画面

Icons and Splash Screens

## 参考资料

- [Cordova百度词条](http://baike.baidu.com/link?url=Xn-bGwsdEccufFTY9TSxuk_vjOMS3hoxPYOz-mhG2d1b4VCzQNzw73SoeICtwfdG0TyUt5V2whQGHuhfbSjex_)
- [Cordova官网](http://cordova.apache.org/)
- [Apache Cordova 教程](http://wiki.jikexueyuan.com/project/apache-cordova-tutorial/)——极力推荐！
- [极光推送](https://www.jpush.cn/)