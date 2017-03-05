Jello
======

前端开发工具。

为前端开发人员搭建能够快速调试、预览的环境。
使前后端开发工作分离，前端人员能够独立于后台程序做开发调试。

## 常用命令

    jello server start
    jello release
    jello server stop
打开生成的网页文件目录

    jello server open


Jello前端开发使用Velocity模版框架，使前端开发模块化，提高了代码复用率，使开发过程更清晰，效率更高。

## Velocity

Velocity官网[点击进入](http://velocity.apache.org/)

### 简介
  ```
  Velocity是一个基于java的模板引擎（template engine）。
  它允许任何人仅仅使用简单的模板语言（template language）来引用由java代码定义的对象。
  ```

  ```
  当Velocity应用于web开发时，界面设计人员可以和java程序开发人员同步开发一个遵循MVC架构的web站点。
  也就是说，页面设计人员可以只关注页面的显示效果，而由java程序开发人员关注业务逻辑编码。
  Velocity将java代码从web页面中分离出来，这样为web站点的长期维护提供了便利，同时也为我们在JSP和PHP之外又提供了一种可选的方案。
  ```

  ```
  Velocity的能力远不止web站点开发这个领域，例如，它可以从模板（template）产生SQL和PostScript、XML，它也可以被当作一个独立工具来产生源代码和报告，或者作为其他系统的集成组件使用。
  Velocity也可以为Turbine web开发架构提供模板服务（template service）。
  Velocity+Turbine提供一个模板服务的方式允许一个web应用以一个真正的MVC模型进行开发。
  ```

### 应用情况
本项目使用Velocity模板框架，进行模板式开发，以.vm为后缀的文件即为Velocity模板文件。
模板继承其他模板，引用部件(widget)，并复写其中的块("block")以填充或修改内容。
通过模板的层层继承和内容扩充，实现最终的设计。

### 使用方法
  ```
  这里只展示本项目使用到的代码。
  ```
继承：
    #extends("./frame.vm")
定义和复写"块"(block)：
    #block("body")#end
引入"部件"(widget)：
    #widget("/widget/footer/footer.vm")
单行注释：
    ##这是一行注释。
多行注释：
    #*
    一些注释。
    别的注释。
    *#


