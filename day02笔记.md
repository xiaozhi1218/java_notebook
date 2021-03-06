# day02【进制、变量、类型转换、运算符】

##### 今日复习指南

```java
1.变量【重点: 用30分钟】
  	Demo01BianLiang.java 
    Demo02BianLiang.java
2.运算符【重点: 用1个小时】	
    Demo11Operator.java
    Demo12Operator.java
    Demo13Operator.java
    Demo14Operator.java
    Demo15Operator.java
    
	练习写代码时,必要的注释是需要的,但是千万不要像响哥一样写的这么详细,只要自己理解就ok了
    
3.数据类型转换【难点非重点: 理解,用30分钟】 大体看看
    

```

##### 今日内容介绍

```java
变量【重点】
数据类型转换【难点非重点: 理解】
运算符【重点】	
```



### 第二章 变量和数据类型【重要】

##### 2.1 变量概念及分类

```java
数学中有个常数的概念:
y = x + 10; 	//整数数字10是不可以发生变化的
b = a + 6.6;	//小数数字6.6是不可以发生变化的

数学中的数字(常量)是有分类的,对应java中的常量也是有分类的
    
x,y是可以发生变化的
	x: 2 y: 12
	x: 6 y: 16    

x,y中的数据是可以发生变化的,而且x,y内部的数据也是有类型(整数)
    
      
a,b是可以发生变化的
  a: 2.2 b: 8.8
  a: 3.3 b: 9.9    
b,b中的数据是可以发生变化的,而且a,b内部的数据也是有类型(小数)
      
像x,y,a,b 这样东西,里面的数据是可以发生变化的,而且数据是有类型的,我们把这样的东西称为变量(容器: 里面只能放一个数据)      

变量为什么要有这么多的分类: 不同的分类,占用的字节数不同,取值范围就不同,使用的场景也就不同

1.变量概念: 在程序的执行过程中,其值可以在一定范围内发生改变的量
2.分类:
	(1)整数
        byte		1个字节		-128到127
        short		2个字节		正负3万多
        int			4个字节		正负21亿		整数默认int类型
        long		8个字节		大概19位数字	   表示long类型数据后面需要加L/l
        
    (2)小数
        float		4个字节		表示float数据后面需要加F/f
        	注意: 虽然float占4个字节,但是由于采用科学计数法,取值范围远远超过long
        double		8个字节		小数默认double类型
                
    (3)字符:
		char		2个字节		
    (4)布尔:
		boolean		1个字节		取值为true或者false
            
```



##### 2.2 变量定义格式图解分析 

```java
变量的理解:
1.变量的本质就是内存中的一块空间,空间的大小由数据类型决定
2.要想找到变量对应的内存空间的数据,需要给变量对应的内存空间起个名字,叫做变量名称
3.变量对应的内存空间中必须有数据才能使用,这种向变量内存空间中,存储数据的过程叫做初始化或者赋值

变量的定义格式一(先挖坑,然后种萝卜):
	数据类型 变量名称;//先挖坑
	变量名称 = 数据值;//再种萝卜
	
变量的定义格式二(挖坑,同时种萝卜):
	数据类型 变量名称 = 数据值;//挖坑,同时种萝卜
	
变量的定义格式三(先挖多个坑,然后分别向每个坑中种萝卜):
	数据类型 变量名称1,变量名称2,变量名称3;//先挖多个坑
	变量名称1 = 数据值1;//向第一个坑中种萝卜
	变量名称2 = 数据值2;//向第二个坑中种萝卜
	变量名称3 = 数据值3;//向第三个坑中种萝卜
	
变量的定义格式四(挖多个坑,同时分别向每个坑中种萝卜):
	数据类型 变量名称1 = 数据值1,变量名称2 = 数据值2,变量名称3 =数据值3 ;	
	
```

##### 图解:

![image-20200508094901514](img/image-20200508094901514.png)





##### 2.3 定义8种变量

