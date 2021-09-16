# day01 【前言、入门程序、常量】

##### 今日复习指南

```java
1.入门案例(0.5个小时内完成,多写几遍)
	HelloWorld.java		编写,编译和运行
    
2.注释和关键字(0.5个小时内完成,多写几遍)
    Demo01ZhuShi.java
    Demo02GuanJianZi.java
    
3.常量及分类(1个小时内完成,演示效果)
    Demo03ChangLiang.java
    
4.其它知识(简单一看)
```



##### 主要内容

```java
Java语言的发展历史【了解】
Java语言开发环境搭建【重点:安装jdk,配置环境变量,安装notepad++】
HelloWorld入门程序【重点】
注释和关键字【理解】
常量【重点重点重点重点重点】
进制及转换【了解】
```



### 第一章 开发前言

##### 1.1 Java语言概述【了解】

```java
Java是一种高级编程语言，而且是面向对象的编程语言。
Java语言是美国Sun公司（Stanford University Network），在1995年推出的高级的编程语言。
Java语言共同创始人之一：詹姆斯·高斯林 （James Gosling），被称为“Java之父”
Java语言的版本：1.0-1.4，5.0...8.0...13.0
目前我们学习的8.0
```

##### 1.2 Java语言能做什么

```java
Java语言主要应用在互联网程序的开发领域
网上购物商城
物流
金融
各行各业的门户网站
```

##### 1.3 Java语言的跨平台实现原理

```java
JVM: Java虚拟机,是专门用来运行Java程序的
平台: 指的就是操作系统,比如windows,linux,macos等
跨平台: 我们编写的一个Java程序,可以做多个操作系统上运行
		一次编译,到处运行
    
1.问题1
	Java程序是跨平台的?	正确的
		一次编译到处运行

2.问题2
	JVM是跨平台的? 错误的
	JVM是实现Java程序跨平台的基石
	针对不同的操作系统提供不同的JVM
	而程序在JVM中运行

3.问题3
	Java程序的跨平台是依靠JVM的不夸平台实现的
	正确的
```

![image-20200507092958702](img/image-20200507092958702.png)

##### 1.4 JDK_JRE_JVM的组成和作用

```java
JVM: Java虚拟机,是专门用来运行Java程序的,但是不能单独安装
JRE: Java运行环境,包含JVM(Java虚拟机,是专门用来运行Java程序的)和核心类库
JDK: Java开发工具包,包含JRE和开发工具
    
小贴士：
三者关系： JDK > JRE > JVM
```

![image-20200420095512929](img/image-20200420095512929.png)

### 第二章 Java语言开发环境搭建

##### 2.1 JDK安装

```java
jdk的下载和安装
    1.注意操作系统是windows,linux,MacOS
    2.注意操作系统的位数是32位还是64位
    3.安装java相关软件的时候: 安装路径中不允许出现中文和空格
```



##### 2.2 常用DOS命令的使用

```java
如何进入DOS命令操作窗口?
    1.开始/命令提示符
    2.开始/搜索程序和文件 输入cmd
    3.windows键 + R --> 输入cmd
	4.窗口空白处/按住shift键 + 鼠标右键单击/在此处开命令窗口

```

![image-20200330102544966](img/image-20200330102544966.png)

![image-20200330102611049](img/image-20200330102611049.png)

##### 2.3 环境变量JAVA_HOME的配置【了解，已经配置了的话，大家不用过多的浪费时间】

