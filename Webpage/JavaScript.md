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
