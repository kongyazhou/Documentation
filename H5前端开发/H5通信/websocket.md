# WebSocket

[Websocket](http://baike.baidu.com/link?url=Z6A2FGqDLWzj5fPTtVadpZ4kcVhK6uxw_7vcqN7eRhAC9tpiLmRposL7nhj4XYrxlJTVuk5C--6ydKgtZ-zyH_)

WebSocket protocol 是HTML5提供的一种新的通信方式。它实现了浏览器与服务器全双工通信(full-duplex)。

[知乎大神讲解Websocket](http://www.zhihu.com/question/20215561)

## Websocket协议

[WebSocket 实战](http://www.ibm.com/developerworks/cn/java/j-lo-WebSocket/)

[WebSocket 协议栈](http://tools.ietf.org/html/rfc6455?cm_mc_uid=78694715613414449023553&cm_mc_sid_50200000=1453666467)


## PhoneGap Android中使用Websocket

#### 使用cordova官方websocket插件

```
这是官方的插件，当然要用这个。
后面还介绍了两个分官方插件，仅作学习之用。
```

cordova官方websocket插件：[cordova-plugin-websocket](https://www.npmjs.com/package/cordova-plugin-websocket)

**安装方法**

	cordova plugin add cordova-plugin-websocket

**示例代码**

	document.addEventListener('deviceready', function () {
	    var ws = new WebSocket('ws://echo.websocket.org');
	 
	    ws.onopen = function () {
	        console.log('open');
	        this.send('hello');         // transmit "hello" after connecting 
	    };
	 
	    ws.onmessage = function (event) {
	        console.log(event.data);    // will be "hello" 
	        this.close();
	    };
	 
	    ws.onerror = function () {
	        console.log('error occurred!');
	    };
	 
	    ws.onclose = function (event) {
	        console.log('close code=' + event.code);
	    };
	}, false);

由于项目时间紧迫，未能深究。

其他事项请查看官网说明。

#### anismiles/websocket-android-phonegap

anismiles的[websocket-android-phonegap](https://github.com/anismiles/websocket-android-phonegap)使得PhoneGap能够使用Websocket进行通信。

 **使用方法**

1. Copy Java source into your source folder.
2. Copy websocket.js in your assets/www/js folder
3. Attach com.strumsoft.websocket.phonegap.WebSocketFactory to WebView, like this:

	@Override
	public void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		super.loadUrl(" file:///android_asset/www/index.html ");

		// attach websocket factory
		appView.addJavascriptInterface(new WebSocketFactory(appView), "WebSocketFactory");
	}

4. In your page, create a new WebSocket, and overload its method 'onmessage', 'onopen', 'onclose', like this:

	// new socket
	var socket = new WebSocket('ws://192.168.1.153:8081');
	 
	// push a message after the connection is established.
	socket.onopen = function() {
	 socket.send('{ "type": "join", "game_id": "game/6"}')
	};

	// alerts message pushed from server
	socket.onmessage = function(msg) {
	 alert(JSON.stringify(msg.data));
	};

	// alert close event
	socket.onclose = function() {
	 alert('closed');
	};


ps: It doesn't support 'onerror' event, and various states as defined by WebSocket APIs yet. I am working on it. By the way, if you like the project, join the force. 

这种方法适用于早期phonegap2.9.0版本，而目前phonegap已经更新到6.*版本，已经发生了许多变化，这种方法不再支持。

未来有时间可以考虑学习这份代码，并稍作修改使其支持最新的phonegap。

有时间的话。

#### koush/AndroidAsync

```
Asynchronous socket, http (client+server), websocket, and socket.io library for android. Based on nio, not threads.
```

koush的[AndroidAsync](https://github.com/koush/AndroidAsync)项目是github上关于Android Websocket star数最多的项目了。

有时间的话可以学习学习，看看能为否为我所用。

有时间的话。

## 服务器端websocketd

Github上的[joewalnes/websocketd](https://github.com/joewalnes/websocketd)是一款基于go语言开发的快速搭建websocket服务器的框架。

使用该框架后，服务器上的程序的标准输入输出都变成了发送和接收websocket消息。

程序可使用Python, Ruby, Perl, Bash, .NET, C, Go, PHP, Java, Clojure, Scala, Groovy, Expect, Awk, VBScript, Haskell, Lua, R, whatever!

我推荐使用python。

	websocketd --port=8080 python main.py

即可在8080端口监听websocket消息。

## 参考文章

《[为Phonegap Android平台增加websocket支持，使默认成为socket.io首选通道选择](http://www.thinksaas.cn/group/topic/201163/)》

[搭建基于Android和PhoneGap的开发环境](http://www.cnblogs.com/meteoric_cry/archive/2011/05/21/2052521.html)

[相关问题](http://zhidao.baidu.com/link?url=sO-bOraEfGMdelk9soW_4qnuvF42m45E6HDyAopHFIzu_Hh80augY2zdPweW3tFsuR6p8fi1yv-cQdXbERDPkI-T6zAxR8zJJKDNvcgiVc7)