```java
记事本软件的启动方式?
    1.开始/程序/附件/记事本
    2.C:/windows/找到notepad.exe命令,双击启动
    3.如果在DOS窗口的命令中:
		C:\windows> notepad.exe	回车 运行这个命令
        首先在C:\windows路径下,寻找是否存在notepad.exe,发现有,直接运行
            
       	D:\abc> notepad.exe	回车 运行这个命令
        首先:在D:\abc路径下,寻找是否存在notepad.exe,发现没有
        其次: 如果发现在当前路径D:\abc没有要运行的notepad.exe命令,到系统环境变量path中寻找
        path:... C:\Windows;...,发现path中配置的路径C:\Windows有该命令,直接运行.如果path中配置的所有的路径中都没有要运行的命令,运行报错了.
        
  
            
            
给Java配置环境变量的意义/目的/作用? 
       让我们可以在任意路径下运行java开发的相关工具(javac: 编译工具,java: 运行工具)
            
            
    比如jdk的安装路径:C:\develop\Java\jdk1.8.0_162
    配置步骤:
	1.创建名称为JAVA_HOME的环境变量,取值是 C:\develop\Java\jdk1.8.0_162
    2.把步骤1中创建的名称为JAVA_HOME的环境变量,添加到系统环境变量path中
    找到系统环境变量path,在前面添加: %JAVA_HOME%\bin;...
        
    3.如果在DOS窗口的命令中:
		C:\develop\Java\jdk1.8.0_162\bin> javac.exe	回车 运行这个命令
        首先在C:\develop\Java\jdk1.8.0_162\bin路径下,寻找是否存在javac.exe,发现有,直接运行
        
        D:\abc> javac.exe	回车 运行这个命令
        首先:在D:\abc路径下,寻找是否存在javac.exe,发现没有
        其次: 如果发现在当前路径D:\abc没有要运行的javac.exe命令,到系统环境变量path中寻找
        path:... %JAVA_HOME%\bin;...,发现path中配置的名称为JAVA_HOME的环境变量,对应的路径C:\develop\Java\jdk1.8.0_162\bin中有要运行的javac.exe命令,直接运行,如果path中配置的所有路径中,都没有要运行的javac.exe命令,运行报错了
            
        寻找名称为JAVA_HOME的环境变量,找到后,使用其配置的具体路径进行替换:
		path:... C:\develop\Java\jdk1.8.0_162\bin;...,
		替换后的路径: C:\develop\Java\jdk1.8.0_162\bin中有javac命令,就可以直接运行

```



![](img/JAVA_HOME.png)

![](img/JAVA_HOME2.png)    



### 第三章 HelloWorld入门程序

##### 3.1 程序开发的步骤

```java
1.源程序:
	程序员写的程序
	程序员在自己可以看得懂得程序
	程序: 字母,数字,其他符号
源程序是程序员编写的,程序员自己可以看得懂得程序,
本质就是一个文本文件,但是扩展名不是.txt,而是.java
    
2.生产JVM可以执行的字节码(.class)文件
    JVM: 叫做Java虚拟机,是专门用来运行Java程序的
    但是JVM是一个二货,只能识别0和1,而存储0和1的文件叫做字节码文件(.class文件)
    如何把源文件(程序)翻译成JVM能够执行的字节码文件(程序)呢?
    使用javac命令(编译命令)
    使用格式: javac 文件名.java
    编译HelloWorld.java源文件: javac HelloWorld.java
    生成一个字节码文件: HelloWorld.class 
        
3.把字节码文件交给JVM执行
    不管是源文件(程序)还是字节码文件(程序)都存储在硬盘中?
	不会自动执行,如何把字节码文件交给JVM执行呢?
	
    使用java命令(运行命令)
	使用格式: java 文件名
	java HelloWorld
```

![image-20200507105346651](img/image-20200507105346651.png)

##### 3.2 HelloWorld案例的编写编译运行

```java
1.编写源文件
    创建一个名称为HelloWorld.txt的文本文件,把扩展名修改为.java
    打开HelloWorld.java源文件,输入以下内容,并保存(ctrl+s)
    public class HelloWorld {
        public static void main(String[] args){
            System.out.println("HelloWorld");
        }
    }

2.编译: javac命令
    根据.java源文件生产对应的.class文件(字节码文件)
    使用javac命令的格式:
		javac 文件名.java
        javac HelloWorld.java
            
    注意:
		(1)保证当前路径下javac命令可以使用
        (2)保证当前路径下有要进行编译的源(.java)文件
        (3)使用编译javac命令时,文件名后面必须写扩展名.java
            
3.运行: java命令            
    把字节码(.class)文件交给jvm执行
    使用java命令的格式:
		java 文件名
        java HelloWorld 
    注意:
		(1)保证当前路径下java命令可以使用
        (2)保证当前路径下有要进行运行的字节码(.class)文件
        (3)使用运行java命令时,文件名后面不能写扩展名.class
            

```

##### 3.3 HelloWorld案例的常见问题

```java
非法字符问题。Java中的符号都是英文格式的。
大小写问题。Java语言对大小写敏感（区分大小写）。
在系统中显示文件的扩展名，避免出现HelloWorld.java.txt文件。
编译命令后的java文件名需要带文件后缀.java
运行命令后的class文件名（类名）不带文件后缀.class
不要把main写成mian
```

##### 3.4 Notepad++软件的安装和配置

