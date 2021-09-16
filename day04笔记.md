# day04 【选择结构】

##### 今日复习指南

```java
1.if语句(1个小时内完成,80%的内容搞定,switch的重要程度比if要低):
	(1)第一种格式:Demo02If.java
	(2)第二种格式:Demo05IfElseMax.java		获取两个int数字最大值
	(3)第三种格式:Demo03IfElseIfElseScore.java	判断成绩的区间,给出奖励的
        
2.switch语句(半个小时内完成,20%的内容搞定):
	Demo02SwitchMonth.java	练习根据数字判断输出月份
        
```

##### 今日内容

```java
顺序结构【了解】
选择结构之if【重点之重点：应用】
选择结构之switch【重点：应用】

修改类/包的名称:
    1.右键/Refactor/Rename
    2.快捷键: shift + f6
    3.直接修改class关键字后面的名称,alt+回车-->Rename file

创建包/类/模块的快捷键: alt + insert
    有的笔记本电脑insert键位的使用需要按住fn键
    有的笔记本电脑上的insert键被简写成ins
    
自动补全代码: ctrl + shift + 回车
    
向下换行: shift + 回车
    
向上换行: ctrl + alt + 回车
```

## 第一章 流程控制

##### 1.1 流程控制分类

```java
流程：简单来讲所谓流程就是完成一件事情的多个步骤组合起来就叫做一个流程
注意: 在一个程序执行的过程中，各条语句的执行顺序对程序的结果是有直接影响的。
举例：
    结果：正在学习Java编程语言
    流程：学习编程想法 --> 黑马程序员的咨询老师 --> 安排课程 --> 听Java课程	
    
流程控制语句分类
    1.顺序结构: 按照代码的书写顺序,从上而下依次执行
    2.选择/分支结构
        (1)if语句【重点】
        (2)switch语句
    3.循环结构
        (1)for循环【重点】
        (2)while循环
        (3)do-while循环
    
```

##### 1.2 顺序结构

```java
public class Demo01Sequence {
    public static void main(String[] args) {
        //1.顺序结构: 按照代码的书写顺序,从上而下依次执行
        System.out.println("开始.....");
        System.out.println("今天天气不错,我们上午黑马直播java课....A");
        System.out.println("下午还有答疑老师辅导课....B");
        System.out.println("这的确挺爽的....C");
        System.out.println("结束....");
    }
}
```



## 第二章 选择结构-if【重点】

##### 2.1 if语句的第一种格式介绍

```java
英文单词if是: 如果的意思
1.if语句的第一种格式:
	if(布尔表达式){
        语句体;
    }
	其它语句;

2.执行流程:
	(1)使用计算if后面()中布尔表达式的结果,看是true,还是false
    (2)如果if后面()中布尔表达式的结果是true,执行if后面{}中的语句体,接着执行其它语句
    (3)如果if后面()中布尔表达式的结果是false,跳过if后面{}中的语句体,直接执行其它语句
        
3.注意:
	(1)if语句的第一种格式,适用于有一种情况的场景 
    (2)if后面()中表达式不管写的多么简单或者多么复杂,最终的结果一定是布尔类型,要么是true,要么是false
    (3)if后面{}中的语句体,要么执行(布尔表达式结果为true)要么不执行(布尔表达式结果为false)
    (4)if后面{}中的语句体: 一条或者多条语句(每条语句末尾处使用分号结尾)
    (5)if后面{}中的语句体的语句体只有一条语句,此时{}可以省略,但是初学者讲义保留    
      
```

##### 图解:

![image-20200424093139471](img/image-20200424093139471.png)

##### 2.2 if语句的第一种格式练习

```java
练习
	需求1：判断a和b的值是否相等，如果相等，就在控制台输出：a等于b
	需求2：判断a和c的值是否相等，如果相等，就在控制台输出：a等于c
public class Demo02If {
    public static void main(String[] args) {
        //需求1：判断a和b的值是否相等，如果相等，就在控制台输出：a等于b
        int a = 10, b = 20;
        if (a == b) {//10 == 20: false,不执行{}中的语句体
            System.out.println(a + "等于" + b);
        }

        if (a != b) {//10 != 20: true,执行{}中的语句体
            System.out.println(a + "不等于" + b);
        }

        //需求2：判断a和c的值是否相等，如果相等，就在控制台输出：a等于c
        int c = 30;
        if (a == c) {//10 == 30: false,不执行{}中的语句体
            System.out.println(a + "等于" + c);
        }

        if(a != c) {//10 != 30: true,执行{}中的语句体
            System.out.println(a + "不等于" + c);
        }
        System.out.println("main....end....");//模拟格式中的其它语句
    }
}
```



