# WebSocket

[Websocket](http://baike.baidu.com/link?url=Z6A2FGqDLWzj5fPTtVadpZ4kcVhK6uxw_7vcqN7eRhAC9tpiLmRposL7nhj4XYrxlJTVuk5C--6ydKgtZ-zyH_)

WebSocket protocol 是HTML5提供的一种新的通信方式。它实现了浏览器与服务器全双工通信(full-duplex)。

[知乎大神讲解Websocket](http://www.zhihu.com/question/20215561)

## Websocket

[WebSocket 实战](http://www.ibm.com/developerworks/cn/java/j-lo-WebSocket/)

[WebSocket 协议栈](http://tools.ietf.org/html/rfc6455?cm_mc_uid=78694715613414449023553&cm_mc_sid_50200000=1453666467)


## PhoneGap中使用Websocket

anismiles的[websocket-android-phonegap](https://github.com/anismiles/websocket-android-phonegap)使得PhoneGap能够使用Websocket进行通信。

#### websocket-android-phonegap使用方法

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

参考文章《[为Phonegap Android平台增加websocket支持，使默认成为socket.io首选通道选择](http://www.thinksaas.cn/group/topic/201163/)》
