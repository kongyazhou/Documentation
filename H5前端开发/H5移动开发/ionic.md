# ionic

```
本文介绍ionic1相关的资料。
```

ionic是一个用来开发混合手机应用的，开源的，免费的**代码库**。可以优化html、css和js的性能，构建高效的应用程序，而且还可以用于构建Sass和AngularJS的优化。ionic是一个值得信赖的框架。


## ionic相关资料

- [ionic百度词条](http://baike.baidu.com/link?url=Ss8i3DrvH0y_pcOGJi-ujIeOQiDDwbhkWcfA_viM_CeR0rKWjGPjXPQHfPUMBm7hwR6lh_BpYClREajXma1hTq)
- [《ionic开发实战》](http://blog.csdn.net/i348018533/article/details/47258449)
- [ionic官网](http://ionicframework.com/)
- [ionic creator](http://ionic.io/products/creator)
- [ionic wechat](http://www.cnblogs.com/Frogmarch/) ，某大的学习和开发记录，看完你就会ionic了

## ionic开发环境搭建

首先您需要安装Node.js，我们在接下来的安装中需要使用到其 NPM 工具，更多 NPM 介绍可以查看我们的NPM 使用介绍。

然后通过命令行工具安装最新版本的 cordova 和 ionic 。通过参考Android和iOS官方文档来安装。

Window 和 Linux 上打开命令行工具执行以下命令：

```bash
$ npm install -g cordova
$ npm install -g ionic
```

#### Sublime text

推荐使用Sublime text作为编辑工具。

推荐安装使用以下Sublime text插件：
- SublimeLinter
	- jslint
	- csslint
- DocBlock
- Ionic Framework Snippets
- AngularJS
- HTML-CSS-JS prettify
- AutoFilename
- All Autocomplete

#### npm

推荐使用命令行npm作为调试、打包、构建工具。

推荐安装使用以下npm插件：

- jslint
- csslint
- ionic
- gulp
	- gulp-concat
	- gulp-htmlmin
	- gulp-uglify
	- gulp-ng-annotate
- bower

## ionic基本操作

#### 创建一个项目

```bash
$ ionic start myApp tabs
```

#### 在模拟器中运行它

```bash
$ cd myApp
$ ionic platform add ios
$ ionic build ios
$ ionic emulate ios
```

#### 在浏览器中实时预览

```bash
ionic serve
```

简单快捷，实时更新，谁用谁知道~

## ionic creator

在线编辑HTML的UI页面。

拖拽控件，轻松设计UI。

神器！可惜app版要付费账户才能用，网页版的免费账户只能建一个项目。

[ionic creator](http://ionic.io/products/creator)

## ionic View app

在命令行输入 "ionic upload" 便可将项目发送到ionic view app中，以供预览。

## ionic事件

点击滑动等事件。

[ionic事件](https://www.zoomla.cn/Item/2843.aspx)

## 相关组件

[ionic可折叠列表](http://codepen.io/shengoo/pen/bNbvdO/)，源码网站

[ionic可折叠列表](http://www.sheng00.com/1502.html)，介绍该组件的网站

[ionic icons](http://ionicons.com/)