```java
public class Demo01BianLiang {
	public static void main(String[] args){
		/*
			变量的定义格式一(先挖坑,然后种萝卜):
			数据类型 变量名称;//先挖坑
			变量名称 = 数据值;//再种萝卜
		*/
		byte a;//挖了一个byte类型(1个字节)的坑,给这个坑起个名字叫a
		
		a = 66;//把数字66存储到byte类型的坑a中
		
		System.out.println(a);//打印byte类型(1个字节)的坑a中的内容: 66
		
		a = 88;//把数字88存储到byte类型的坑a中,原有的数据66将被替换
		
		System.out.println(a);//打印byte类型(1个字节)的坑a中的内容: 88
		
		/*
			变量的定义格式二(挖坑,同时种萝卜):
				数据类型 变量名称 = 数据值;//挖坑,同时种萝卜
		*/
		short b = 100;//挖了一个short类型(2个字节)的坑,给这个坑起个名字叫b,同时向这个坑中存储数字100
		
		System.out.println(b);//打印short类型(2个字节)的坑b中的内容: 100
		
		/*
			变量的定义格式三(先挖多个坑,然后分别向每个坑中种萝卜):
			数据类型 变量名称1,变量名称2,变量名称3;//先挖多个坑
			变量名称1 = 数据值1;//向第一个坑中种萝卜
			变量名称2 = 数据值2;//向第二个坑中种萝卜
			变量名称3 = 数据值3;//向第三个坑中种萝卜
		*/
		int c,d,e;//挖了三个int类型(4个字节)的坑,给每个坑分别起名为c,d,e
		
		c = 200;//把数字200存储到int类型的坑c中
		d = 300;//把数字300存储到int类型的坑d中
		e = 500;//把数字500存储到int类型的坑e中
		
		System.out.println(c);//打印int类型(4个字节)的坑c中的内容: 200
		System.out.println(d);//打印int类型(4个字节)的坑d中的内容: 300
		System.out.println(e);//打印int类型(4个字节)的坑e中的内容: 500
		
		/*
			变量的定义格式四(挖多个坑,同时分别向每个坑中种萝卜):
			数据类型 变量名称1 = 数据值1,变量名称2 = 数据值2,变量名称3 =数据值3 ;
		*/
		//挖了三个long类型的坑,名字分别叫做f,g,h
		//同时把600L存储到坑f中
		//同时把700L存储到坑g中
		//同时把800L存储到坑h中
		long f = 600L,g = 700L,h = 800L;
		
		System.out.println(f);//打印long类型(8个字节)的坑f中的内容: 600
		System.out.println(g);//打印long类型(8个字节)的坑g中的内容: 700
		System.out.println(h);//打印long类型(8个字节)的坑h中的内容: 800
		
	}
}
```

```java
public class Demo02BianLiang {
	public static void main(String[] args){
		//float类型
		//定义float类型变量a,并初始化
		//大萝卜不能直接存储到小坑中
		//float a = 6.6;//错误: 6.6默认是double类型,占8个字节,不能存储到4个字节的float变量中
		
		float a = 6.6F;
		System.out.println(a);//打印变量a中的内容
		
		//double类型
		//定义double类型变量b,并初始化
		double b = 8.8;
		System.out.println(b);//打印变量b中的内容
		
		//char类型
		//定义char类型变量c1,并初始化
		char c1 = 'a';
		System.out.println(c1);//打印变量c1中的内容
		
		//char c2 = '';//错误: ''中不能不写字符
		//System.out.println(c2);//打印变量c2中的内容
		
		//char c3 = 'ab';//错误: ''中不能写2个及以上的字符
		//System.out.println(c3);//打印变量c3中的内容
		
		//boolean类型: 只能存储true或者false
		//定义boolean类型变量d1,并初始化
		boolean d1 = true;
		System.out.println(d1);//打印变量d1中的内容
		
		d1 = false;//把false存储到变量d1中,原有的数据将被替换
		
		System.out.println(d1);//打印变量d1中的内容
		
		//d1 = 100;//错误: 数据类型不匹配
		//System.out.println(d1);//打印变量d1中的内容
		
		
	}
}
```