##### 2.3 if语句的第二种格式介绍

```java
英文单词if是: 如果的意思
英文单词else是: 否则的意思
1.if语句的第二种格式:
	if(布尔表达式){
        语句体1;
    } else {
        语句体2;
    }
	其它语句;

2.执行流程:
	(1)使用计算if后面()中布尔表达式的结果,看是true,还是false
    (2)如果if后面()中布尔表达式的结果是true,执行if后面{}中的语句体1,接着执行其它语句
    (3)如果if后面()中布尔表达式的结果是false,执行else后面{}中的语句体2,接着执行其它语句
        
3.注意:
	(1)if语句的第二种格式,适用于有两种情况的场景 
    (2)if后面()中表达式不管写的多么简单或者多么复杂,最终的结果一定是布尔类型,要么是true,要么是false
    (3)语句体1和语句体2,只有一个会被执行
    (4)适用于二选一的场景(是与否的场景)
        
```

##### 图解:

![image-20200424095214017](img/image-20200424095214017.png)

##### 2.4 if语句的第二种格式练习判断大小

```java
需求：
    判断a是否大于b，如果是，在控制台输出：a的值大于b，否则，在控制台输出：a的值不大于b
    
实现步骤:
	1.定义2个int变量a和b,并分别初始化
	2.a和b的大小关系有两种情况,所以使用if-else语句对a和b的值进行判断,并输出不同的结果
        
public class Demo03IfElse {
    public static void main(String[] args) {
        //1.定义2个int变量a和b,并分别初始化
        int a = 10, b = 20;

        //2.a和b的大小关系有两种情况,所以使用if-else语句对a和b的值进行判断,并输出不同的结果
        if (a > b) {//10 > 20: false,执行else后面{}中的语句体
            System.out.println(a + "的值大于" + b);
        } else {
            System.out.println(a + "的值不大于" + b);
        }
        System.out.println("main....end....");//模拟格式中的其它语句
    }
}
 
```

##### 2.5 if语句的第二种格式练习判断奇偶数

```java
需求：
    任意给出一个整数，请用程序实现判断该整数是奇数还是偶数，并在控制台输出该整数是奇数还是偶数。
    
实现步骤:
	1.创建键盘录入Scanner类的对象
    (1.导包: import java.util.Scanner; 2.创建对象: Scanner sc = new Scanner(System.in);)
    2.获取键盘录入的整数数字,保存到int变量num中
    3.使用if语句的第二种格式(if-else),判断num中的数字,输出对应的奇偶数情况
        num%2==0: 说明num中的数字是偶数
        num%2!=0: 说明num中的数字是奇数
            
public class Demo04IfElseJiOu {
    public static void main(String[] args) {
        //1.创建键盘录入Scanner类的对象
        //(1.导包: import java.util.Scanner; 2.创建对象: Scanner sc = new Scanner(System.in);)
        Scanner sc = new Scanner(System.in);

        //2.获取键盘录入的整数数字,保存到int变量num中
        System.out.println("请输入一个整数数字: ");
        int num = sc.nextInt();
        //System.out.println("您输入的整数是: "+num);

        //3.使用if语句的第二种格式(if-else),判断num中的数字,输出对应的奇偶数情况
        /*if(num%2==0){
            System.out.println(num+"是一个偶数数字");
        } else {
            System.out.println(num+"是一个奇数数字");
        }*/

        if(num%2!=0){
            System.out.println(num+"是一个奇数数字");
        } else {
            System.out.println(num+"是一个偶数数字");
        }


        System.out.println("main....end....");//模拟格式中的其它语句

    }
}

```

