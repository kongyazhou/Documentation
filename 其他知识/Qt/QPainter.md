---
title: paintEvent(QPaintEvent *)函数重载
---

paintEvent(QPaintEvent *)函数是QWidget类中的虚函数，用于ui的绘制，会在多种情况下被其他函数自动调用，比如update()时。下面简单说一下绘制界面时所需要的东西。

1. QPainter类
这个类主要提供在窗体或者其他绘图设备上进行绘图的功能，在paintEvent(QPaintEvent *)中使用如下：
[cpp] view plaincopy在CODE上查看代码片派生到我的代码片
QPainter painter(this);  
此类中常用的函数有：
drawXXX()函数，用于绘制图形、文字和路径等；
fillXXX()函数，用于填充，可在指定区域内进行填充；
brush()和pen()  笔刷和钢笔的相关操作

2. QPainterPath类
这个类为绘图提供容器，主要还是用于描述绘制路径。可以通过函数setFillRule(Qt::WindingFill);来设置填充规则，通过addRect（）函数来添加绘制区域。
 
3. QColor类
此类提供颜色支持，这里的颜色可以定义四个属性：QColor ( int r, int g, int b, int a = 255 )，即红、绿、蓝和透明度。除此之外，也可以单个设置这四个值，通过类似setAlpha()的函数即可设置，这对设计渐进效果很有帮助。
 
下面送上一段摘自别人项目中的代码，仅供参考学习。
[cpp] view plaincopy在CODE上查看代码片派生到我的代码片

	void ABC::paintEvent(QPaintEvent *)  
	{  
	    QPainterPath path;  
	    path.setFillRule(Qt::WindingFill);  
	    path.addRect(10, 10, this->width()-20, this->height()-20);  
	  
	    QPainter painter(this);  
	    painter.setRenderHint(QPainter::Antialiasing, true);  
	    painter.fillPath(path, QBrush(Qt::white));  
	  
	    QColor color(0, 0, 0, 50);  
	    for(int i=0; i<10; i++)  
	    {  
	        QPainterPath path;  
	        path.setFillRule(Qt::WindingFill);  
	        path.addRect(10-i, 10-i, this->width()-(10-i)*2, this->height()-(10-i)*2);  
	        color.setAlpha(150 - qSqrt(i)*50);  
	        painter.setPen(color);  
	        painter.drawPath(path);  
	    }  
	} 
 