##### 2.4 变量的注意事项

```java
变量定义的注意事项:
	1.变量名称：在同一个大括号范围内，变量的名字不可以相同。
	2.变量赋值：定义的变量，不赋值不能使用。
	3.定义long类型的变量时，需要在整数的后面加L（大小写均可，建议大写）。
		因为整数默认是int类型，整数太大可能超出int范围。
		
	4.定义float类型的变量时，需要在小数的后面加F（大小写均可，建议大写）。
		因为浮点数的默认类型是double， double的取值范围是大于float的，类型不兼容。
        
public class Demo03BianLiangNotice {
	public static void main(String[] args){
		
		//定义int变量a,并初始化
		int a = 100;		
		System.out.println(a);
		
		//错误: 不能在同一个区域({}),定义同名的变量
		//int a = 200;
		//System.out.println(a);
		
		//定义int变量b,未赋值
		int b;
		//System.out.println(b);//错误: b中没有值,不能使用
		
		b = 200;//把数字200赋值给变量b
		System.out.println(b);
		
		//long c = 6000000000;//错误: 6000000000(60亿)默认是int类型,但是大小已经远远超过int的取值范围(正负21亿)了
		//System.out.println(c);
		
		long d = 6000000000L;//6000000000L: 是long类型的数据
		System.out.println(d);
		
		//错误: 大萝卜不能直接放入小坑中
		//float e = 6.6;//错误: 6.6默认是double类型,占8个字节,不能赋值给4个字节的float变量e
		//System.out.println(e);
		
		float f = 6.6F;//6.6F: 是float类型的数据
		System.out.println(f);
	}
}
```



##### 2.5 标识符的含义及注意事项

```java
标识符:
	1.概念: 程序中起名字的地方(类名,方法名称,变量名)
	2.命名规则： 硬 性 要 求
		标识符可以包含 英文字母26个(区分大小写) 、 0-9数字 、 $（美元符号） 和 _（下划线） 。
		标识符不能以数字开头。
		标识符不能是关键字。
	3.命名规范： 软 性 建 议
        类名规范：首字母大写，后面每个单词首字母大写（大驼峰式）。
			Demo01BianLiang
			Demo02BianLiang
			Demo03BianLiangNotice
			Demo04BiaoShiFu
				
		方法名规范： 首字母小写，后面每个单词首字母大写（小驼峰式）。
			getMin(...){...}
			getMax(...){...}
				
		变量名规范：首字母小写，后面每个单词首字母大写（小驼峰式）。
			num
			value
			maxValue
public class Demo04BiaoShiFu {
	public static void main(String[] args){
		int b2;//正确
		//int b*2;//错误: 不能包含*
		
		//int 2b;//错误: 不能以数字开头
		
		//int public;//错误: 不能是关键字。
		
		//按照小驼峰规则,定义变量
		int ageOfMyGirlFriend = 18;
		System.out.println(ageOfMyGirlFriend);
	}
}
```



### 第三章 数据类型转换【理解】

##### 3.1 自动类型转换【从小到大自动】

```java
Java程序中要求参与的计算的数据，必须要保证数据类型的一致性，如果数据类型不一致将发生类型的转换。
    int + int
    int + long ==> long + long  (把int转换成long: 从小到大,自动类型转换,不需要代码的干预)
    int + long ==> int + int  (把long转成int: 从大到小,强制类型转换,必须手动代码完成)
    

1.自动类型转换概念:
	取值范围小的数据或者变量可以直接赋值给取值范围大的变量(小萝卜可以直接放入大坑中)
        
2.特点: 
	(1)自动类型转换是自动完成的,不需要代码的干预
    (2)byte/short/char类型数据,只要参加运算会自动转换为int类型    
    (3)byte、short、char-->int-->long-->float-->double
举例:
有一个byte类型(1个字节)的数字5:			00000101	
byte类型自动类型转换成short类型(2个字节):
	在左侧补充1个字节的0,因为左侧补充的都是0,对原有数据是没有影响的,仍然是5
	00000000 00000101 

byte类型自动类型转换成int类型(4个字节): 
	在左侧补充3个字节的0,因为左侧补充的都是0,对原有数据是没有影响的,仍然是5
	00000000 00000000 00000000 00000101
    
byte类型自动类型转换成long类型(8个字节):  
	在左侧补充7个字节的0,因为左侧补充的都是0,对原有数据是没有影响的,仍然是5
	00000000 00000000 00000000 00000000 00000000 00000000 00000000 00000101

总结:
	根据需求,在数据前面补充若干字节的0,因为补充的都是0,对原有数据大小是没有影响的(打肿脸充胖子)
```

