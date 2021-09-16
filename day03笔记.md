# day03 【IDEA、运算符、数据输入】

##### 今日复习指南

```java
1.IDEA操作(0.5个小时内完成)
    (1)创建项目
    (2)创建模块
    (3)创建包
    (4)创建类
2.运算符(0.5个小时内完成)
    (1)关系运算符:Demo01GuanXi.java
	(2)逻辑运算符:Demo03DuanLu.java						短路&&和||
	(3)三元运算符:Demo03SanYuanMax.java					三个和尚的最大身高
3.键盘录入(1个小时内完成: 多练几遍)
    Demo02ScannerSum.java								获取键盘录入的两个int数字求和
    Demo03ScannerMax.java								获取键盘录入的三个int数字求最大值

```

##### 今天内容介绍

```java
IDEA【重点：操作】
运算符【重点：理解】
数据输入【重点：格式需要记忆】
练习【重点：操作】
```

### 第一章 开发工具IntelliJ IDEA

##### 1.1 IDEA开发工具的安装

##### 1.2 IDEA的首次驱动

```java
查看文件夹IDEA操作文档\01_首次驱动项目和模块的创建.docx文件
```

![image-20200423095232276](img/image-20200423095232276.png)

##### 1.3 IDEA的包和类的创建

```java
查看文件夹IDEA操作文档\02_包和类的创建.docx
```

##### 1.4 IDEA字体的设置和快捷键的修改

```java
查看文件夹IDEA操作文档\03_字体设置及快捷键修改.docx
```

![image-20200423100303569](img/image-20200423100303569.png)

##### 修改字体

![image-20200423100359715](img/image-20200423100359715.png)

##### ctrl+滚轮放大/缩小字体

![image-20200423100524073](img/image-20200423100524073.png)



![image-20200423140027699](img/image-20200423140027699.png)

##### 1.5 IDEA工程目录的介绍

![image-20200423102650103](img/image-20200423102650103.png)

##### 1.6 IDEA快捷键的使用

```java
1.psvm + 回车: main方法
2.sout + 回车: 输出语句
3.ctrl + d: 复制当前行
4.ctrl + alt + L: 格式化代码
5.alt + shift + ↑: 向上移动代码
6.alt + shift + ↓: 向下移动代码
7.ctrl + /: 单行注释
8.ctrl + shift + /: 多行注释
9.alt + 回车: 代码修正
10.alt + /: 自动提示
11.ctrl + Y: 删除当前行
    
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("HelloWorld");
        int a = 1, b = 2, c = 3;

        /*int num = 10;
        byte d = num;*/

        int i = a;



    }
}

```

##### 1.7 IDEA创建模块和删除模块

```java
查看文件夹IDEA操作文档\04_非首次模块的创建导入删除.docx
```

##### 1.8 IDEA导入项目和关闭项目

```java
查看文件夹IDEA操作文档\05_非首次项目的创建导入打开.docx
```



### 第二章 运算符

##### 2.1 关系运算符

```java
1.作用:
	用来比较数据之间的大小关系
        
2.特点:
	不管关系表达式多么复杂或者多么简单,返回值一定是布尔类型的结果,要么是true,要么是false
        
3.分类:
	== 		a==b，判断a和b的值是否相等，成立为true，不成立为false
    != 		a!=b，判断a和b的值是否不相等，成立为true，不成立为false
    > 		a>b，判断a是否大于b，成立为true，不成立为false
    >= 		a>=b，判断a是否大于或者等于b，成立为true，不成立为false
    < 		a<b，判断a是否小于b，成立为true，不成立为false
    <= 		a<=b，判断a是否小于或者等于b，成立为true，不成立为false
        
4.注意:
	(1)=: 一个等号是赋值的意思
    (2)==: 两个等号是判断是否相同的意思
```

