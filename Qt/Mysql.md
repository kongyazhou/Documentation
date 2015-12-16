---
title: Mysql

---

```
本文主要介绍Qt5中用QMYSQL连接Mysql数据库的方法。
Qt5中默认包含QMYSQL驱动，但要想使用，还需要添加一些文件。
Qt4默认不支持Mysql，用起来实在麻烦，就不做讨论了。
```

## 准备工作

要使用Qt中的数据库模块，必须先在项目目录中的project.pro文件中，加入下面这行代码:

```
	QT += sql
```

## 程序代码

下面的代码实现了"创建一个Mysql连接，并将连接结果打印到标题上"的功能。

    QSqlDatabase db = QSqlDatabase::addDatabase("QMYSQL3");
    db.setHostName("127.0.0.1");
    db.setPort(3306);
    db.setDatabaseName("test");
    db.setUserName("root");
    db.setPassword("root");
    if(db.open())
    {
        QTextCodec *codec = QTextCodec::codecForName("GB18030");
        setWindowTitle(codec->toUnicode("Mysql连接成功"));
    }
    else
    {
        QTextCodec *codec = QTextCodec::codecForName("GB18030");
        setWindowTitle(codec->toUnicode("Mysql连接失败"));
    }


## 添加驱动

如果完成上面的操作后直接构建并运行程序，则会报错:

```
QSqlDatabase: QMYSQL driver not loaded 
QSqlDatabase: available drivers: QSQLITE QMYSQL QMYSQL3 QPSQL QPSQL7
```

这是因为，Qt5本身还缺少一些连接Mysql所必需的文件。

去Mysql官网下载**32位**的[Mysql Connector/C](http://dev.mysql.com/downloads/connector/c/)

```
必须是32位的，64位的不行。
必须是C语言的，C++的不行。
```

安装完成后，将Mysql Connector安装目录下的lib\libmysql.dll文件复制到Qt安装目录的Qt5.5.1\5.5\mingw492_32\bin文件夹下。

```
以我的系统安装路径为例：
将
C:\Program Files (x86)\MySQL\MySQL Connector C 6.1\lib\libmysql.dll
复制到
C:\Qt\Qt5.5.1\5.5\mingw492_32\bin\libmysql.dll
```

复制完后重启Qt即可。

再次构建并运行之前的程序，Qt不再报错。

如果SqlDatabase配置正确，还能看连接成功后修改的标题。