```java
public class Demo05Convert {
	public static void main(String[] args){
		int i = 1; 
		byte b = 2; 
		/*
			b是byte类型,i是int类型,运算时类型不一致,会发生自动类型转换
			byte类型(1个字节)的b会自动转换成int类型(4个字节):在byte类型的b左侧补充3个字节的0
			
			最终变成了两个int数据相加,结果是int类型(占用4个字节),不能直接赋值给左侧的byte类型的变量x,占用1个字节
			
			大萝卜不能直接放入小坑中
		*/
		//byte x = b + i; 
		//System.out.println(x);
		
		/*
			b是byte类型,i是int类型,运算时类型不一致,会发生自动类型转换
			byte类型(1个字节)的b会自动转换成int类型(4个字节):在byte类型的b左侧补充3个字节的0
			
			最终变成了两个int数据相加,结果是int类型(占用4个字节),可以直接赋值给左侧的int类型的变量y,占用4个字节
			
			大萝卜可以直接放入大坑中
		*/
		int y = b + i;
		System.out.println(y);//3
	}
}
```

```java
public class Demo06Convert {
	public static void main(String[] args){
		int i = 1; 
		double d = 2.5;
		/*
			i是int类型,d是double类型,运算时类型不一致,会发生自动类型转换
			int类型(4个字节)的i会自动转换成double类型(8个字节): 最终效果就是在整数后面添加.0 比如: 1变成1.0
			
			最终变成了两个double数据相加,结果是double类型(占用8个字节),不能直接赋值给左侧的int类型的变量x,占用4个字节
			
			大萝卜不能直接放入小坑中
		*/
		//int x = i + d;		
		//System.out.println(x);
		
		/*
			i是int类型,d是double类型,运算时类型不一致,会发生自动类型转换
			int类型(4个字节)的i会自动转换成double类型(8个字节): 最终效果就是在整数后面添加.0 比如: 1变成1.0
			
			最终变成了两个double数据相加,结果是double类型(占用8个字节),可以直接赋值给左侧的double类型的变量y,占用8个字节
			
			大萝卜可以直接放入大坑中
		*/
		double y = i + d;
		System.out.println(y);
	}
}
```



##### 3.2 强制类型转换【从大到小强制】


```java
1.强制类型转换概念:	
	取值范围大的数据或者变量不能直接赋值给取值范围小的变量(大萝卜不能直接放入小坑中)
        解决方案:
			(1)把坑变大
            (2)把萝卜变小(强制类型转换)

2.格式:
	转后类型 变量名称 = (转后类型)转前数据或者变量;
	long类型(8个字节)的数字5:
	long num = 5L;
	long类型强制类型转换成int类型(4个字节):
	int a = (int)num;//把num中的数据强制类型转换成int类型,并把结果赋值给int变量a

举例:
有一个long类型(8个字节)的数字5:	
	00000000 00000000 00000000 00000000 00000000 00000000 00000000 00000101

long类型强制类型转换成int类型(4个字节): 
	砍掉左侧的四个字节的内容,因为砍掉的都是数字0,所以对最终的结果数据没有影响仍然是5
    00000000 00000000 00000000 00000101    
	

long类型强制类型转换成short类型(2个字节):
	砍掉左侧的六个字节的内容,因为砍掉的都是数字0,所以对最终的结果数据没有影响仍然是5
	00000000 00000101
        
long类型强制类型转换成byte类型(1个字节):
	砍掉左侧的七个字节的内容,因为砍掉的都是数字0,所以对最终的结果数据没有影响仍然是5
    00000101    

总结: 
    根据需求,砍掉数据左侧的若干字节的数据,只要砍掉的都是0,对原数据没有影响
        但是只要砍掉的数据中包含1,就会对原数据产生影响(可能会损失精度)
```