```java
public class Demo01GuanXi {
    public static void main(String[] args) {
        int a = 10, b = 20;
        boolean result = (a == b);
        System.out.println(result);//false
        System.out.println(a != b);//10 != 20: true
        System.out.println(a > b);//10 > 20: false
        System.out.println(a >= b);//10 >= 20: false
        System.out.println(a < b);//10 < 20: true
        System.out.println(a <= b);//10 <= 20: true
        System.out.println(a == b);//10 == 20: false
        System.out.println(a = b);//20 把变量b的值赋值给变量a,最后打印变量a的值
    }
}

```



##### 2.2 逻辑运算符

```java
举例: 咱们班哥们在黑马学习java,顺利毕业,高薪就业,找到了对象,谈了好长时间,需要谈婚论嫁
到你对象家和准岳母谈判:
	准岳母:
		小伙子呀,你必须得有房子(条件1: true/false),然后呢,你必须还得有车子(条件2: true/false)		
        以上的要求: 两个条件都得满足(true),这个事才能确定下来			使用逻辑运算符	&
            
        小伙子呀,你要么有房子(条件1: true/false),你呀要么有车子(条件2: true/false)		
        以上的要求: 两个条件只要有一个满足(true),这个事就能确定下来			使用逻辑运算符	|
            
    
1.作用: 
	用来连接多个条件(布尔表达式的: 结果为true/false的式子),最终的结果也必须是一个布尔类型的数据,要么是true,
	要么是false
    不管逻辑运算符连接的式子有多么简单或者多么复杂,最终结果要么是true,要么是false    
2.分类:
	(1)&(shift+7): 逻辑与,表示并且的意思,多个条件同时成立的意思,就是只有多个条件都是true,最终的结果才是true
        特点:
			【有false，则false】： 只要有一个条件不成立（false），结果就是false
    (2)|(shift+\): 逻辑或,表示或者的意思,多个条件,只要有一个成立,最终的结果就是true
        特点:
        	【有true，则true】：只要有一个条件是true，结果就是true
    (3)^(shift+6): 逻辑异或,相同为false,不同为true			----基本不用
    (4)!(shift+1): 逻辑取反,!true 就是false,!false 就是true
        
```

```java
public class Demo02LuoJi {
    public static void main(String[] args) {
        int a = 10,b = 20,c = 30;
        System.out.println(a>b & a>c);//10 > 20 & 10 > 30 ==> false & false ==> false
        System.out.println(a<b & a<c);//10 < 20 & 10 < 30 ==> true & true ==> true
        System.out.println(a>b & a<c);//10 > 20 & 10 < 30 ==> false & true ==> false
        System.out.println(a<b & a>c);//10 < 20 & 10 > 30 ==> true & false ==> false

        System.out.println("--------------------");

        System.out.println(a>b | a>c);//10 > 20 | 10 > 30 ==> false | false ==> false
        System.out.println(a<b | a<c);//10 < 20 | 10 < 30 ==> true | true ==> true
        System.out.println(a>b | a<c);//10 > 20 | 10 < 30 ==> false | true ==> true
        System.out.println(a<b | a>c);//10 < 20 | 10 > 30 ==> true | false ==> true

        System.out.println("--------------------");
        System.out.println(a>b ^ a>c);//10 > 20 ^ 10 > 30 ==> false ^ false ==> false
        System.out.println(a<b ^ a<c);//10 < 20 ^ 10 < 30 ==> true ^ true ==> false
        System.out.println(a>b ^ a<c);//10 > 20 ^ 10 < 30 ==> false ^ true ==> true
        System.out.println(a<b ^ a>c);//10 < 20 ^ 10 > 30 ==> true ^ false ==> true
        System.out.println("--------------------");
        System.out.println(!true);//false
        System.out.println(!false);//true
    }
}

```



##### 2.3 逻辑运算符的短路效果

```java
逻辑运算符的短路效果
	1.短路的逻辑运算符
    	(1)短路逻辑与&&: 左侧为false,右边不计算
        (2)短路逻辑或||: 左侧为true,右侧不计算
    2.特点:
        (1)短路逻辑与&&: 和&结果是相同的,但是&&可以提高效率
        (2)短路逻辑与||: 和|结果是相同的,但是||可以提高效率

    3.建议:
        以后开发学习中,全部使用短路与&& 以及 短路或||
```

