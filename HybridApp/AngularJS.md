# AngularJS

Google

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

.directive("指令名，标签名",function(){
	return{

}

}

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