```java
public class Demo07Convert {
	public static void main(String[] args){
		double d = 1.5;
		/*
			左侧d是double类型(占8个字节),右侧的int类型的变量x(占4个字节)
			相当于: 左侧是较大的数据,右侧的变量比较小
			大萝卜不能直接放入小坑中
		*/
		//int x = d;
		//System.out.println(x);
		/*
			左侧d是double类型(占8个字节),右侧的int类型的变量x(占4个字节)
			double数据是不能直接赋值给int变量的: 大萝卜不能直接放入小坑中
			但是进行了强制类型转换,把double数据强制转换成int数据
			
			double强制类型转换成int: 直接把小数部分干掉,会损失精度
		*/
		
		int y = (int)d;
		
		System.out.println(y);
	}
}
```



```java
public class Demo08Convert {
	public static void main(String[] args){
		short s = 1;
		/*
			s是short类型,1是int类型,运算时类型不一致,会发生自动类型转换
			short类型(2个字节)的s会自动转换成int类型(4个字节):在short类型的s左侧补充2个字节的0
			
			最终变成了两个int数据相加,结果是int类型(占用4个字节),不能直接赋值给左侧的short类型的变量s,占用2个字节
			
			大萝卜不能直接放入小坑中
		*/
		//s = s + 1;		
		//System.out.println(s);
		
				
		/*
			s是short类型,1是int类型,运算时类型不一致,会发生自动类型转换
			short类型(2个字节)的s会自动转换成int类型(4个字节):在short类型的s左侧补充2个字节的0
			
			最终变成了两个int数据相加,结果是int类型(占用4个字节),不能直接赋值给左侧的short类型的变量s,占用2个字节
			
			但是在赋值之前把int类型的结果,强制转换成short类型(砍掉左侧的2个字节的内容),
			由于砍掉的2个字节都是0,所以最终的结果没有影响,仍然是2
			
			把萝卜变小
		*/
		s = (short)(s + 1);
		System.out.println(s);
	}
}
```



##### 图解(其它案例):

![image-20200508120946828](img/image-20200508120946828.png)



##### 3.3 ASCII码表

```java
计算机是一个二货,只能存储0和1,所以存储到计算机中的所有内容都会转换成0和1进行存储
所以我们在计算机中存储的字符也不例外,也需要把字符转换成0和1进行存储
问题: 如何把字符转换成0和1呢?
通过ASCII编码表: 存储字符和数字对应关系的一张表格
    
存储字符时：需要查找ASC码表,找到字符对应的数字,将数字转换为二进制数存放到计算机中
	'A'	---> 65 ---> 1000001		大写字母是连续的,ASCII编码值依次+1
    'a' ---> 97 ---> 1100001		小写字母是连续的,ASCII编码值依次+1
    '0' ---> 48 ---> 110000		    数字字符是连续的,ASCII编码值依次+1
    
使用字符时：将对应的二进制数转换为十进制 找到ASC表中对应的字符 
    1000001 ---> 65 ---> 'A'
    1100001 ---> 97 ---> 'a'
    110000  ---> 48 ---> '0'

    
```

![image-20200508115505469](img/image-20200508115505469.png)

##### 3.4 int类型和char类型的运算原理

