CentOS7
======

这里记录了服务器环境安装和配置时遇到的常见问题，为今后自己搭建服务器做准备。

服务器系统将采用CentOS 7。

## 基础知识

查看内核版本，位数，版本号：
cat /proc/version
uname -a
uname -r

列出所有版本信息
lsb_release -a

cat /etc/issue

查看CentOS版本号：
cat /etc/redhat-release

查看系统位数：
getconf LONG_BIT

## 系统环境搭建

### CentOS7安装

### 系统升级
系统升级命令:
升级所有包，改变软件设置和系统设置,系统版本内核都升级

    #yum -y update
升级所有包，不改变软件设置和系统设置，系统版本升级，内核不改变

    #yum -y upgrade


### 安装MariaDB



### 网络配置

### 固定IP

### 翻墙
目前没有找到好的在Linux下翻墙的方法，所以我采用的方法是在Windows下开启VPN，虚拟机设置为NAT网络模式。



## Jello前端调试环境搭建

### 安装node.js

本方法是按照这篇[博文](http://www.linuxidc.com/Linux/2015-02/113554.htm)的步骤安装的。
需要翻墙安装，虚拟机翻墙我用的方法是windows翻墙，虚拟机设置为NAT网络模式即可。

安装步骤简单摘录如下：(以v0.12.0为例，查看[最新版本号](https://nodejs.org/))
下载压缩包(建议翻墙)

    wget http://nodejs.org/dist/v0.12.0/node-v0.12.0.tar.gz
解压并进入目录

    tar xvf node-v0.12.0.tar.gz
    cd node-v0.12.0
准备编译环境

    sudo yum install gcc gcc-c++
设置和编译(会需要一些时间来完成)

    ./configure
    make
安装

    sudo make install
检查是否安装成功

    node --version

安装完后就能用npm安装fis、jello等开发框架了。



### Jello 安装

详细步骤在Github上有，这里摘录一些主要的安装步骤。

    ```
    目前没有找到好的在Linux下翻墙的方法，所以我采用的方法是在Windows下开启VPN(推荐使用UUU VPN，每天一小时免费)，然后将虚拟机的网络设置为NAT模式，这样一来，Linux下也能愉快的翻墙啦！
    ```
安装JDK
按照百度经验步骤安装[JDK](http://jingyan.baidu.com/article/c74d60007b85510f6a595dfa.html)。

安装jello & lights

    npm install lights -g
    npm install jello -g
检查是否安装成功(成功会看到一个大大的FIS LOGO)

    jello -v
安装插件

    npm install -g fis-parser-marked
    npm install -g fis-parser-utc
    npm install -g fis-parser-sass

### 关闭防火墙

    systemctl start firewalld.service#启动firewall
    systemctl stop firewalld.service#停止firewall
    systemctl disable firewalld.service#禁止firewall开机启动

## tomcat和Nginx

服务器部署方面的内容，将由下面三个问题中展开学习。
问题一：
nginx 是否可以把 js css html 图片等静态的都存上去？
tomcat 是否只需要动态程序，还是js css也要放tomcat呢？而只有图片和HTML放nginx？

问题二：
前提：只有一台硬件服务器
是否可以让外界只通过nginx访问进入网站，nginx把动态请求分发给tomcat处理。

问题三：
前提：只有一台硬件服务器
nginx 后面是否可以配置多个tomcat同时提供服务？
如果可以配置多个TOMCAT同时提供服务，那比只采用一个tomcat提供服务有什么优势？？

回答一：
nginx作为专业的反向代理程序，对静态资源的处理性能是非常之高的。像js/css/html之类用nginx代理比tomcat代理性能会好很多倍。tomcat只处理动态请求。

回答二：
完全可以。nginx可以通过配置把特定目录或扩展名的请求，转发到后台服务器上，如tomcat/php等。配置也非常简单，百度一下，看个例子就入门了。

回答三：
配置多个tomcat服务器，则可从容的停掉其中一台服务器升级，而不影响前端用户的使用。还有比这更美妙的事么。

尝试[部署tomcat+Nginx](http://www.360doc.com/content/12/0615/23/15643_218433480.shtml)负载均衡服务器。

### nginx
按照网上博客的步骤在CentOS7中[编译安装nginx](http://www.centoscn.com/image-text/install/2014/0812/3480.html)，如果速度慢请翻墙，我使用的版本是nginx-1.9.2。
或者按照百度经验的步骤[yum安装nginx](http://jingyan.baidu.com/article/aa6a2c14dc36640d4d19c47e.html)。(未验证)
设置nginx开机自启动:
如果你采用编译安装的方式，直接在/etc/rc.local 增加如下代码即可：
/usr/local/nginx/sbin/nginx 
前提是你的nginx是安装到/usr/local/nginx下。

另外，如果使用yum 安装的话，默认是作为服务器，开机自动启动的。可以用chkconfig 查看。

### tomcat
下载[安装tomcat](http://blog.csdn.net/czmchen/article/details/41047455)。

项目路径配置：
在Tomcat默认安装后，tomcat的主目录是webapps/root目录，所以如果想改变tomcat的主目录的话可以如下所做：

第一种：（假设tomcat安装在C盘下，项目名为bidding）打开C:/Tomcat/conf/server.xml，在<host></host>之间加入代码：<Context docBase="C:/Program Files/Apache Software Foundation/Tomcat 5.5/webapps/bidding" path="" debug="0"  reloadable="true"/>这样重新启动tomcat，我们的主目录就被设置为bidding这个项目了。

第二种：将tomcat安装目录下的ROOT下的所有文件全部删除，然后将工程的解压后的文件全部拷进去。

第三种：Tomcat5.0以下版本在C:/Tomcat/conf/Catalina/localhost目录下会自动生成了一个ROOT.Xml，但是5.0以上版本不再生成此文件，所以可以新建个ROOT.xml,在里面加入如下代码：
    <?Xml version='1.0' encoding='utf-8'?><Context crossContext="true" docBase=""C:/Program Files/Apache Software Foundation/Tomcat 5.5/webapps/bidding"" path="" reloadable="true"></Context>

[Tomcat中更改网站根目录和默认页的配置方法](http://www.jb51.net/article/49814.htm)

推荐几篇文章

[JavaWeb学习总结(一)——JavaWeb开发入门](http://www.cnblogs.com/xdp-gacl/p/3729033.html)

[JavaWeb学习总结(二)——Tomcat服务器学习和使用(一)](http://www.cnblogs.com/xdp-gacl/p/3734395.html)

[JavaWeb学习总结(三)——Tomcat服务器学习和使用(二)](http://www.cnblogs.com/xdp-gacl/p/3744053.html)

[javaweb学习总结(四)——Http协议](http://www.cnblogs.com/xdp-gacl/p/3751277.html)

[javaweb学习总结(五)——Servlet开发(一)](http://www.cnblogs.com/xdp-gacl/p/3760336.html)

[javaweb学习总结(六)——Servlet开发(二)](http://www.cnblogs.com/xdp-gacl/p/3763559.html)

[javaweb学习总结(七)——HttpServletResponse对象(一)](http://www.cnblogs.com/xdp-gacl/p/3789624.html)

[javaweb学习总结(八)——HttpServletResponse对象(二)](http://www.cnblogs.com/xdp-gacl/p/3791993.html)

[javaweb学习总结(九)—— 通过Servlet生成验证码图片](http://www.cnblogs.com/xdp-gacl/p/3798190.html)

[javaweb学习总结(十)——HttpServletRequest对象(一)](http://www.cnblogs.com/xdp-gacl/p/3798347.html)

[云计算的基本概念](http://www.cnblogs.com/xdp-gacl/p/3836771.html)

好吧 总共得有五十多篇

这篇是[Linux下的JavaWeb部署](http://www.cnblogs.com/xdp-gacl/p/4097608.html)

[Nginx+tomcat](http://cssor.com/nginx-location-configuration.html)

ajp egret creatJS

MyEclipse必不可少

[无盘工作站](http://baike.baidu.com/link?url=8p6eKt07ZsXnfhf3DzzltT3TIplYybTXOte4gbwk6Sydj4JPN0Ws6EX3VJBcz2oDvpnBCDNVVmRStUzeaxiSVq)