```java
需求：
    任意给出两个整数，请用程序实现求出两个整数的最大值,并输出到控制台。
    
实现步骤:
	1.创建键盘录入Scanner类的对象
    2.获取两个键盘录入的整数数字,分别保存到2个int变量a和b中
    3.定义int变量max,作用是用来保存两个int数字的最大值
    4.使用if-else对a和b中的值进行大小判断
    	4.1如果: a>b 是成立的,说明a是最大的,把a的值赋值给变量max
        4.2否则: a>b 是不成立的,说明b是最大的,把b的值赋值给变量max
    5.打印max的值
            
import java.util.Scanner;            
public class Demo05IfElseMax {
    public static void main(String[] args) {

        //1.创建键盘录入Scanner类的对象
        Scanner sc = new Scanner(System.in);

        //2.获取两个键盘录入的整数数字,分别保存到2个int变量a和b中
        System.out.println("请输入第一个整数数字: ");
        int a = sc.nextInt();

        System.out.println("请输入第二个整数数字: ");
        int b = sc.nextInt();

        //3.定义int变量max,作用是用来保存两个int数字的最大值
        int max;

        //4.使用if-else对a和b中的值进行大小判断
        if(a>b) {//10 > 20 ==> false
            //4.1如果: a>b 是成立的,说明a是最大的,把a的值赋值给变量max
            max = a;
        } else {
            //4.2否则: a>b 是不成立的,说明b是最大的,把b的值赋值给变量max
            max = b;
        }
        //5.打印max的值
        //System.out.println("数字 "+a+"和"+b+"的最大值是: "+max);
        System.out.println("最大值: "+max);

        System.out.println("main....end....");//模拟格式中的其它语句
    }
}

```

##### 图解分析:

![image-20200424103803810](img/image-20200424103803810.png)

##### 2.6 if语句的第三种格式介绍

```java
英文单词if是: 如果的意思
英文单词else是: 否则的意思
1.if语句的第三种格式:
	if (布尔表达式1) { 
        语句体1; 
    } else if (布尔表达式2) { 
        语句体2; 
    }
	…else if (布尔表达式n) {
        语句体n; 
    } else { 
        语句体n+1; 
    }
	其它语句;

2.执行流程:
	(1)首先计算布尔表达式1的值
	(2)如果值为true就执行语句体1；如果值为false就计算布尔表达式2的值
	(3)如果值为true就执行语句体2；如果值为false就计算布尔表达式3的值
	(4)…
	(5)如果没有任何布尔表达式为true，就执行语句体n+1。	

3.注意:
	(1)if语句的第三种格式,适用于有多种情况(大于等于3)的场景 
    (2)if后面()中表达式不管写的多么简单或者多么复杂,最终的结果一定是布尔类型,要么是true,要么是false
    (3)语句体1到语句体n+1,只有一个会被执行
    (4)适用于多选一的场景
    (5)有if就可以在后面写条件,没有if,不能写条件,不能直接在else后面写条件
    (6)最后一个else后面没有if,是用来兜底的,如果上面所有if后的条件都不成立,直接执行最后一个else中的代码

```

图解:

![image-20200424111252158](img/image-20200424111252158.png)

##### 2.7 if语句的第三种格式练习根据数字输出对应的星期