![image-20200330120224421](img/image-20200330120224421.png)

搜狗输入法的设置: 中文状态使用英文标点符号

![image-20200420120351691](img/image-20200420120351691.png)

![image-20200420120702626](img/image-20200420120702626.png)

![image-20200420120741611](img/image-20200420120741611.png)

### 第四章 注释和关键字

##### 4.1 注释

```java
1.概念:
	用来解释说明程序的文字,是给程序员看的,不会影响程序的编译和运行效率。
2.分类：
    (1)当行注释: //  只能写一行内容
	(2)多行注释: /* 可以写多行(1行,2行...)内容 */
	(3)文档注释: /** 可以写多行(1行,2行...)内容  */				基本不用
        
        
//这里是定义一个类,类的名字叫做Demo01ZhuShi,
//而且文件名必须和类的名字保持一模一样,public class 目前是固定写法,目前记住,后面讲解
public class Demo01ZhuShi {
	/*
		这里是定义main方法,public static void main(String[] args)是固定写法
		main方法是程序的入口
	*/
	public static void main(String[] args){
		/*
			这是一个输出语句,用来向控制台输出显示内容的,
			()中的""里面的内容会被输出显示到控制台上
		*/
		System.out.println("zhushi....");
	}
}
```

##### 4.2 关键字

```java
/*
	邮箱:	@前面是用户名 @后面是使用的是哪家的邮箱
	
		zhangsan@163.com			正确的
		zhangsan@qq.com				正确的
		zhangsan_nigulasi@qq.com	正确的
		zhangsan@nigulasi@qq.com	错误的

		@理解为在邮箱当中具有特殊的含义和使用方式,不能胡乱用,看做邮箱名称中的关键字
	
	关键字:
		1.概念: 是指在程序中，Java已经定义好的单词，具有特殊含义和特殊使用方式。
			具体的哪些单词是关键字,它们的特殊含义和用法是什么?今天不讲解
			学习的目标: 要求能够辨识出程序中的关键字
			
		2.特点:
			(1)所有的字母都是小写的
			(2)高级编辑器中彩色显示
			
		3.说出以下程序中的关键字:
			public class static void 
*/
public class Demo02GuanJianZi {
	public static void main(String[] args){
		System.out.println("guanjianzi....");
	}
}
```



### 第五章 常量 

##### 5.1 常量的概念和分类

```java
数学中有常数的概念:
	y = x + 5;		//数字5是一个常数,其值不可以发生改变  
	b = a + 5.5;	//数字5.5是一个常数,其值不可以发生改变

数学中对常数进行了分类:
	比如: 
		数字5是一个整数常数,其值不可以发生改变
        数字5.5是一个小数数常数,其值不可以发生改变
            
数学中的常数,对应到java中叫常量,数学中的常数有分类,java中的常量也有分类,而且比数学中的分类更加丰富

1.概念:	在程序的执行过程中,其值不可以发生改变的量
2.分类:
	(1)整数常量:	100		200
    (2)小数常量:	5.5		7.7
    (3)字符常量:
		java中规定字符常量必须使用单引号''引起来,而且单引号''中只能写一个字符(不能不写,也不能写2个以上)
        举例:
			A:		'a'							正确的
            B:		''		里面什么都没有写  	   错误的
            C:		' '		里面有一个空格			正确的
            D:		'ab'						错误的				
            E:		'好'						    正确的
            F:		'女子'					   错误的
     (4)布尔常量:只有两个值true和false
     		true: 表示肯定的,对的,是的,正确的,成立的
            false:表示否定的,错的,不是的,却无的,不成立的
     (5)字符串常量:
		java中规定字符串常量必须使用双引号""引起来,而且单引号""中可以写多个字符(0个,1个,2个....)
        举例:
			A:		"a"								正确的
            B:	    "" 			里面什么都没有写	  正确的
            C:  	" "			里面有一个空格		   正确的
            D:		"ab"							正确的
            E:		"好"							   正确的
            F:		"女子"						   正确的
                
     (6)空常量: null
                
		快捷键: ctrl + d 复制一行
	 
	 	System.out.println(xxx);//把xxx输出到控制台,并换行
	 	System.out.print(xxx);//把xxx输出到控制台,不换行
```

##### 5.2 打印不同类型的常量

