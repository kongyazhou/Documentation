Java
==========
捉到博客教程[一篇](http://blog.csdn.net/eastmount/article/details/45653615)，挺详细的，建议仔细看完。

推荐传智播客方立勋的JavaWeb视频教程

SummerTheatre使用Java语言开发网站后台程序，采用[J2EE技术架构](http://baike.baidu.com/link?url=y98HRwaUO-E-9V3_ch20Q82RE9poBwOc70l96Tvjb8L9WbDCN2XPRE3ASXWGiX3gFaypGuwo4wr266R-vA_fuK#3)(Java 2 platform Enterprise Edition)。

目录：
*[MVC](#MVC)
*[JSP](#JSP)
*[Servlet](#Servlet)
*[JavaBean](#JavaBean)
*[JDBC](#JDBC)
*[Myeclipse](#Myeclipse)

## MVC模型
在正式开始学习Java网站开发之前，我们应当先了解一下MVC模型这个概念。
在Java开发中有一个设计模式，叫做MVC，意思是Model(模型)-View(视图)-Controller(控制器)。
模型就是javaBean，用来封装和书写逻辑；
视图就是jsp，用来显示界面；
控制器是servlet用来控制接收和跳转。

后面的章节我将分别介绍各个内容。

[spring MVC](http://baike.baidu.com/link?url=So5VrESD-LFEK5wmZdSJ5mN6csTQxj3IiScS42eoNBGETgSe3WLQ_Sk8X3NKECLxIF_e1SlFgjWSJ5nrYi58W_)

对于初学者或者想了解mvc的人来说我觉得 spring是最好的，它的实现就是教科书！第二它和tapestry一样是一个纯正的servlet系统，这也是它和tapestry相比 struts所没有的优势。而且框架本身有代码，看起来容易理解。
## JSP
JSP就是Java Server page。
他是动态网页技术标准。

### 简介

  ```
  JSP全名为Java Server Pages，中文名叫java服务器页面，其根本是一个简化的Servlet设计，它[1] 是由Sun Microsystems公司倡导、许多公司参与一起建立的一种动态网页技术标准。
  JSP技术有点类似ASP技术，它是在传统的网页HTML（标准通用标记语言的子集）文件(*.htm,*.html)中插入Java程序段(Scriptlet)和JSP标记(tag)，从而形成JSP文件，后缀名为(*.jsp)。
  用JSP开发的Web应用是跨平台的，既能在Linux下运行，也能在其他操作系统上运行。
  ```

### 基础
[PHP](http://www.w3school.com.cn/php/index.asp)
　　PHP（Hypertext
Preprocessor）是一种嵌入HTML页面中的脚本语言。它大量地借用C和Perl语言的语法， 并结合PHP自己的特性，使Web开发者能够快速地写出动态产生页面。

　　PHP是完全免费的开源产品，不用花钱，Apache和MYSQL也是用样免费开源，在国外非常流行，PHP和MYSQL搭配使用，可以非常快速的搭建一套不错的动态网站系统，因此国外大多数主机系统都配有免费的APACHE＋PHP＋MYSQL。通常认为这种搭配的执行效率比IIS＋ASP＋ACCESS要高，而后者的使用还必须另外交钱给微软。

　　PHP的语法和Perl很相似，但是PHP所包含的函数却远远多于Perl，PHP没有命名空间，编程时候必须努力避免模块的名称冲突。一个开源的语言虽然需要简单的语法和丰富的函数，但PHP内部结构的天生缺陷导致了PHP不适合于编写比中小型业余网站更大的网站。
JSP（JavaServer
Pages）是Sun公司推出的一种动态网页技术。JSP技术是以Java语言作为脚本语言的，熟悉JAVA语言的人可以很快上手。
　　JSP本身虽然也是脚本语言，但是却和PHP、ASP有着本质的区别。PHP和ASP都是由语言引擎解释执行程序代码，而JSP代码却被编译成Servlet并由Java虚拟机执行，这种编译操作仅在对JSP页面的第一次请求时发生。因此普遍认为JSP的执行效率比PHP和ASP都高。

　　JSP是一种服务器端的脚本语言，最大的好处就是开发效率较高，JSP可
以使用JavaBeans或者EJB（Enterprise
JavaBeans）来执行应用程序所要求的更为复杂的处理，但是这种网站架构因为其业务规则代码与页面代码混为一团，不利于维护，因此并不适应大型应用
的要求，取而代之的是基于MVC的Web架构。MVC的核心思想是将应用分为模型、视图和控制器三部分。模型是指应用程序的数据，以及对这些数据的操作；
视图是指用户界面；控制器负责用户界面和程序数据之间的同步。通过MVC的Web架构，可以弱化各个部分的耦合关系，并将业务逻辑处理与页面以及数据分离
开来，这样当其中一个模块的代码发生改变时，并不影响其他模块的正常运行，所以基于MVC的Web架构更适应于大型应用开发的潮流。

　　因此，不少国外的大型企业系统和商务系统都使用以上的MVC架构，能够支持高度复杂的基于Web的大型应用。

　　结论：JSP对于网站开发来讲不像PHP那样易学易用，支持JAVA的主机也少于支持PHP的主机，这从一定程度上限制了Java技术在网站上的发展，不过在企业软件应用上来讲，MVC还是拥有相当大的优势的，虽然其配置和部署相对其他脚本语言来说要复杂一些，但对于跨平台的中大型企业应用系统来讲，基于JAVA技术的MVC架构几乎成为唯一的选择。

JSP操作数据库

## JavaBean
JavaBeand的基础知识可以通过阅读[百度百科](http://baike.baidu.com/link?url=Etjjv45zFmgH4zZhW4KJny2-6_v_at7-Nq75w_g7B5wbvt2Wh3ZZP1-Fi5SK4_w96_hYhKcbr20KZ7xcGSUnvK)获得
。

JavaBean 是一种JAVA语言写成的可重用组件。
为写成JavaBean，类必须是具体的和公共的，并且具有无参数的构造器。JavaBean 通过提供符合一致性设计模式的公共方法将内部域暴露成员属性。众所周知，属性名称符合这种模式，其他Java 类可以通过[自省机制](http://blog.csdn.net/wsllq334/article/details/7006353)发现和操作这些JavaBean 的属性。

JavaBean可分为两种：一种是有用户界面（UI，User Interface）的JavaBean；还有一种是没有用户界面，主要负责处理事务（如数据运算，操纵数据库）的JavaBean。JSP通常访问的是后一种JavaBean。

## Servlet

一篇关于Servlet的[博文](http://blog.csdn.net/eastmount/article/details/45536369)。
Servlet是运行在Web容器的类，能处理Web客户的HTTP请求，并产生HTTP响应。

服务器上需要一些程序，常常是根据用户输入访问数据库的程序。这些通常是使用公共网关接口（Common Gateway Interface，CGI）应用程序完成的。然而，在服务器上运行 Java，这种程序可使用 Java 编程语言实现。在通信量大的服务器上，JavaServlet 的优点在于它们的执行速度更快于 CGI 程序。各个用户请求被激活成单个程序中的一个线程，而无需创建单独的进程，这意味着服务器端处理请求的系统开销将明显降低。

实现过程
最早支持 Servlet 技术的是 JavaSoft 的 Java Web Server。此后，一些其它的基于 Java 的 Web Server 开始支持标准的 Servlet API。Servlet 的主要功能在于交互式地浏览和修改数据，生成动态Web内容。这个过程为：
1) 客户端发送请求至服务器端；
2) 服务器将请求信息发送至 Servlet；
3) Servlet 生成响应内容并将其传给服务器。响应内容动态生成，通常取决于客户端的请求；
4) 服务器将响应返回给客户端。
Servlet 看起来像是通常的 Java 程序。Servlet 导入特定的属于 Java Servlet API 的包。因为是对象字节码，可动态地从网络加载，可以说 Servlet 对 Server 就如同 Applet对 Client 一样，但是，由于 Servlet 运行于 Server 中，它们并不需要一个图形用户界面。从这个角度讲，Servlet 也被称为 FacelessObject。
一个 Servlet 就是 Java 编程语言中的一个类，它被用来扩展服务器的性能，服务器上驻留着可以通过“请求-响应”编程模型来访问的应用程序。虽然 Servlet 可以对任何类型的请求产生响应，但通常只用来扩展 Web 服务器的应用程序。


生命周期
客户端请求该 Servlet；
加载 Servlet 类到内存；
实例化并调用init()方法初始化该 Servlet；
service()（根据请求方法不同调用doGet() 或者 doPost()，此外还有doGet()、doPut()、doTrace()、doDelete()、doOptions()）；
destroy()。

Servlet输出
response.getWriter().print("Servlet doPost!");
把网页的源码一句一句打出去




写了这么多，到底什么是serverlet和javabean?

## Myeclipse

后台开发需要使用Myeclipse软件。
我是用的是Myeclipse2015稳定版2.0，安装包已上传至百度云，点这里[下载cracker](http://download.csdn.net/detail/tmraz/8854727)。

    ```
    Myeclipse2015和老版本有许多不同，所以网上的很多教程和资料并不适用。
    ```

Myeclipse默认的字体显示中文时会很小，修改字体的设置方法如下：
windows->Preferences->General->Appearance->Colors and Fonts->Basic->Text Font
推荐设置
字体：微软雅黑 字形：常规 大小：小五


新建项目的时候Myeclipse 没有点上创建web.xml选项，记得要点上。

Myeclipse 2015 新建servlet时不需要更新web.xml。




jsp向servlet传递参数
jsp中使用request.setAttribute(name, object)保存，
servlet中使用request.getAttribute(name)取

获取表单数据
request.getParameter("");

[servlet怎么设置jsp变量](http://zhidao.baidu.com/link?url=XPk_7owrSl3X_dY4Opi_1S7uHTwR8ch3IIlFGXxunaKJHqQ8Ncnktzpq8zIF_A7V8M6YUSIQU9tu301Wf3h-g_)
如果数据量大的话可以通过bean来实现
如果小的话可以request、session、page、application来传递
具体可以借鉴上面几位仁兄的建议