```java
public class Demo09Char {
	public static void main(String[] args){
		//定义char类型的变量ch,并初始化为'A'
		char ch = 'A';
		System.out.println(ch);//A
		/*
			自动类型转换中:
				byte/short/char类型,只要参加运算,会自动转换为int类型
				
			ch是char类型,在参加运算时,自动转为int类型
			问题:
				char类型如何转换为int类型的数字呢?
				查看ASCII编码表: 找到'A'对应的数字是65,然后参与运算
				
		*/
		System.out.println(ch+1);//66
		/*
			自动类型转换中:
				byte/short/char类型,只要参加运算,会自动转换为int类型
				
			ch是char类型,在参加运算时,自动转为int类型
				查看ASCII编码表: 找到'A'对应的数字是65,然后参与运算
				所以: ch + 1 的结果是66
				
			然后把int数字66强制转换成char类型的数据
			问题:
				int类型的数据如何强制转换成char类型数据呢?
				查看ASCII编码表: 找到int数字66对应的字符'B'显示出来
		*/
		System.out.println((char)(ch+1));//B
	}
}
```



### 第四章 运算符

##### 4.1 算术运算符加减乘除

```java
1.运算符：对常量或者变量进行操作的符号 
2.表达式：用运算符把常量或者变量连接起来符合java语法的式子就可以称为表达式。
3.数学运算符:
	(1)+: 加法运算
    (2)-: 减法运算
    (3)*: 乘法运算
    (4)/: 除法运算
/*
	算数运算符
		1.运算符：对常量或者变量进行操作的符号 
		2.表达式：用运算符把常量或者变量连接起来符合java语法的式子就可以称为表达式。
		3.数学运算符:
			(1)+: 加法运算
			(2)-: 减法运算
			(3)*: 乘法运算
			(4)/: 除法运算
				被除数 ÷ 除数 = 商(/: 取的就是商) ......	余数
*/
public class Demo10Operator {
	public static void main(String[] args){
		int a = 3;
		int b = 2;
		System.out.println(a + b);//3 + 2: 5 
		System.out.println(a - b);//3 - 2: 1 
		System.out.println(a * b);//3 * 2: 6 
		//3/2: int/int 结果必然是int类型
		System.out.println(a / b);//3 / 2: 1 
		
		//int * double / int ==> double /	int ==> double / double ==> double
		System.out.println((a*1.0) / b);//3.0 / 2 ==> 3.0/2.0 ==> 1.5 				 
	}
}
```



##### 4.2 算术运算符%

```java
/*
	%运算符: 取余数(模)运算符
		被除数 ÷ 除数 = 商(/: 取的就是商) ......	余数(%: 取的就是余数)
		
	作用:
		1.判断数字的奇偶性: 
			数字%2 结果是0 说明数字是偶数
			数字%2 结果不是0 说明数字是奇数
			
		2.判断一个数字是否能够被另外一个数字整除
			结果为0: 说明可以整除
			结果不为0: 说明不可以整除
			
		3.可以把%和/结合使用计算数字的个位,十位,百位,千位
			比如有个int变量num,保存数字1234
			int num = 1234;
			个位: num%10
			十位: num/10%10
			百位: num/100%10
			千位: num/1000%10
*/
public class Demo11Operator {
	public static void main(String[] args){
		System.out.println(10%2);//0 说明10是偶数
		System.out.println(11%2);//1 说明11是奇数
		
		System.out.println(100%25);//0 说明100可以被25整除
		System.out.println(100%26);//22 说明100不可以被26整除
		
		System.out.println("---------------");
		int num = 1234;
		System.out.println(num%10);//4: 个位    1234 ÷ 10 = 商123 .... 余数4(%)
		//System.out.println(num/10);//123	    1234 ÷ 10 = 商123(/) .... 余数4(%)
		System.out.println(num/10%10);//3 十位  123 ÷ 10 = 商12(/) ...  余数3(%)
		
		//System.out.println(num/100);//12     1234 ÷ 100 = 商12(/) ... 余数34(%)
		
		System.out.println(num/100%10);//2 百位 12 ÷ 10 = 商1(/) ...  余数2(%)
		
		System.out.println(num/1000%10);//1 千位
	}
}
```

![image-20200421144143935](img/image-20200421144143935.png)

##### 4.3 算术运算符+的特殊用法