```java
public class Demo03ChangLiang {
	public static void main(String[] args){
		//(1)整数常量:	100		200		
		System.out.println(100);		
		System.out.println(200);
		
		//(2)小数常量:	5.5		7.7
		System.out.println(5.5);
		System.out.println(7.7);
		
		//(3)字符常量:
		System.out.println('a');
		//System.out.println('');//错误的: ''不能没有字符
		System.out.println(' ');//正确的: ' '有一个空格
		System.out.println('好');//正确的: ' '有一个空格
		//System.out.println('女子');//错误的: '女子'不能写2个及以上的字符
		
		//(4)字符串常量
		System.out.println("a");
		System.out.println("");
		System.out.println(" ");
		System.out.println("ab");
		System.out.println("好想你");
		System.out.println("女子");
		
		//(5)布尔常量
		System.out.println(true);
		System.out.println(false);
		
		//(6)空常量
		//System.out.println(null);//错误: 不能直接打印空常量null
	}
}
```

### 第六章 计算机中的进制与字节【了解了解】

##### 6.1 进制及转换

- 进制

  ```java
  进制的概念：逢几进一就叫做几进制
  进制的分类：
      十进制:	逢十进一		每位的数字0-9
      二进制:	逢二进一		每位的数字0-1
      八进制:	逢八进一		每位的数字0-7
      十六进制:  逢十六进一	   每位的数字0-9,10(A/a),11(B/b),12(C/c),13(D/d),14(E/e),15(F/f)
          
  ```

  

- 转换

  ```java
  1.十进制转十进制
      (十进制数字的每一位(从右向做)上隐藏了一个10的多少次方,第1位是10的0次方,第2位是10的1次方...):
  
      十进制数字1234(x^y: x的y次方):       
  		1234 = 4 + 30 + 200 + 1000
               = 4*10^0 + 3*10^1 + 2*10^2 + 1*10^3
              
  2.二进制转十进制(8421编码):	
  	(二进制数字的每一位(从右向做)上隐藏了一个2的多少次方,第1位是2的0次方,第2位是2的1次方...):
      1101 = 1*2^0 + 0*2^1 + 1*2^2 + 1*2^3
           = 1*1 + 0*2 + 1*4 + 1*8
         = 1 + 0 + 4 + 8
           = 13
        
      1111 = 1*2^0 + 1*2^1 + 1*2^2 + 1*2^3
         = 1*1 + 1*2 + 1*4 + 1*8
           = 1 + 2 + 4 + 8
           = 15
          
    
  3.十进制转二进制: 除以2取余数,倒过来写
      十进制的13转换成二进制:	1101
  	十进制的75转换成二进制:	1001011
  ```
  
  ##### 十进制转二进制图解:
  
  ![image-20200507150517171](img/image-20200507150517171.png)
  
  ##### 6.2 计算机中的存储单位(2的10次方就是1024) 

```java
1.位(bit): 计算机中存储一个数字0或者1所占用的空间   简写成b
2.字节(Byte): 8个位占用的空间叫做一个字节  		简写成B
    字节是我们常见的计算机中最小存储单元。
    1B = 8b
    1024B = 1KB
    1024KB = 1MB
    1024MB = 1GB
    1024GB = 1TB
    ....
    
    务必记住:
		1个字节是8位
```





##### 总结

```java
能够说出JDK,JRE,JVM各自的作用和关系
    JVM: Java虚拟机,是专门用来运行Java程序的,不能独立安装
    JRE: Java运行环境,包含JVM和核心类库
    JDK: Java开发环境,包含JRE和开发工具(javac编译,java运行)
        
能够完成HelloWorld案例的编写及运行
    1.编写
        public class HelloWorld {
            public static void main(String[] args) {
                System.out.println("HelloWorld");
            }
        }
	2.编译:
		javac HelloWorld.java  生产字节码文件HelloWorld.class
            
    3.运行:
		java HelloWorld
            
能够使用注释对程序进行说明
	//: 单行注释
    /*...*/: 多行注释
    /**...*/: 文档注释 			不用
能够知道关键字的特点            
   1.所有字母都是小写
   2.高级编辑器中彩色显示
        
能够知道常量的分类
   1.整数: 100,200
   2.小数: 6.6,8.8
   3.字符:
		'a' ''中只能写一个符号,不能不写,也不能写多个(2个及以上)
   4.布尔:
		true: 成立
        false: 不成立
   5.字符串:
		"abcd" ""中可以写多个字符(0个,1个,2个...)
   6.空常量null: 不能直接打印
       
```
