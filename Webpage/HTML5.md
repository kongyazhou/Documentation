# HTML5

[表单的GET和POST方法](http://blog.csdn.net/wzwenhuan/article/details/7803510)

[用画图软件修改图片像素](http://jingyan.baidu.com/article/cdddd41c59463653cb00e1d4.html)

注释：Internet Explorer 8 以及更早的版本不支持 <video> 标签。
格式      IE     Firefox      Opera      Chrome        Safari
Ogg     No      3.5+         10.5+      5.0+          No
MPEG4  9.0+      No       No        5.0+          3.0+
WebM    No      4.0+         10.6+      6.0+          No
 
NO：代表不支持这款浏览器。
X.0+：表示支持这款及版本更高的浏览器



video 元素允许多个 source 元素。source 元素可以链接不同的视频文件。浏览器将使用第一个可识别的格式：
实例
    <video width="320" height="240" controls="controls">
        <source src="movie.ogg" type="video/ogg">
        <source src="movie.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>



## WebSocket

是HTML5所支持的socket

服务器端倾力推荐[Websocketd](https://github.com/joewalnes/websocketd)

Websocketd能够迅速建立起一套基于Websocket协议的服务器端环境。
