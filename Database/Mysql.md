# Mysql

## 安装MariaDB/Mysql

查看已安装的mariadb包
```bash
rpm -qa|grep mariadb
```

删除已安装的mariadb
```
yum remove mariadb mariadb-server
```

从网络安装mariadb
```
yum install mariadb mariadb-server
```

/var/lib/mysql

设置root密码(为1)
```bash
mysqladmin -u root -p password 1
```

首先配置允许访问的用户，采用授权的方式给用户权限

```bash
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%'IDENTIFIED BY '123456' WITH GRANT OPTION;
```

说明：root是登陆数据库的用户，123456是登陆数据库的密码，*就是意味着任何来源任何主机反正就是权限很大的样子。
	
最后配置好权限之后不应该忘记刷新使之生效

```bash
flush privileges;
```

再次访问就可以了。
	
本项目数据库将使用Mysql。
在CentOS7中使用了MariaDB替代了之前一直使用的Mysql。

可以参考网上的[资料](http://www.cnblogs.com/zhangzhu/archive/2013/07/04/3172486.html)，很全很详细。
centOS7中用mariadb代替了mysql，启动、重启服务命令如下：

```
systemctl start mariadb
systemctl restart mariadb
systemctl enable mariadb开机启动
```

    查看Mysql版本
    mysql -V

    连接Mysql
    mysql -u root -p

    连接远程Mysql
    mysql -h 127.0.0.1 -u root -p 123

    退出
    \q

    创建数据库
    create database abc;

    显示所有库
    show databases;

    删除数据库
    drop database abc;

    连接数据库
    use abc;

    当前选择的数据库
    select database();

    显示当前时间
    select now();

    显示日月年
    SELECT DAYOFMONTH(CURRENT_DATE);
    SELECT MONTH(CURRENT_DATE); 
    SELECT YEAR(CURRENT_DATE);

    查看所有表
    show tables;

    创建表
    create table <表名> ( <字段名1> <类型1> [,..<字段名n> <类型n>]);

    删除表
    drop table MyClass;

    向表中插入数据
    insert into <表名> [( <字段名1>[,..<字段名n > ])] values ( 值1 )[, ( 值n )]

    查询表中数据
    select * from < 表名 >
    select <字段1，字段2，...> from < 表名 > where < 表达式 >

    删除表中数据
    delete from 表名 where 表达式

    修改表中数据
    update MyClass set name='Mary' where id=1;

    加索引
    alter table 表名 add index 索引名 (字段名1[，字段名2 …]);
    例子： mysql> alter table employee add index emp_name (name);

    加主关键字的索引
    alter table 表名 add primary key (字段名);
    例子： mysql> alter table employee add primary key(id);

    加唯一限制条件的索引
    alter table 表名 add unique 索引名 (字段名);
    例子： mysql> alter table employee add unique emp_name2(cardnumber);

    删除某个索引
    alter table 表名 drop index 索引名;
    例子： mysql>alter table employee drop index emp_name;
        增加字段
        alter table MyClass add passtest int(4) default '0'

    增加字段：
    ALTER TABLE table_name ADD field_name field_type;

    修改原字段名称及类型：
    ALTER TABLE table_name CHANGE old_field_name new_field_name field_type;

    删除字段：
    ALTER TABLE table_name DROP field_name;

    修改表名
    rename table MyClass to YourClass;
    ```


Tomcat[数据库连接池](http://baike.baidu.com/link?url=qGzAlxhyEKKfvibRdC1YnmEwxDJh_Mt_lYe6Ojz48sZFPGO1GrNaLcJQGu8L3iow4224H3-zssIyz4qK8LUKX_)概念介绍。
数据库连接池[使用说明](http://jingyan.baidu.com/article/a24b33cd6be2a019ff002b10.html)。
[JDBC](http://baike.baidu.com/link?url=7ayq9q-4L9mntaJNE_VgE96cZ3Usc5LlCcOeByiWW2vOnJtYmrMB0K_75XGwssMDF9TQ33JdgTR5Bv0jsE5z9_)

JSTL和EL表达式需要：
standard.jar和jstl.jar的[下载地址](http://blog.sina.com.cn/s/blog_904d1154010108jj.html)

mysql 用户管理和[权限管理](http://www.cnblogs.com/fslnet/p/3143344.html)


## Mysql图形化管理工具
mysql navicat
优点是支持中文
[官方网站](http://www.navicat.com.cn/)
[注册机下载](http://download.csdn.net/detail/ydq0828/7378133)

char和varchar
char效率高 占存储大
varchar效率低 占存储小(占用空间随内容变化)
[MYSQL中CHAR,VARCHAR,BLOB和TEXT的比较](http://blog.csdn.net/forever0wind/article/details/7473576)

没有boolean
用tinyint代替

[mysql 中 character set 与 collation 的点滴理解](http://zhongwei-leg.iteye.com/blog/899227)

[Mysql中用中文查询的方法](http://www.ibm.com/developerworks/cn/java/j-lo-chinesecoding/)

要使用中文查询数据库，建立连接时应如下写：

    Connection conn = DriverManager.getConnection("jdbc:mysql://192.168.182.128:3306/Summer?useUnicode=true&characterEncoding=UTF-8","root","1");


这个查询要求是：用模糊查询查地址是，广州，上海，成都的学员
select * from stuInfno where stuaddress like '北京%','上海%','成都%'
这样不对啊，到底该怎么写啊，指教下

select * from stuInfno 
where substring(stuaddress,1,2) in ('北京','上海','成都')

[Tomcat线程池设置](http://my.oschina.net/u/1266624/blog/163539)
额 这个好像不是数据库连接池..

连接池的使用将放到后期的性能优化上去。
第一版将不使用。

[PrepareStatement作用](http://zhidao.baidu.com/link?url=nRWmzf3zckaZROf3U46F8kgBsEg9JnnJkvJngEaZ-3MKQ-BeBc7bMYR5AzCzC_BtD8eq97biEnMkSUYCAa-Iha)

[从关系型数据库到非关系型数据库](http://blog.csdn.net/robinjwong/article/details/18502195)

数据库事务必须具备ACID特性，ACID是Atomic原子性，Consistency一致性，Isolation隔离性，Durability持久性。

在读方面，传统上为了克服关系型数据库缺陷，提高性能，都是增加一级 [**memcache**](http://baike.baidu.com/link?url=DF2GBJjkYN4IK436o4ZEl5R8YJ4mPqtmpUcsZHAVtroIc-wdSecYUgXtYpvbfvNcvUHMJVxS5XdcOqCnqvNt6_)来静态化网页，而在SNS中，变化太快，**memchache**已经无能为力了。


## [用户权限管理](http://www.cnblogs.com/4php/p/4113593.html)
2.1 创建普通用户

2.1.1 CREATE USER

CREATE USER ‘用户名称’ [@’主机名称’]

例：CREATE USER 'user1';

验证是否创建成功：

mysql> SELECT user FROM mysql.user;

4. 修改用户密码：

 

UPDATE mysql.user SET password=PASSWORD('新密码') WHERE user='用户名

[AND host=’主机名称’]';

UPDATE mysql.user SET password=PASSWORD('111111') WHERE user='root';