```java
public class Demo03DuanLu {
    public static void main(String[] args) {
        int a = 2;
        /*
            整个表达式(3>5)&&(++a>2)从左向右计算
            先计算表达式3>5结果为false
            因为两个表达式使用&&连接,左侧为false,已经决定了最终的结果为false,
            不管右侧表达式(++a>2)的结果是true还是false,都无法改变&&的最终结果,
            所以右侧表达式(++a>2)不进行计算
         */
        System.out.println((3>5)&&(++a>2));//false
        System.out.println(a);//2: 说明++a没有计算,&&右侧的表达式没有执行

        int b = 2;
        /*
            整个表达式(3>5)&(++b>2)从左向右计算
            先计算表达式3>5结果为false
            因为两个表达式使用&连接,左侧为false,虽然已经决定了最终的结果为false,
            但是右侧表达式(++b>2)仍然要进行计算,所以b的值最终是3
         */
        System.out.println((3>5)&(++b>2));//false
        System.out.println(b);//3: 说明++b进行计算,&右侧的表达式执行了

        System.out.println("-------------------");
        int c = 2;
        /*
            整个表达式(3<5)||(++c>2)从左向右计算
            先计算表达式3<5结果为true
            因为两个表达式使用||连接,左侧为true,已经决定了最终的结果为true,
            不管右侧表达式(++c>2)的结果是true还是false,都无法改变||的最终结果,
            所以右侧表达式(++c>2)不进行计算
         */
        System.out.println((3<5)||(++c>2));//true
        System.out.println(c);//2: 说明++c没有计算,||右侧的表达式没有执行

        int d = 2;
        /*
            整个表达式(3<5)|(++d>2)从左向右计算
            先计算表达式3<5结果为true
            因为两个表达式使用|连接,左侧为true,虽然已经决定了最终的结果为true,
            但是右侧表达式(++d>2)仍然要进行计算,所以d的值最终是3
         */
        System.out.println((3<5)|(++d>2));//true
        System.out.println(d);//3: 说明++d进行计算,|右侧的表达式执行了
    }
}

```



##### 2.4 三元运算符格式

```java
1.格式:
	数据类型 变量名称 = 布尔表达式1 ? 表达式2 : 表达式3;

2.执行流程:
	(1)计算布尔表达式1的结果,看是true还是false
    (2)如果布尔表达式1的结果为true,就把表达式2的结果赋值给左侧的变量
    (3)如果布尔表达式1的结果为false,就把表达式3的结果赋值给左侧的变量
        
```

##### 执行流程图解:

![image-20200423115658540](img/image-20200423115658540.png)

##### 2.5 三元运算符的练习之两只老虎(相等)

```java
需求：
    动物园里有两只老虎，已知两只老虎的体重分别为180kg、200kg，
    请用程序实现判断两只老虎的体重是否相同。

实现步骤:
	1.定义两个int变量w1和w2,分别代表两只老虎的体重,并按照题目要求进行初始化
	2.使用三元运算符判断w1和w2的值是否相同,保存到boolean变量result中
    3.打印result的值
        
public class Demo01SanYuan {
    public static void main(String[] args) {
        //1.定义两个int变量w1和w2,分别代表两只老虎的体重,并按照题目要求进行初始化
        int w1 = 180, w2 = 200;

        //2.使用三元运算符判断w1和w2的值是否相同,保存到boolean变量result中

        boolean result = (w1 == w2) ? true : false;

        //3.打印result的值
        System.out.println("两只老虎的体重相同吗? "+result);

        System.out.println("---------------");

        String s = (w1 == w2) ? "相同" : "不相同";

        System.out.println("两只老虎的体重相同吗? "+s);
    }
}

```



##### 2.6 三元运算符的练习之两只老虎(最大值)

