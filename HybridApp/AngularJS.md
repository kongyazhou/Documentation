# AngularJS

```
看来phonegap开发UI还是得用ionic
而ionic所用的AngularJS是Google推出的优秀框架
值得好好学习~

开发的过程中为了赶进度没有系统的学习
等项目结束了把资料整理一下
慕客网上的教程认真看一遍
深入掌握AngularJS的原理
```

## MVC

Controller() 控制器:
ng-controller

View 视图:

Model 数据模型:

#### 困难



## 模块化

var myModule = angular.module("",

## 

<html ng-app="">相当于main()

ng-model定义变量

<intput ng-model="a">

{{a}}调用变量a的值

## 指令系统

```javascript
.directive("指令名，标签名",function(){
	return{
	
	}
}
```

return的内容替换指令标签。

## 双向数据绑定

数据发生变化，视图立即跟着变化

## 开发环境

代码编辑器
断点调试工具
版本管理工具
代码合并和混淆工具
依赖管理工具
单元测试工具
集成测试工具

nodejs
sublime
webstorm显示浏览兼容性
chrome batarang断电调试 针对AngularJS
git 

代码合并和混淆工具 grunt
uglify混淆
concat合并
watch监控

bower依赖管理
自动安装依赖的组建
依赖检测
版本兼容检测

http-server轻量级server
输入http-server可把任何目录建立网站
npm安装即可

karma单元测试

Jasmine写测试用例
describe
it
expect
to

protractor专门angularjs测试工具

## 阅读资料

[AngularJS 之 Factory vs Service vs Provider](http://www.oschina.net/translate/angularjs-factory-vs-service-vs-provider)

[上文的英文版](http://blog.csdn.net/lglgsy456/article/details/36902179)


[angularJS的controller之间如何正确的通信](http://www.tuicool.com/articles/InuMF3J)

[angular.js 下如何动态插入删除dom节点](http://yijiebuyi.com/blog/7702aba213aec9de43b129b3d2f3b30c.html)

[AngularJS开发人员最常犯的10个错误](http://blog.jobbole.com/78946/)

[AngularJS WebSocket Service](http://www.51joben.com/archives/7302.html)