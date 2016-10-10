JavaScript
==========

JavaScript是最常用的网络的脚本语言，你可以通过阅读  [W3C教程](http://www.w3school.com.cn/js/index.asp/)来学习它。

## 目录
* [简介](#简介)
* [自动性能优化](#自动性能优化)
* [jQuery](#jQuery)
* [holderjs](#holderjs)
* [AngularJS](#AngularJS)
* [BackboneJS](#BackboneJS)
  * [安装](#安装)
  * [快速上手](#快速上手)
  * [jello 命令](#jello 命令)
  * [模板继承](#模板继承)
  * [模板数据绑定](#模板继承)
  * [页面模拟](#页面模拟)
  * [插件说明](#插件说明)
  * [配置](#配置)
  * [后端整合](#后端整合)
  * [fis.properties](#fisproperties)
  * [更多资料](#更多资料)


## 简介

```
JavaScript 是属于网络的脚本语言！
JavaScript 被数百万计的网页用来改进设计、验证表单、检测浏览器、创建cookies，以及更多的应用。
JavaScript 是因特网上最流行的脚本语言。
JavaScript 很容易使用！你一定会喜欢它的！
```




## jQuery

## holderjs

## AngularJS

前端JS框架

## RequireJS

RequireJS在线项目地址：[Github](https://github.com/jrburke/requirejs/)
RequireJS官方网站：[官网](http://requirejs.org/)

### 简介

```
RequireJS 是一个JavaScript模块加载器。
它非常适合在浏览器中使用，但它也可以用在其他脚本环境, 就像 Rhino and Node.使用RequireJS加载模块化脚本将提高代码的加载速度和质量。

RequireJS会让你以不同于往常的方式去写JavaScript。
你将不再使用script标签在HTML中引入JS文件，以及不用通过script标签顺序去管理依赖关系。
```

### Jello方案中使用RequireJS的准备工作

1. 从官网下载require.js[地址](http://www.requirejs.cn/docs/download.html)
2. 将下载下来的require.js放到项目目录下的/static/js文件夹下。

### Velocity模板引擎中RequireJS的使用方法

    //网页头部必须声明才能使用RequireJS
    #html("/static/js/require.js")

    //Velocity使用形式
    //加载单个CSS/SCSS文件
    #require("bootstrap/css/bootstrap.css")
    #require("/static/scss/global.scss")

    //脚本的形式使用
    //加载bootstrap前端css框架
    #script()
    //启用 bootstrap
        require(['bootstrap']);
    #end


## BackboneJS

Backbone 为复杂Javascript应用程序提供模型(models)、集合(collections)、视图(views)的结构。
其中模型用于绑定键值数据和自定义事件；集合附有可枚举函数的丰富API； 视图可以声明事件处理函数，并通过RESTful JSON接口连接到应用程序。

当我们开发含有大量Javascript的web应用程序时，首先你需要做的事情之一便是停止向DOM对象附加数据。 通过复杂多变的jQuery选择符和回调函数创建Javascript应用程序，包括在HTML UI，Javascript逻辑和数据之间保持同步，都不复杂。 但对富客户端应用来说，良好的架构通常是有很多益处的。
Backbone将数据呈现为模型, 你可以创建模型、对模型进行验证和销毁，甚至将它保存到服务器。 当UI的变化引起模型属性改变时，模型会触发"change"事件； 所有显示模型数据的视图会接收到该事件的通知，继而视图重新渲染。 你无需查找DOM来搜索指定id的元素去手动更新HTML。 — 当模型改变了，视图便会自动变化。

## 基础习题

```
1.我们可以在下列哪个 HTML 元素中放置 Javascript 代码？
正确答案：<script>
2.写 "Hello World" 的正确 Javascript 语法是？
正确答案：document.write("Hello World")
3.插入 Javacript 的正确位置是？
正确答案：<body> 部分和 <head> 部分均可
4.引用名为 "xxx.js" 的外部脚本的正确语法是？
您的回答：<script src="xxx.js">
5.外部脚本必须包含 <script> 标签吗？
正确答案：否
6.如何在警告框中写入 "Hello World"？
您的回答：alert("Hello World")
7.如何创建函数？
正确答案：function myFunction()
8.如何调用名为 "myFunction" 的函数？
正确答案：myFunction()
9.如何编写当 i 等于 5 时执行一些语句的条件语句？
正确答案：if (i==5)
10.如何编写当 i 不等于 5 时执行一些语句的条件语句？
正确答案：if (i != 5)
11.在 JavaScript 中，有多少种不同类型的循环？
正确答案：两种。for 循环和 while 循环。
12.for 循环如何开始？
正确答案：for (i = 0; i <= 5; i++)
13.如何在 JavaScript 中添加注释？
您的回答：//This is a comment
14.可插入多行注释的 JavaScript 语法是？
您的回答：/*This comment has more than one line*/
15.定义 JavaScript 数组的正确方法是？
正确答案：var txt = new Array("George","John","Thomas")
16.如何把 7.25 四舍五入为最接近的整数？
正确答案：Math.round(7.25)
17.如何求得 2 和 4 中最大的数？
您的回答：Math.max(2,4)
18.打开名为 "window2" 的新窗口的 JavaScript 语法是？
正确答案：window.open("http://www.w3school.com.cn","window2")
19.如何在浏览器的状态栏放入一条消息？
您的回答：window.status = "put your message here"
20.如何获得客户端浏览器的名称？
正确答案：navigator.appName
```


[返回顶端按钮JS代码](http://www.jb51.net/article/35995.htm)

jquery中的$(function(){...})什么时候执行

这个是在页面DOM文档加载完成后加载执行的，等效于$(document).ready(function(){...}); 
优于window.onload，后者必须等到页面内包括图片的所有元素加载完毕后才能执行。

jQuery 文档操作 - appendTo() 方法

jquery中常用的函数和属性详细解析

Dom：
Attribute：属性
$("p").addClass(css中定义的样式类型); 给某个元素添加样式
$("img").attr({src:"test.jpg",title:"test Image"}); 给某个元素添加属性/值，参数是map
$("input").attr({"checked", "checked"}); 
$("img").attr("title", function() { return this.src }); 给某个元素添加属性/值
$("元素名称").html(); 获得该元素内的内容（元素，文本等）
$("元素名称").html("<b>new stuff</b>"); 给某元素设置内容
$("元素名称").removeAttr("属性名称") 给某元素删除指定的属性以及该属性的值
$("元素名称").removeClass("class") 给某元素删除指定的样式
$("元素名称").text(); 获得该元素的文本
$("元素名称").text(value); 设置该元素的文本值为value
$("元素名称").toggleClass(class) 当元素存在参数中的样式的时候取消,如果不存在就设置此样式
$("input元素名称").val(); 获取input元素的值
$("input元素名称").val(value); 设置input元素的值为value
Manipulation：
$("元素名称").after(content); 在匹配元素后面添加内容
$("元素名称").append(content); 将content作为元素的内容插入到该元素的后面
$("元素名称").appendTo(content); 在content后接元素
$("元素名称").before(content); 与after方法相反
$("元素名称").clone(布尔表达式) 当布尔表达式为真时，克隆元素（无参时，当作true处理）
$("元素名称").empty() 将该元素的内容设置为空
$("元素名称").insertAfter(content); 将该元素插入到content之后
$("元素名称").insertBefore(content); 将该元素插入到content之前
$("元素").prepend(content); 将content作为该元素的一部分，放到该元素的最前面
$("元素").prependTo(content); 将该元素作为content的一部分，放content的最前面
$("元素").remove(); 删除所有的指定元素
$("元素").remove("exp"); 删除所有含有exp的元素
$("元素").wrap("html"); 用html来包围该元素
$("元素").wrap(element); 用element来包围该元素


不知道你对javascript是否了解，如果了解可以跟你举一个例子：
新建一个 HTML 文件 1-1.html，加入如下所示的代码。
一个简单的 jQuery 应用
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 
Transitional//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title> 第一个简单的jQuery 程序 </title>
    <script language="javascript" type="text/javascript" 
            src="Jscript/jquery-1.4.2.min.js"></script>
    <script type="text/javascript">
           $(document).ready(function(){
              alert("您好, 欢迎来到jQuery世界");           
           })
    </script>
</head>
<body>
</body>
</html>
在上述文件的代码中，有一段如下的代码 ：
$(document).ready(function(){
               //程序段         
})
该段代码类似于传统的 JavaScript 代码：
window.onload=function(){
               //程序段
}
//--
//window.onload=function(){...}的作用又跟声明函数loading function loading(){...}，并在html的<body onload="loading()">调用一样
//这样写就不用在body的onload事件里面调用，只需在js程序段里面编写即可
//--
虽然上述两段代码在功能上可以互换，但它们之间又有许多区别 ：
  执行时间不同： $(document).ready在页面框架下载完毕后就执行；而window.onload必须
在页面全部加载完毕（包含图片下载）后才能执行。很明显，前者的执行效率高于后者。
  执行数量不同： $(document).ready可以重复写多个，并且每次执行结果不同；而window.
onload尽管可以执行多个，但仅输出最后一个执行结果，无法完成多个结果的输出。
  $(document).ready(function(){}) 可以简写成 $(function(){})，因此与下面的代码是等
价的。
$(document).ready(function(){
              // 程序段           
})
等价于
$(function(){
              // 程序段           
})

$(document).ready(function(){})