```java
需求：
    动物园里有两只老虎，已知两只老虎的体重分别为180kg、200kg，
    请用程序实现计算两只老虎的体重的最大值。

实现步骤:
	1.定义两个int变量w1和w2,分别代表两只老虎的体重,并按照题目要求进行初始化
    2.使用三元运算符,计算w1和w2的最大值,把结果保存到int变量max中
    3.打印max的值
public class Demo02SanYuanMax {
    public static void main(String[] args) {
        //1.定义两个int变量w1和w2,分别代表两只老虎的体重,并按照题目要求进行初始化
        int w1 = 180, w2 = 200;

        //2.使用三元运算符,计算w1和w2的最大值,把结果保存到int变量max中

        int max = (w2 > w1) ? w2 : w1;

        //3.打印max的值
        System.out.println("两只老虎体重的最大值: "+max);
    }
}

```

##### 图解分析

![image-20200509140611337](img/image-20200509140611337.png)

##### 2.7 三元运算符的练习之三个和尚

```java
需求：
    一座寺庙里住着三个和尚，已知他们的身高分别为150cm、210cm、165cm，
    请用程序实现获取这三个和尚的最高身高。

实现步骤:
	1.定义3个int变量h1,h2,h3代表三个和尚的身高,并根据题目需求进行初始化
    2.使用三元运算符计算出h1和h2的最大值,保存到int变量temp中
    3.使用三元运算符计算出temp和h3的最大值,保存到int变量max中
    4.最终打印max的值
        
public class Demo03SanYuanMax {
    public static void main(String[] args) {
        //1.定义3个int变量h1,h2,h3代表三个和尚的身高,并根据题目需求进行初始化
        int h1 = 150, h2 = 210, h3 = 165;

        //2.使用三元运算符计算出h1和h2的最大值,保存到int变量temp中
         int temp = (h1 > h2) ? h1 : h2;

        //3.使用三元运算符计算出temp和h3的最大值,保存到int变量max中
        int max = (temp > h3) ? temp : h3;

        //4.最终打印max的值
        System.out.println("三个和尚的最大身高: "+max);//210
    }
}

```

##### 图解分析

![image-20200423142035533](img/image-20200423142035533.png)

### 第三章 数据输入（应用）

##### 3.1 键盘录入的基本使用

```java
数据输出: 把程序运行的结果数据输出到控制台,从而显示到屏幕上
数据输入: 获取用户从键盘上录入的数据到程序当中,然后程序根据业务需求,对获取到的数据进行相关处理

思考1:
	像数据输入这样的操作使用非常频繁,而且实现起来比较复杂,jdk的开发人员已经把此功能实现好了
    jdk中把获取键盘录入数据的功能放到了java.util包的Scanner类中

思考2: 如何使用键盘录入Scanner类呢?
    java中的数据类型: 基本数据类型(四类八种)和引用数据类型(类,接口,数组,枚举...)
    对于引用类型的使用有固定的使用步骤,而键盘录入Scanner类就是一个引用类型,使用也有固定的步骤

键盘录入Scanner的使用,有固定的3个步骤:                    ----固定格式,先记住
	1.导包(找到我们要使用的东西,告诉jvm我们使用的东西在哪里)
		格式:
        	import 包名.类名;
            import java.util.Scanner;

	2.创建对象:
    	格式:
        	类名 对象名 = new 类名(...);
            类名: 就是之前写代码时class关键字后面的名字
            Scanner sc = new Scanner(System.in);
            注意: System.in是固定写法,后面就业班专门讲解

	3.使用:
		sc.nextInt(): 获取键盘录入的整数数字
	4.练习:
		获取键盘录入的一个int数字并输出到控制台
            (1)导包: import java.util.Scanner;
            (2)创建对象: Scanner sc = new Scanner(System.in);
            (3)获取键盘录入的数字: sc.nextInt()

import java.util.Scanner;                
public class Demo01Scanner {
    public static void main(String[] args) {
        //(1)导包: import java.util.Scanner;
        //(2)创建对象: Scanner sc = new Scanner(System.in);
        Scanner sc = new Scanner(System.in);

        //(3)获取键盘录入的数字: sc.nextInt()
        System.out.println("哥们,请您输入一个整数数字: ");
        int num = sc.nextInt();
        System.out.println("您输入的整数数字: "+num);
    }
}
```