```java
/*
	+符号的作用
		1.数学中的加法运算(数字相加,字符相加)
		2.字符串的拼接(把两个字符串连在一起)
*/
public class Demo12Operator {
	public static void main(String[] args){
		System.out.println(5+5);//10
		/*
			int + char ==> int + int ==> int
			需要:
				char ==> int 查看ASCII码表 'A'对应65
		*/
		System.out.println(5+'A');//5 + 65: 70
		/*
			自动类型转换中:
				byte/short/char类型,只要参加运算,会自动转换为int类型
			char + char ==> int + int ==> int
			需要:
				char ==> int 查看ASCII码表 'A'对应65
				char ==> int 查看ASCII码表 'B'对应66
		*/
		System.out.println('A'+'B');//65 + 66: 131
		
		System.out.println("Hello"+"World");
		//"5+5="+5+5: 从左向右计算
		//先计算"5+5="+5: 此处+号代表字符串的连接 结果是"5+5=5"
		//然后"5+5=5"+5: 此处+号代表字符串的连接 结果是"5+5=55"
		System.out.println("5+5="+5+5);//5+5=55
		
		//()的优先级是比较高的,所以先计算5+5 结果10
		//然后"5+5="+10: 此处+号代表字符串的连接 结果是"5+5=10"
		System.out.println("5+5="+(5+5));//5+5=10

		
	}
}
```



##### 4.4 赋值运算符

```java
/*
	基本赋值运算符: =
	复合赋值运算符:
		+=		a+=b		a=a+b
		-=		a-=b		a=a-b
		*=		a*=b		a=a*b
		/=		a/=b		a=a/b
		%=		a%=b		a=a%b
*/
public class Demo13Operator {
	public static void main(String[] args){
		int a = 10,b = 20;
		a += b;//a = a + b
		System.out.println(a);//30
		System.out.println(b);//20
		
		int c = 30,d = 20;
		c %= d;//c = c % d = 30%20 = 10
		
		System.out.println(c);//10
		System.out.println(d);//20
	}
}

```



##### 4.5 赋值运算符的特点

```java
/*
	赋值运算符特点
		1.+=,-=,/=,*=,%= 运算结果的数据类型和左侧变量的数据类型不一致,隐藏强制类型转换
		2.整数常量只要不超出所赋值的整数变量的取值范围,可以直接赋值,内部隐藏强制类型转换
*/
public class Demo14Operator {
	public static void main(String[] args){
		short s = 1;
		/*
			s是short类型,1是int类型,运算时类型不一致,会发生自动类型转换
			short类型(2个字节)的s会自动转换成int类型(4个字节):在short类型的s左侧补充2个字节的0
			
			最终变成了两个int数据相加,结果是int类型(占用4个字节),不能直接赋值给左侧的short类型的变量s,占用2个字节
			
			大萝卜不能直接放入小坑中
		*/
		//s = s + 1;		
		//System.out.println(s);
		
				
		/*
			s是short类型,1是int类型,运算时类型不一致,会发生自动类型转换
			short类型(2个字节)的s会自动转换成int类型(4个字节):在short类型的s左侧补充2个字节的0
			
			最终变成了两个int数据相加,结果是int类型(占用4个字节),不能直接赋值给左侧的short类型的变量s,占用2个字节
			
			但是在赋值之前把int类型的结果,强制转换成short类型(砍掉左侧的2个字节的内容),
			由于砍掉的2个字节都是0,所以最终的结果没有影响,仍然是2
			
			把萝卜变小
		*/
		s = (short)(s + 1);
		System.out.println(s);
		
		short s2 = 1;
		/*
			+=,-=,/=,*=,%= 运算结果的数据类型和左侧变量的数据类型不一致,隐藏强制类型转换
		*/
		s2 += 1;//s2 = (short)(s2 + 1);
		
		System.out.println(s2);
		/*
			右侧10是int类型(4个字节),左侧变量byte类型(1个字节)
			按照道理来讲: 大萝卜是不可以直接放入小坑中的
			现在为什么可以呢?
			原因是数字10是一个常量,值并没有超出byte的取值范围
			所以可以直接赋值,内部会帮助我们进行强制类型转换
			等价于:
				byte b = (byte)10;
		*/
		byte b = /*(byte)*/10;
		System.out.println(b);//10
	}
}
```