```java
需求:
	键盘录入一个星期数(1,2,...7)，输出对应的星期一，星期二，...星期日
演示效果:
	输入 1 输出 星期一
    输入 2 输出 星期二
    输入 3 输出 星期三 
    输入 4 输出 星期四 
    输入 5 输出 星期五 
    输入 6 输出 星期六 
    输入 7 输出 星期日 
    输入 其它数字 输出 数字有误
        
实现步骤:
	1.创建键盘录入Scanner类的对象
	2.获取键盘录入的整数数字,代表星期数,保存到int变量week中
	3.因为week中的数字有7+1种情况,所以使用if语句的第三种格式进行判断,并输出不同的结果内容

import java.util.Scanner;
public class Demo01IfElseIfElseWeek {
    public static void main(String[] args) {
        //1.创建键盘录入Scanner类的对象
        Scanner sc = new Scanner(System.in);

        //2.获取键盘录入的整数数字,代表星期数,保存到int变量week中
        System.out.println("请输入一个1-7的整数数字(代表星期数):");
        int week = sc.nextInt();

        //3.因为week中的数字有7+1种情况,所以使用if语句的第三种格式进行判断,并输出不同的结果内容
        if(week == 1) {
            System.out.println("星期一");
        } else if(week == 2) {
            System.out.println("星期二");
        } else if(week == 3) {
            System.out.println("星期三");
        } else if(week == 4) {
            System.out.println("星期四");
        } else if(week == 5) {
            System.out.println("星期五");
        } else if(week == 6) {
            System.out.println("星期六");
        } else if(week == 7) {
            System.out.println("星期日");
        } else {//隐藏条件: week>7 || week<1
            System.out.println("您输入的星期数不存在,是火星来的吧,哥屋恩...");
        }

        System.out.println("main....end....");//模拟格式中的其它语句
    }
}

import java.util.Scanner;
public class Demo02IfElseIfElseWeek {
    public static void main(String[] args) {
        //1.创建键盘录入Scanner类的对象
        Scanner sc = new Scanner(System.in);

        //2.获取键盘录入的整数数字,代表星期数,保存到int变量week中
        System.out.println("请输入一个1-7的整数数字(代表星期数):");
        int week = sc.nextInt();

        //3.因为week中的数字有7+1种情况,所以使用if语句的第三种格式进行判断,并输出不同的结果内容
        if(week>7 || week<1) {
            System.out.println("您输入的星期数不存在,是火星来的吧,哥屋恩...");
        } else if(week == 1) { //从这里开始向下,隐藏条件: week>=1 && week<=7
            System.out.println("星期一");
        } else if(week == 2) {
            System.out.println("星期二");
        } else if(week == 3) {
            System.out.println("星期三");
        } else if(week == 4) {
            System.out.println("星期四");
        } else if(week == 5) {
            System.out.println("星期五");
        } else if(week == 6) {
            System.out.println("星期六");
        } else /*if(week == 7)*/ {//隐藏条件: week == 7
            System.out.println("星期日");
        }

        System.out.println("main....end....");//模拟格式中的其它语句
    }
}

```



##### 2.8 if语句的第三种格式练习根据成绩进行奖励

```java
需求：
    小明快要期末考试了，小明爸爸对他说，会根据他不同的考试成绩，送他不同的礼物，
    假如你可以控制小明的得分，请用程序实现小明到底该获得什么样的礼物，并在控制台输出。
    
奖励规则:
	95~100 山地自行车一辆 		包含95和100的	数学中表示方式: [95,100]  不包含95和100: (95,100)
    90~94  游乐场玩一次 		 包含90和94的
    80~89  变形金刚玩具一个     包含80和89的
    80以下  胖揍一顿 			 不包含80分的
        
实现步骤:
	1.创建键盘录入Scanner类的对象
    2.获取一个0-100之间的整数数字(代表小明的考试成绩),保存到int变量score中
    3.因为score中的数字有多种(大于3)情况,所以使用if语句的第三种格式进行判断,并输出不同的结果内容
import java.util.Scanner;
public class Demo03IfElseIfElseScore {
    public static void main(String[] args) {
        //1.创建键盘录入Scanner类的对象
        Scanner sc = new Scanner(System.in);

        //2.获取一个0-100之间的整数数字(代表小明的考试成绩),保存到int变量score中
        System.out.println("请输入一个0-100之间的整数数字(代表小明的考试成绩): ");
        int score = sc.nextInt();

        //3.因为score中的数字有多种(大于3)情况,所以使用if语句的第三种格式进行判断,并输出不同的结果内容
        if(score>=95 && score<=100) {
            System.out.println("奖励山地自行车一辆");
        } else if(score>=90 && score<=94) {
            System.out.println("奖励游乐场玩一次");
        } else if(score>=80 && score<=89) {
            System.out.println("奖励变形金刚玩具一个");
        } else if(score>=0 && score<80){
            System.out.println("奖励胖揍一顿");
        } else /*if(score<0 || score>100)*/{//隐藏条件: score<0 || score>100
            System.out.println("您输入的成绩错误,是火星来的吧,哥屋恩...");
        }

        System.out.println("main....end....");//模拟格式中的其它语句
    }
}

import java.util.Scanner;
public class Demo04IfElseIfElseScore {
    public static void main(String[] args) {
        //1.创建键盘录入Scanner类的对象
        Scanner sc = new Scanner(System.in);

        //2.获取一个0-100之间的整数数字(代表小明的考试成绩),保存到int变量score中
        System.out.println("请输入一个0-100之间的整数数字(代表小明的考试成绩): ");
        int score = sc.nextInt();

        //3.因为score中的数字有多种(大于3)情况,所以使用if语句的第三种格式进行判断,并输出不同的结果内容
        //先排除非法数据
        if(score<0 || score>100) {
            System.out.println("您输入的成绩错误,是火星来的吧,哥屋恩...");
        } else if(score>=95 && score<=100) {//执行到这里及以下: score>=0 && score<=100
            System.out.println("奖励山地自行车一辆");
        } else if(score>=90 && score<=94) {
            System.out.println("奖励游乐场玩一次");
        } else if(score>=80 && score<=89) {
            System.out.println("奖励变形金刚玩具一个");
        } else /*if(score>=0 && score<80)*/{//隐藏条件: score>=0 && score<80)
            System.out.println("奖励胖揍一顿");
        }

        System.out.println("main....end....");//模拟格式中的其它语句
    }
}
```



