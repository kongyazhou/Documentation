# TypeScript

TypeScript，简称TS，是一种由微软开发的自由和开源的编程语言。

它是JS的一个超集，目前最新版本为v2.2.1。

它的[源码](https://github.com/Microsoft/TypeScript)可以在Github上找到。

本文档将介绍TS的一些特性，并列举它的基本使用方法。

## 特性

本节介绍了TS的一些特性，并简单介绍特性的使用方法。

#### 类型注解

TypeScript中的类型注解是约束函数返回值类型或变量类型的一种简便方法。

使用方法：

```
变量 : 类型
```

有以下几种可用类型：

- string
- boolean
- number
- Array<元素类型>
详见[TypeScript-基础类型学习](http://blog.csdn.net/u010130282/article/details/52626633)

在下面的示例中，我们想要在调用greeter函数时传入一个字符串类型参数，并返回一个字符串。

我们尝试在调用greeter函数时传入数组：

```ts
function greeter(person: string): string {
    return "Hello, " + person;
}

var user = [0, 1, 2];

document.body.innerHTML = greeter(user);
```

编译时我们将看到一个错误：

```
greeter.ts(7,26): Supplied parameters do not match any signature of call target
```

同样，尝试在调用greeter函数时不传入任何参数，编译时TypeScript将会告诉你调用这个函数时需要带一个参数。

在这两个例子中，TypeScript基于你的代码结构和类型注解，提供静态分析。

**注意**，虽然有错误，但是仍然编译创建了greeter.js文件。即使你的代码中有错误，你仍旧可以使用TypeScript。但是在这种情况，TypeScript会发出警告：你的代码可能不能按照你预想的那样运行。

#### 接口



#### 箭头函数表达式（lambda函数）

lambda表达式 **()=>{something}** 或 **()=>something** 相当于js中的函数。

它的好处是可以**自动将函数中的this附加到上下文中**。

运行并比较下面两段代码的结果，体会lambda表达式的意义：

```TypeScript
var shape = {
    name: "rectangle",
    popup: function() {
 
        console.log('This inside popup(): ' + this.name);
 
        setTimeout(function() {
            console.log('This inside setTimeout(): ' + this.name);
            console.log("I'm a " + this.name + "!");
        }, 3000);
    }
};

shape.popup();
```


```
var shape = {
    name: "rectangle",
    popup: function() {
 
        console.log('This inside popup(): ' + this.name);
 
        setTimeout( () => {
            console.log('This inside setTimeout(): ' + this.name);
            console.log("I'm a " + this.name + "!");
        }, 3000);
    }
};
 
shape.popup();
```

#### 类

TypeScript支持集成了可选的类型批注支持的ECMAScript 6的类。

这一系列的的支持，使得TS全面支持了面向对象编程方法。

包括以下特性：

**类的成员变量可以被声明为public或者private**

用public修饰的成员可以在任何地方访问，private成员只允许在类中访问。

**继承**

我们可以继承一个已存在的类并创建一个派生类，继承使用关键字 extends。

```
class Shape3D extends Shape {
    ...
}
```

关于类的详细说明，见[TypeScript 入门教程](http://www.runoob.com/w3cnote/getting-started-with-typescript.html)。

## 开发环境搭建

本节简单介绍SublimeText3开发TS所需的相关插件和相关配置，并罗列了一些其他常见的开发环境。

**SublimeText3环境配置：**

- 安装Package Control
- 安装插件TypeScript

**单文件编译：**

- 完成编写.ts文件后，在SublimeText中按下 *Ctrl + B* ，即可将.ts文件编译成.js文件，文件名不变。

**批量编译：**

使用gulp工具，来工程化开发、调试、编译TS程序。

- 安装gulp开发工具，调整开发目录结构
- 安装 *gulp-typescript* 插件
- 编写 *gulpfiles.js* 文件
- 参考[[使用gulp脚本配合TypeScript开发](http://www.cnblogs.com/larlf/p/5825364.html)]

## 参考资料

- [TypeScript中文网](https://www.tslang.cn/)
- [TypeScript 入门教程](http://www.runoob.com/w3cnote/getting-started-with-typescript.html)
- [TypeScript——百度百科](http://baike.baidu.com/link?url=w7P-QoiS-hj_r2jTiZCJZ5mcqQ5SH_IQGWeefx5Ay9KVTdKRz8CEncRpCPnhA_tCCav6SmJZ-rP_DPi7rFPDEGTX4nu62gQvcUFbB9w6ibq)
- [使用gulp脚本配合TypeScript开发](http://www.cnblogs.com/larlf/p/5825364.html)
- [TypeScript-基础类型学习](http://blog.csdn.net/u010130282/article/details/52626633)