##### 4.6 自增自减运算符

```java
/*
	自增(++)自减(--)运算符(代码演示只演示++)
		1.作用: 让变量的值增加1(++)或者减少1(--)
		2.使用格式:
			(1)可以写在变量的前面: ++a,--a
			(2)可以写在变量的后面: a++,a--
		
		3.使用特点:
			(1)单独使用: ++/--自己独占一行,没有其它运算一起参与
				前++和后++,没有任何区别,都是让变量的值增加1
				前--和后--,没有任何区别,都是让变量的值减少1
				
			(2)混合使用: 和其它运算(赋值,打印等)一起
				前++/--: 先++/--,后再使用		先给变量的值增加(++)或者减少(--)1,然后再使用++/--后的结果
				后++/--: 先使用,然后++/--		先使用变量的值,再把变量的值	增加(++)或者减少(--)1
		
		
	重点:					----最常用的东西
		a++: 变量a的值增加1
		a--: 变量a的值减少1
*/
public class Demo15Operator {
	public static void main(String[] args){
		int a = 2;
		//++自己独占一行,没有其它运算一起参与
		a++;//a = a + 1 = 2 + 1
		System.out.println(a);//3
		
		int b = 2;
		//++自己独占一行,没有其它运算一起参与
		++b;//b = b + 1 = 2 + 1
		System.out.println(b);//3
		
		System.out.println("-----------------");
		int c = 2;
		/*
			目前是++和赋值一起操作,属于混合运算
			而且++写在了c的前面,先把c的值增加1,
			c的值变为3,然后再把结果3赋值给变量d,d的值3			
		*/
		int d = ++c;
		
		System.out.println(c);//3
		System.out.println(d);//3
		System.out.println("-----------------");
		
		int e = 2;
		/*
			目前是++和赋值一起操作,属于混合运算
			而且++写在了e的后面,所以先使用e的值(2)赋值给变量f,所以f的值是2,
			然后e的值再增加1,变成3
		*/
		int f = e++;
		
		System.out.println(e);//3
		System.out.println(f);//2
		
		System.out.println("-----------------");
		
		int x = 4; //5 6
		/*
			表达式(x++)+(++x)+(x*10)是从左到右计算的
			先计算(x++): 因为++在后面,先使用x的值4,然后x的值增加,变成5
			4 + (++x)+(x*10)
			接着计算(++x): 因为++在前面,先把x的值增加1,x变成6,然后再使用6
			4 + 6+(x*10)
			接着计算x*10 -->  6*10 结果: 60
			4 + 6 + 10 结果: 70
		*/
		int y = (x++)+(++x)+(x*10);
				// 4 + 6 + 
		System.out.println(x);//6
		System.out.println(y);//70
		
	}
}
```



## 总结

```java
能够说出8种基本数据类型 
    四类八种:
		整数: byte,short,int,long
        小数: float,double
        字符:char
        布尔:boolean
        
能够完成变量的定义及输出
    int a = 10;

	int b;
	b = 20;

	int c,d,e;
	c = 30;
	d = 40;
	e = 50;

	int f = 60,g = 70;

    
能够知道类型转换的格式和顺序【小到大自动，大到小强制】
    double d = 6.6;
	int a = (int)d;
   
能够说出常见的运算符有哪几种
    数学运算符: +,-,*,/,%
    赋值运算符: +=,-=,/=,*=,%=
    自增,自减运算符: ++,--
        
能够知道除法和取余的区别
     /: 除法	求的是商
     %: 取余  求的余数
        
能够完成字符和字符串的加
    +:
		(1)数学中的加法运算(数字和数字,数字和字符,字符和字符)
        (2)字符串的连接: +的左侧或者右侧一点出现字符串,就无法进行数学意义上的加法运算,代表字符串的连接
            
```



