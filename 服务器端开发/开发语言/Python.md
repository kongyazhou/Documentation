# Python

```
本文档写于2016年，文章针对python 3.4.4版本进行学习。
```

[廖雪峰Python3教程](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)

比Java还要高级的语言

为实现快速开发而设计的语言

Python将作为后台开发和算法设计主要使用的语言

## centOS服务器安装python3.4

#### 下载和安装

	tar xf Python-3.4.4.tgz -C /usr/local/src/ 
	cd /usr/local/src/Python-3.4.4/ 
	./configure --prefix=/usr/local/python3.4 
	make && make install

#### 添加 python3.4 命令到环境变量 

添加 python3.4 到环境变量，编辑 ~/.bash_profile，将： 

	PATH=$PATH:$HOME/bin 

改为： 

	PATH=$PATH:$HOME/bin:/usr/local/python3.4/bin 

#### 创建快捷键

ln -s /usr/local/python3.4/bin/python3.4 /usr/bin/python

## 内置的函数

```
官方有chm手册可以查询，非常方便。
```

基本输入输出

input()

print()

#### 一、数学相关

1. 绝对值：abs(-1)
2、最大最小值：max([1,2,3])、min([1,2,3])
3、序列长度：len('abc')、len([1,2,3])、len((1,2,3))
4、取模：divmod(5,2)//(2,1)
5、乘方：pow(2,3,4)//2**3/4
6、浮点数：round(1)//1.0

#### 二、功能相关

1、函数是否可调用：callable(funcname)，注意，funcname变量要定义过
2、类型判断：isinstance(x,list/int)
3、比较：cmp('hello','hello')
4、快速生成序列：(x)range([start,] stop[, step])

#### 三、类型转换

1、int(x)
2、long(x)
3、float(x)
4、complex(x) //复数
5、str(x)
6、list(x)
7、tuple(x) //元组
8、hex(x)
9、oct(x)
10、chr(x)//返回x对应的字符，如chr(65)返回‘A'
11、ord(x)//返回字符对应的ASC码数字编号，如ord('A')返回65

#### 四、字符串处理

1、首字母大写：str.capitalize
复制代码 代码如下:

>>> 'hello'.capitalize()

'Hello'

2、字符串替换：str.replace
复制代码 代码如下:

>>> 'hello'.replace('l','2')
'he22o'

可以传三个参数，第三个参数为替换次数

3、字符串切割：str.split
复制代码 代码如下:

>>> 'hello'.split('l')
['he', '', 'o']

可以传二个参数，第二个参数为切割次数
以上三个方法都可以引入String模块，然后用string.xxx的方式进行调用。

#### 五、序列处理函数

1、len：序列长度
2、max：序列中最大值
3、min：最小值
4、filter：过滤序列
复制代码 代码如下:

>>> filter(lambda x:x%2==0, [1,2,3,4,5,6])
[2, 4, 6]

5、zip：并行遍历
代码如下:

>>> name=['jim','tom','lili']
>>> age=[20,30,40]
>>> tel=['133','156','189']
>>> zip(name,age,tel)
[('jim', 20, '133'), ('tom', 30, '156'), ('lili', 40, '189')]

注意，如果序列长度不同时，会是下面这样的结果：
代码如下:

>>> name=['jim','tom','lili']
>>> age=[20,30,40]
>>> tel=['133','170']
>>> zip(name,age,tel)
[('jim', 20, '133'), ('tom', 30, '170')]

6、map：并行遍历，可接受一个function类型的参数
复制代码 代码如下:

>>> a=[1,3,5]
>>> b=[2,4,6]
>>> map(None,a,b)
[(1, 2), (3, 4), (5, 6)]
>>> map(lambda x,y:x*y,a,b)
[2, 12, 30]

7、reduce：归并
复制代码 代码如下:

>>> l=range(1,101)
>>> l
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100]
>>> reduce(lambda x,y:x+y,l)
5050

[内置函数大全](http://jianfeihit.iteye.com/blog/1835272)

## 框架

#### django

#### flask

#### tornado

多进程通信

如果一个进程收到一个SIGUSR1信号，然后执行信号绑定函数，第二个SIGUSR2信号又来了，第一个信号没有被处理完毕的话，第二个信号就会丢弃。



