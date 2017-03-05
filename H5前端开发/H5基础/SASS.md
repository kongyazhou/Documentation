SASS
==========

Sass技术官网[点击进入](http://sass-lang.com/)

## 简介

```
SASS是一种对css的一种提升，增加了规则嵌套、变量、混合、选择器继承等等。
通过使用命令行的工具或WEB框架插件把它转换成标准的、格式良好的CSS代码。

SASS技术的文件的后缀名有两种形式：.sass和.scss。
这两种的区别在于：
.sass文件对代码的排版有着"非常严格"的要求，而且没有大括号，没有分号。

```

# SCSS代码

    .a {  
        color: blue;  
        font-weight: bold;  
        text-decoration: underline;  
        .b {  
            color:black;  
        }  
    } 

转换成CSS代码

    .a {  
      color: blue;  
      font-weight: bold;  
      text-decoration: underline; }  
      .a .b {  
        color: black; }  

# SASS代码

    .div  
     color: blue  
     .b  
      color: black  
      font-weight: bold  
      text-decoration: none  
      .c  
       color: white

转换成CSS代码

    .div {  
      color: blue; }  
      .div .b {  
        color: black;  
        font-weight: bold;  
        text-decoration: none; }  
        .div .b .c {  
          color: white; } 

```
推荐使用.scss格式，使用起来更加顺手。
```
