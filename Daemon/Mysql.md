Mysql
======
查看安装的mariadb包
rpm -qa|grep mariadb

yum remove mariadb mariadb-server
yum install mariadb mariadb-server

/var/lib/mysql

设置root密码(为1)
mysqladmin -u root -p password 1

首先配置允许访问的用户，采用授权的方式给用户权限

    GRANT ALL PRIVILEGES ON *.* TO 'root'@'%'IDENTIFIED BY '123456' WITH GRANT OPTION;
 说明：root是登陆数据库的用户，123456是登陆数据库的密码，*就是意味着任何来源任何主机反正就是权限很大的样子。
最后配置好权限之后不应该忘记刷新使之生效

    flush privileges;
 再次访问就可以了吧。

本项目数据库将使用Mysql。
在CentOS7中 Mysql升级为MariaDB。

可以参考网上的[资料](http://www.cnblogs.com/zhangzhu/archive/2013/07/04/3172486.html)，很全很详细。
centOS7中用mariadb代替了mysql，启动、重启服务命令如下：

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