##### 图解:

![image-20200424121125368](img/image-20200424121125368.png)

## 第三章 选择结构-switch【重点】

##### 3.1 switch语句格式和介绍

```java
1.switch语句的格式:
	switch(表达式) {
    	case 常量值1;
            语句体1;
            break;
        case 常量值2;
            语句体2;
            break;
        ...
        case 常量值n;
            语句体n;
            break;
        default:
            语句体n+1;
            break;
    }
	其它语句;

2.执行流程:
	首先计算出表达式的值
	其次，和case依次比较，一旦有对应的值，就会执行相应的语句，在执行的过程中，遇到break就会结束。
	最后，如果所有的case都和表达式的值不匹配，就会执行default语句体部分，然后程序结束掉。

3.注意事项:
	(1)break的作用是用来结束switch语句的,一旦执行break,直接跳出到switch外面的其它语句继续执行
	(2)switch后面()中的表达式的数据类型,只能是以下几种类型:
		基本类型: byte/short/char/int 都可以   -----------------重要,选择题经常考到---------------
        引用类型: String或者枚举
	(3)case 后面只能写常量,而且常量值不能重复
	(4)最后一个default的作用:
		用来兜底的,如果所有的case后面的常量值和switch中表达式的值都不相同,就执行default中的内容
	(5)如果default放在最后的话: 后面的break可以省略
	(6)如果所有的case和default后面都有break,那么default和case的顺序可以任意排列,不影响最终的结果
public class Demo01Switch {
    public static void main(String[] args) {
        int choose = 2;
        switch (choose) {//30

            case 1:
                System.out.println("你好~~~~~");
                break;

            case 2:
                System.out.println("我好~~~~~");
                break;

            case 3:
                System.out.println("大家好,才是真的好~~~~~");
                break;

            default:
                System.out.println("他好,我也好~~~~");
                break;
        }
        System.out.println("main....end....");//模拟格式中的其它语句
    }
}
        

```

##### 执行流程

![image-20200424141613697](img/image-20200424141613697.png)

##### 3.2 switch练习根据月份输出对应的季节

```java
需求：
    一年有12个月，分属于春夏秋冬4个季节，
    键盘录入一个月份，请用程序实现判断该月份属于哪个季节，并输出。

演示效果
	输入： 1、2、12 输出：冬季
	输入： 3、4、5 输出：春季
	输入： 6、7、8 输出：夏季
	输入： 9、10、11 输出：秋季
	输入： 其它数字 输出：数字有误

实现步骤(本案例使用switch):
	1.创建键盘录入Scanner类的对象
	2.获取键盘录入的一个1-12的整数数字(代表月份),保存到int变量month中
    3.因为month中的数字有12+1中情况,使用switch语句对month中的值,进行判断,并输出不同的结果
public class Demo02SwitchMonth {
    public static void main(String[] args) {
        //1.创建键盘录入Scanner类的对象
        Scanner sc = new Scanner(System.in);

        //2.获取键盘录入的一个1-12的整数数字(代表月份),保存到int变量month中
        System.out.println("请输入一个1-12的整数数字(代表月份): ");
        int month = sc.nextInt();

        //3.因为month中的数字有12+1中情况,使用switch语句对month中的值,进行判断,并输出不同的结果
        switch (month) {//15
            case 1:
                System.out.println("冬季");
                break;
            case 2:
                System.out.println("冬季");
                break;
            case 12:
                System.out.println("冬季");
                break;
            case 3:
                System.out.println("春季");
                break;
            case 4:
                System.out.println("春季");
                break;
            case 5:
                System.out.println("春季");
                break;
            case 6:
                System.out.println("夏季");
                break;
            case 7:
                System.out.println("夏季");
                break;
            case 8:
                System.out.println("夏季");
                break;
            case 9:
                System.out.println("秋季");
                break;
            case 10:
                System.out.println("秋季");
                break;
            case 11:
                System.out.println("秋季");
                break;
            default:
                System.out.println("您输入的月份不存在,哪个星球来的,哥屋恩...");
                break;
        }
        System.out.println("main....end....");//模拟格式中的其它语句
    }
}

```



