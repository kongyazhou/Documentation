# jpush

```
jpush是极光推送
国内较好的推送
开元免费
支持phonegap
```

## jpush cordova插件

#### 使用方法

1). 安装JPush PhoneGap Plugin。 有两种方法。

- 方法一： 在线安装

	cordova plugin add  https://github.com/jpush/jpush-phonegap-plugin.git --variable API_KEY=your_jpush_appkey  

- 方法二：下载到本地再安装

使用git命令将jpush phonegap插件下载的本地

	git clone https://github.com/jpush/jpush-phonegap-plugin.git

将这个目录标记为$JPUSH_PLUGIN_DIR

	cordova plugin add $JPUSH_PLUGIN_DIR  --variable API_KEY=your_jpush_appkey

2). 安装cordova-plugin-device

	cordova plugin add cordova-plugin-device

3). 在js中调用函数,初始化jpush sdk

	window.plugins.jPushPlugin.init();

//由于phonegap插件采用了Lazy load的特性，    所以这里建议在js文件能执行的最开始就加

#### API说明

插件的API集中在JPushPlugin.js文件中,这个文件的位置如下

android:[YOUR__ANDROID_PROJECT]/assets/www/plugins/cn.jpush.phonegap.JPushPlugin/www
iOS:[YOUR_iOS_PROJEcT]/www/plugins/cn.jpush.phonegap.JPushPlugin/www
具体的API请参考这里

**iOS和android通用API简介**

- 停止与恢复推送服务 API

	window.plugins.jPushPlugin.init()

	window.plugins.jPushPlugin.stopPush()

	window.plugins.jPushPlugin.resumePush()

	window.plugins.jPushPlugin.isPushStopped(callback)

- 获取 RegistrationID API

	window.plugins.jPushPlugin.getRegistrationID(callback)

- 别名与标签 API

	window.plugins.jPushPlugin.setTagsWithAlias(tags,alias)

	window.plugins.jPushPlugin.setTags(tags)

	window.plugins.jPushPlugin.setAlias(alias)

- 获取点击通知内容

	event - jpush.openNotification

- 获取通知内容

	event - jpush.receiveNotification

- 获取自定义消息推送内容

	event - jpush.receiveMessage

- 通用API详细说明

**iOS API简介**

- 获取自定义消息推送内容

	event - jpush.receiveMessage

//推荐使用事件的方式传递，但同时保留了receiveMessageIniOSCallback的回调函数，兼容以前的代码

	window.plugins.jPushPlugin.receiveMessageIniOSCallback(data)

- 页面的统计

	window.plugins.jPushPlugin.startLogPageView (pageName)

	window.plugins.jPushPlugin.stopLogPageView (pageName)

	window.plugins.jPushPlugin.beginLogPageView (pageName,duration)

- 设置Badge

	window.plugins.jPushPlugin.setBadge(value)
	
	window.plugins.jPushPlugin.resetBadge()
	
	window.plugins.jPushPlugin.setApplicationIconBadgeNumber(badge)

- 本地通知

后续版本加入
- 日志等级设置

	window.plugins.jPushPlugin.setDebugModeFromIos ()

	window.plugins.jPushPlugin.setLogOFF()

[iOS API详细说明]

**android API简介**

- 获取集成日志

	window.plugins.jPushPlugin.setDebugMode(mode)

- 接收推送消息和点击通知

//下面这两个api 是兼容旧有的代码

	window.plugins.jPushPlugin.receiveMessageInAndroidCallback(data)

	window.plugins.jPushPlugin.openNotificationInAndroidCallback(data)

- 统计分析 API

	window.plugins.jPushPlugin.setStatisticsOpen(boolean)

或在 MainActivity 中的 onPause() 和 onResume() 方法中分别调用 JPushInterface.onResume(this) 和 JPushInterface.onPause(this) 来启用统计分析功能, 如果使用这种方式启用统计分析功能，则window.plugins.jPushPlugin.setStatisticsOpen(boolean) 方法不再有效，建议不要同时使用。

- 清除通知 API

	window.plugins.jPushPlugin.clearAllNotification()

- 通知栏样式定制 API

	window.plugins.jPushPlugin.setBasicPushNotificationBuilder = function()

	window.plugins.jPushPlugin.setCustomPushNotificationBuilder = function()

- 设置保留最近通知条数 API

	window.plugins.jPushPlugin.setLatestNotificationNum(num)

- 本地通知API

	window.plugins.jPushPlugin.addLocalNotification(builderId,
                                            content,
                                            title,
                                            notificaitonID,
                                            broadcastTime,
                                            extras)

	window.plugins.jPushPlugin.removeLocalNotification(notificationID)

	window.plugins.jPushPlugin.clearLocalNotifications()

## jpush服务器端

```
这里只介绍python服务器端的使用，其他语言的可以自行到相关页面查看
```

Github上[jpush-api-python-client](https://github.com/jpush/jpush-api-python-client)

#### 安装

To install jpush-api-python-client, simply:

	$ sudo pip install jpush

or alternatively install via easy_install:

	$ sudo easy_install jpush

or from source:

	$ sudo python setup.py install//没成功

推荐使用第一种。

#### 使用方法

看懂所有的examples，也就会使用jpush-api-python-client了。

那我就对examples文件夹下的例子一一分析和学习。

**push文件夹**中的example对push的参数意义做了示范。

- conf.py

配置app_key和master_secret。

- example_all.py

一个最简单的全推送。

- example_audience.py

演示了audience参数的用法，即，你可以通过配置该参数对指定的一个或一些目标推送。

- example_options.py

演示了options参数的用法，**暂时不太清楚具体的作用**。

- example_platformmsg.py

演示了platformmsg参数的用法，即你可以针对不同的平台使用定义不同的消息。

- example_silent.py

演示了silent参数的用法，即如何发送静音推送。

- example_validate.py

演示了validate参数的用法，**暂时不太清楚具体的作用**。

**device文件夹**中的example对设备(用户)管理做了示范。稍后进行学习。

## 更多内容

- [极光推送官网](https://www.jpush.cn/)
- [极光Github开源库](https://github.com/jpush/jpush-phonegap-plugin)