##### 键盘录入的理解

![image-20200423144716089](img/image-20200423144716089.png)



##### 3.2 键盘录入的练习

```java
需求：
    获取键盘录入的两个整数(int类型)数字,在控制台输出求和的结果。
    
实现步骤:
	1.导包: import java.util.Scanner
    2.创建键盘录入Scanner类的对象: Scanner sc = new Scanner(System.in)
    3.获取键盘录入的两个整数数字,分别保存到int变量a和b中
    4.计算a和b的和,保存到int变量sum中
    5.打印sum的值	
public class Demo02ScannerSum {
    public static void main(String[] args) {
        //1.导包: import java.util.Scanner
        //2.创建键盘录入Scanner类的对象: Scanner sc = new Scanner(System.in)
        Scanner sc = new Scanner(System.in);

        //3.获取键盘录入的两个整数数字,分别保存到int变量a和b中
        System.out.println("请输入第一个整数数字: ");
        int a = sc.nextInt();

        System.out.println("请输入第二个整数数字: ");
        int b = sc.nextInt();

        System.out.println(a+"...."+b);

        //4.计算a和b的和,保存到int变量sum中
        int sum = a + b;

        //5.打印sum的值
        System.out.println("和: "+sum);
    }
}

```

##### 3.3 键盘录入改写三个和尚案例

```java
需求：
    一座寺庙里住着三个和尚，已知他们的身高分别为150cm、210cm、165cm，身高需要使用键盘录入
    请用程序实现获取这三个和尚的最高身高。
    
实现步骤:
	1.创建键盘录入Scanner类的对象(不用单独先自己写导包)
		(1)写出单词Scanner,然后按alt + / 根据提示选择相应的类 会自动导包
        (2)一边写,根据提示直接选择相应的类,回车会自动导包
    2.获取键盘录入的三个整数数字,分别代表三个和尚的身高,分别保存到int变量h1,h2,h3中
    3.使用三元运算符求出h1和h2的最大身高,保存到int变量temp中
    4.使用三元运算符求出temp和h3的最大身高,保存到int变量max中
    5.打印max的值
import java.util.Scanner;        
public class Demo03ScannerMax {
    public static void main(String[] args) {
        //1.创建键盘录入Scanner类的对象(不用单独先自己写导包)
        Scanner sc = new Scanner(System.in);
        //2.获取键盘录入的三个整数数字,分别代表三个和尚的身高,分别保存到int变量h1,h2,h3中
        System.out.println("请输入第一个和尚的身高(整数数字): ");
        int h1 = sc.nextInt();

        System.out.println("请输入第二个和尚的身高(整数数字): ");
        int h2 = sc.nextInt();

        System.out.println("请输入第三个和尚的身高(整数数字): ");
        int h3 = sc.nextInt();

        System.out.println(h1 + "..." + h2 + "..." + h3);

        //3.使用三元运算符求出h1和h2的最大身高,保存到int变量temp中
        int temp = (h1 > h2) ? h1 : h2;

        //4.使用三元运算符求出temp和h3的最大身高,保存到int变量max中
        int max = (temp>h3) ? temp : h3;

        //5.打印max的值
        System.out.println("三个和尚的最大身高: "+max);
    }
}

```



## 总结

```
能够知道&&和&的区别
	&&: 短路与,左边为flase,右边不进行计算		效率高
	&: 不管左边是true还是false,右边都进行计算		效率低
	
	但是: &&和&的结果是相同的
	
能够使用三元运算符完成获取两个数中较大值
	int a = 10, b = 20;
	int max = (b>a) ? b : a;
	
能够使用键盘录入数据并完成两个数据求和
	导包: import java.util.Scanner;
	创建: Scanner sc = new Scanner(System.in);
	使用:
		int a = sc.nextInt();
		int b = sc.nextInt();
		int sum = a + b;
		sout("sum="+sum);
	
能够使用IDEA完成HelloWorld案例			----必须会
能够知道IDEA的项目结构
能够使用IDEA完成模块的导入
```