##### 3.3 使用case穿透优化根据月份输出对应的季节的案例

```java
使用case穿透优化根据月份输出对应的季节的案例
	发现问题:
    	前面Demo02SwitchMonth.java文件中出现了大量的重复的代码
        1,2,12代码重复,3,4,5代码重复,6,7,8代码重复,9,10,11代码重复
        每三个case中的代码都是相同的

解决方案使用case穿透:
	如果多个连续的case中具有相同的代码和break,可以只保留最后一个case中的代码和break,
    前面的多个case中省略掉代码和break(只保留case)

    在switch语句中，如果case的后面不写break，将出现穿透现象，
    也就是不会在判断下一个case的值，直接向后运行，直到遇到break，或者整体switch结束。

执行步骤:
	1.先找到case入口: 先找到常量值和switch表达式值相同的case
    2.执行找到的case入口中的代码:
    	如果没有break,直接执行(不再判断下一个case中的常量值是否和switch表达式的值是否相同)下一个case中的代码,
        直到遇到break,结束switch语句
public class Demo03SwitchMonth {
    public static void main(String[] args) {
        //1.创建键盘录入Scanner类的对象
        Scanner sc = new Scanner(System.in);

        //2.获取键盘录入的一个1-12的整数数字(代表月份),保存到int变量month中
        System.out.println("请输入一个1-12的整数数字(代表月份): ");
        int month = sc.nextInt();

        //3.因为month中的数字有12+1中情况,使用switch语句对month中的值,进行判断,并输出不同的结果
        switch (month) {//9
            case 1:
            case 2:
            case 12:
                System.out.println("冬季");
                break;
            case 3:
            case 4:
            case 5:
                System.out.println("春季");
                break;
            case 6:
            case 7:
            case 8:
                System.out.println("夏季");
                break;
            case 9:
            case 10:
            case 11:
                System.out.println("秋季");
                break;
            default:
                System.out.println("您输入的月份不存在,哪个星球来的,哥屋恩...");
                break;
        }
        System.out.println("main....end....");//模拟格式中的其它语句
    }
}
```



## 总结

```java
能够使用if语句完成获取两个数中较大值
    int a = 10,b = 20;
	int max;//作用用来保存较大值的
	if(a>b) {
       max = a; 
    } else {//a<=b: 说明b是较大的
       max = b;
    }
	sout(max);

能够使用if语句完成根据分数输出对应级别
    举例:
		[95,100] 	"卓越"
        [90,95)		"优秀"
        [80,90)		"良好"
        [70,80)		"一般"
        [60,70)		"及格"
        [0,60)		"不及格"
        其它情况	 "数字错误"
    int score = 95; 
    if(score>=95 && score<=100) {
        sout("卓越");
    } else if(score>=90 && score<95) {
        sout("优秀");
    } else if(score>=80 && score<90) {
        sout("良好");
    } else if(score>=70 && score<80) {
        sout("一般");
    } else if(score>=60 && score<70) {
        sout("及格");
    } else if(score>=0 && score<60) {
        sout("不及格");
    } else {
        sout("数字错误");
    }
         
能够使用switch语句完成根据月份输出对应季节
    int month = 5;
    switch(month) {
        case 1:
        	sout("冬季");
        	break;
        case 2:
        	sout("冬季");
        	break;
        case 12:
        	sout("冬季");
        	break;
        ...
        default:
        	sout("数字错误");
        	break;
    }     
```

