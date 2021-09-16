# day06 【循环跳转、循环嵌套、随机数】

##### 今日复习指南

```java
1.break和continue(0.5个小时内完成,20%的内容搞定)
	(1)Demo02Break.java	测试break的使用
	(2)Demo04Continue.java  测试continue的使用      

2.循环嵌套(半个小时内完成,20%的内容搞定):
	Demo01ForFor.java	测试循环嵌套的执行流程    教练安排运动员跑圈
        
3.随机数(半个小时内完成,20%的内容搞定):
    Demo01Random.java	测试随机数字的基本使用
        
4.猜数字游戏案例(1个小时内完成,40%的内容搞定):
	Demo03GuessNum.java
```



##### 今日内容

```java
跳出语句break，continue【重点】
循环嵌套【理解】
随机数字【重点：死格式】
猜数字案例【重点中的重点】
```

### 第一章 循环跳转【理解】

##### 1.1 break的介绍

```java
break的使用场景:
	1.使用在switch语句中,用来结束switch语句,执行switch语句后面的其它语句
    2.使用在循环中,用来结束循环(1.本次循环的循环体中break后面的代码不再执行 2.剩余次数的循环也不再执行),
		执行循环后面的其它语句
    3.break不能使用在出switch和循环语句以外的其它位置
```

##### 1.2 break的使用

```java
public class Demo01Break {
    public static void main(String[] args) {
        System.out.println("顾客获取到了购买的四个包子..........");
        for (int num = 1; num <= 4; num++) {
            /*
                当num的值为2时,num == 2 --> true,if后面()中是true,执行if后面{}中的内容,
                首先: 执行输出语句
                其次: 执行break,一旦执行break,本次循环的循环体中break后面的代码不再执行,
                剩余次数的循环也不再执行,直接从循环中跳出到循环后面的其它代码继续执行

             */
            if (num == 2) {
                System.out.println("发现2号包子上有个大家伙(小强),2号(及剩余所有)包子不能吃了,找老板投诉");
                break;
            }
            System.out.println("顾客吃第"+num+"个包子......");
        }
        System.out.println("顾客投诉: 这是神马包子,岂有此理.老板: 非常抱歉,赔偿100000元~~~~~");
    }
}
```

##### 图解分析：

![image-20200514092950990](img/image-20200514092950990.png)

##### 1.3 break的练习

```java
public class Demo02Break {
    public static void main(String[] args) {

        for (int i = 1; i <= 10; i++) {
            /*
                当i的值是5的时候, i % 5 == 0 --> 5%5 == 0 --> true,
                if后面()中是true,执行if后面{}中的内容(只有break),
                一旦执行break,本次循环的循环体中break后面的代码不再执行,
                而且剩余次数的循环也不再执行,直接从循环中跳出(结束循环)到循环后面的其它语句
             */
            if (i % 5 == 0) {
                break;
            }
            System.out.println("HelloWorld~~~~~~~~~~~~~~~" + i);
        }
        System.out.println("main....end....");
    }
}
```

##### 图解分析：

![image-20200427094428938](img/image-20200427094428938.png)

##### 1.4 continue的介绍

```java
continue的使用场景:
	1.只能使用在循环中,作用是提前结束本次循环,继续进行下一次循环
    2.不能使用在除循环结构中的其它位置
```



##### 1.5 continue的使用

```java
public class Demo03Continue {
    public static void main(String[] args) {
        System.out.println("顾客获取到了购买的四个包子..........");
        for (int num = 1; num <= 4; num++) {
            /*
                当num的值为2时,num == 2 --> true,if后面()中是true,执行if后面{}中的内容,
                首先: 执行输出语句
                其次: 执行continue,一旦执行continue,本次循环的循环体中continue后面的代码不再执行,
                继续执行下一次循环的步进表达式
                总结: continue的作用提前结束本次循环,继续进行下一次循环

             */
            if (num == 2) {
                System.out.println("把第2个包子弄脏了,不能吃第2个包子了,继续吃其它包子...");
                continue;
            }
            System.out.println("顾客吃第"+num+"个包子......");
        }
        System.out.println("找老板结账,交钱400块,老板说: 欢迎下次光临....");
    }
}
```

##### 图解分析：

![image-20200514100702686](img/image-20200514100702686.png)

##### 1.6 continue的练习

```java
public class Demo04Continue {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            /*
                当i的值是5和10的时候, i % 5 == 0 --> true,
                if后面()中是true,执行if后面{}中的内容(只有continue),
                一旦执行continue,本次循环的循环体中continue后面的代码不再执行,
                继续执行下一次循环的步进表达式
                总结: continue的作用提前结束本次循环,继续进行下一次循环(步进表达式)
             */
            if (i % 5 == 0) {
                continue;
            }
            System.out.println("HelloWorld....." + i);
        }
        System.out.println("main~~~~~~~end~~~~~~~~");
    }

}

```

##### 图解分析：

![image-20200514122234145](img/image-20200514122234145.png)



### 第二章 循环扩展知识点【理解】

##### 2.1 循环嵌套的概念和格式

```java
1.概念: 使用一个循环作为另外一个循环的循环体,外面的循环叫做外层循环,里面的循环叫做内层循环
2.格式(for嵌套):
	for(初始化表达式1;布尔表达式2;步进表达式7){//外层循环
        
        for(初始化表达式3;布尔表达式4;步进表达式6) {//内层循环
            内层循环的循环体5;
        }
        
    }
	其它语句;

3.执行流程:
	1,2(true:外层循环条件) -->
        3,4(true:内层循环条件),5,6 --> 4(true:内层循环条件),5,6 
        --> 直到4(false:内层循环条件),结束内层循环 
    7,2(true:外层循环条件) -->
        3,4(true:内层循环条件),5,6 --> 4(true:内层循环条件),5,6 
        --> 直到4(false:内层循环条件),结束内层循环 
    ...
    直到2(false:外层循环条件),结束外层循环,执行外层循环后面的其它语句
        
```

##### 执行流程图解:

![image-20200427112215139](img/image-20200427112215139.png)

```java
1.需求:
	(1)教练安排运动员跑圈
	(2)教练总共安排3次,每次跑3圈
        
2.问题:
	1.外层循环 int i = 1 执行几次? 1次
    2.内层循环 int j = 1 执行几次? 3次
    3.内层循环的循环体执行几次?
    	外层循环的次数 * 内层循环每遍执行的次数 = 3 * 3 = 9
3.总结:
	外层循环执行1次,内层循环执行完整的(从初始化表达式开始)一遍
	
public class Demo01ForFor {
    public static void main(String[] args) {
        /*
            外层循环第一次: i = 1 i<=3 --> 1<=3 --> true --> 执行外层循环的循环体
                内层循环:
                    j: 1,2,3(3次执行内层循环的输出语句),
                    4 j<=3 --> 4<=3 --> false --> 结束内层循环,执行外层循环的步进表达式i++,i: 2

            外层循环第二次: i = 2 i<=3 --> 2<=3 --> true --> 执行外层循环的循环体
                内层循环:
                    j: 1,2,3(3次执行内层循环的输出语句),
                    4 j<=3 --> 4<=3 --> false --> 结束内层循环,执行外层循环的步进表达式i++,i: 3

            外层循环第三次: i = 3 i<=3 --> 3<=3 --> true --> 执行外层循环的循环体
                内层循环:
                    j: 1,2,3(3次执行内层循环的输出语句),
                    4 j<=3 --> 4<=3 --> false --> 结束内层循环,执行外层循环的步进表达式i++,i: 4

            外层循环第四次: i = 4 i<=3 --> 4<=3 --> false --> 结束外层循环,执行外层循环后面的其它语句

         */
        for(int i = 1;i<=3;i++){//外层循环: 控制趟/遍数
            System.out.println("教练第"+i+"次说: 你给我跑跑3圈");
            for(int j = 1;j<=3;j++){//内层循环: 控制每趟/遍执行的次数
                System.out.println(("           运动员跑第"+i+"次第" + j + "圈"));
            }
        }
        System.out.println("main...end...");
    }
}

```



##### 循环嵌套概念图解:

![image-20200427110457429](img/image-20200427110457429.png)







##### 2.2 循环嵌套打印月份

```java
需求:
	使用嵌套循环，打印2021年至2023年月份，格式：xxxx年x月
/*
    需求:
	    使用嵌套循环，打印2021年至2023年月份，格式：xxxx年x月

	总结:
        外层循环执行1次,内层循环执行完整的(从初始化表达式开始)一遍
 */
public class Demo02ForForMonth {
    public static void main(String[] args) {
        for (int year = 2021; year <= 2023; year++) {//外层循环: 控制年份 2021 2022 2023   3次

            for (int month = 1; month <= 12; month++) {//内层循环: 控制每年的月份,每年都有12个月,都是从1月开始
                //1,2...12: 12次
                System.out.println(year + "年" + month + "月");//执行次数:3*12 = 36次
            }
        }
        System.out.println("main....end....");
    }
}
```

##### 图解分析:

![image-20200427113418654](img/image-20200427113418654.png)

##### 2.3 循环嵌套模拟钟表

```java
需求:
	模拟钟表的时针和分针
	时针(外层循环)走一个格,分钟(内层循环)走一圈
	对应:
	外层循环执行一次,内层循环执行完整的一遍

/*
    需求:
        模拟钟表的时针和分针
        时针(外层循环)走一个格,分钟(内层循环)走一圈
        对应:
        外层循环执行一次,内层循环执行完整的一遍

 */
public class Demo03ForForClock {
    public static void main(String[] args) {

        for (int hour = 0; hour < 24; hour++) {//外层循环: 控制每天都有24小时

            for (int minute = 0; minute < 60; minute++) {//内层循环: 控制每小时都有60分钟

                System.out.println(hour+"点"+minute+"分");

            }
        }

        //System.out.println("main....end...");
    }
}
```

##### 图解分析:

![image-20200427114211716](img/image-20200427114211716.png)

### 第三章 随机数【重点】

##### 3.1 随机数Random的介绍

```java
1.概念:	java.util.Random类就是用来产生随机数字的,也是一种引用类型
2.随机数Random类的使用步骤:
	和Scanner的使用步骤是相同的
    (1)导包(找到我们要使用的东西)
        格式:
			import 包名.类名;
			import java.util.Random;
		快捷键:
			alt + 回车
        注意:
			a.java.lang包下的东西可以直接使用,不用导包
            b.当前类和要使用的类,处于同一个包中,也不用导包
     (2)创建对象
     	类名 对象名 = new 类名(...);
		类名: 之前写代码时,class关键字后面的名称
            
     	创建Scanner类的对象: Scanner sc = new Scanner(System.in);//其中: System.in 是固定写法
			

		创建Random类的对象: Random r = new Random();//其中: ()中什么都不用写,固定格式
     
	(3)使用  
        Scanner中获取键盘录入的整数: int num = sc.nextInt();
		Random中产生随机整数数字:
			r.nextInt(): 产生一个int范围内(正负21亿)的随机数字
			r.nextInt(int类型整数数字n): 产生一个0到n之间的随机数字(包含0,但是不包含n)
				其中: 圆括号()中的int类型整数数字n表示产生随机数字的上限范围
                    
	            
3.练习:
	(1)产生10个int范围内的整数数字
    (2)产生10个0到100之间(包含0,但是不包含100)的整数数字
    (3)产生10个1到100之间(包含1,包含100)的整数数字	
        [1,100] --> [0,99] + 1 --> [0,100) + 1 --> r.nextInt(100) + 1

        思考:
            产生10个66到178之间(包含66,包含178)的整数数字
```

##### 3.2 Random类的使用

```java
练习:
	(1)产生10个int范围内的整数数字
    (2)产生10个0到100之间(包含0,但是不包含100)的整数数字
    (3)产生2个1到5之间(包含1,包含5)的整数数字
    (4)产生10个1到100之间(包含1,包含100)的整数数字	
        
public class Demo01Random {
    public static void main(String[] args) {
        //创建Random类的对象
        Random r = new Random();

        //(1)产生10个int范围内的整数数字
        for (int i = 0; i < 10; i++) {
            //产生1个int范围内的整数数字
            int num = r.nextInt();
            System.out.println(num);
        }
        System.out.println("---------------");

        //(2)产生10个0到100之间(包含0,但是不包含100)的整数数字
        //r.nextInt(100): 产生0到100之间的1个随机数字,但是可以产生0,一定不会产生100(包含0,不包含100) [0,100) <==> [0,99]
        for (int i = 0; i < 10; i++) {
            //产生1个0到100之间(包含0,但是不包含100)的整数数字
            int num = r.nextInt(100);
            System.out.println(num);
        }
        System.out.println("---------------");

        //(3)产生2个1到5之间(包含1,包含5)的整数数字
        /*
            如果可以产生: 0,1,2,3,4           ==>[0,4] ==> [0,5) ==> r.nextInt(5)
            之后:                 +1         r.nextInt(5) + 1
            结果:        1,2,3,4,5
         */
        for (int i = 0; i < 2; i++) {
            //产生1个1到5之间(包含1,包含5)的整数数字
            int num = r.nextInt(5) + 1;
            System.out.println(num);
        }
        System.out.println("---------------");

        //(4)产生10个1到100之间(包含1,包含100)的整数数字
        /*
            先产生0到99的随机数字(包含0,包含99) --> r.nextInt(100)
            +1
            结果是1到100的随机数字(包含1,包含100) --> r.nextInt(100) + 1
         */
        for (int i = 0; i < 10; i++) {
            //产生1个1到100之间(包含1,包含100)的整数数字
            int num = r.nextInt(100) + 1;//[0,99]+1
            System.out.println(num);
        }
        System.out.println("---------------");
        //证明以上代码,确实可以产生1和100
        while(true) {
            //产生1个1到100之间(包含1,包含100)的整数数字
            int num = r.nextInt(100) + 1;//[0,99]+1
            System.out.println(num);
            if (num == 1 || num == 100) {
                break;
            }
        }
    }
}
```

```java
/*
    练习:
        产生10个66到178之间(包含66,包含178)的整数数字
        [66,178] --> [0, 112] + 66 --> [0,113) + 66 --> r.nextInt(113) + 6
 */
public class Demo02Random {
    public static void main(String[] args) {
        //创建Random类的对象
        Random r = new Random();
        //产生10个66到178之间(包含66,包含178)的整数数字
        for (int i = 0; i < 10; i++) {
            //产生1个66到178之间(包含66,包含178)的整数数字
            int num = r.nextInt(113)+66;
            System.out.println(num);
        }
        System.out.println("-------------");
        //证明以上方式,是可以产生最小值66和最大值178的
        while (true) {
            //产生1个66到178之间(包含66,包含178)的整数数字
            int num = r.nextInt(113)+66;
            System.out.println(num);
            if (num == 66 || num == 178) {
                break;
            }
        }
    }
}

```



##### 3.3 Random练习-猜数字

```java
1.需求：程序自动生成一个1-100之间(包含1,包含100)的数字，使用程序实现猜出这个数字是多少？
    
2.效果：
	如果猜的数字比真实数字大，提示你猜的数据大了
	如果猜的数字比真实数字小，提示你猜的数据小了
	如果猜的数字与真实数字相等，提示恭喜你猜中了

3.使用的知识点:
    (1)使用产生随机数字的Random类(1.导包 2.创建对象 3.使用: nextInt(100)+1)
    (2)使用键盘录入Scanner类(1.导包 2.创建对象 3.使用: nextInt())
    (3)使用if语句的第三种格式,比较用户输入的数字和产生的随机数字的大小关系
    (4)用户多少次可以猜对,不确定,需要使用循环(死循环: while(true))
    (5)用户猜测正确后,需要停止循环,使用break  
4.实现步骤:
	(1)创建产生随机数字的Random类的对象
    (2)产生一个[1,100]之间的随机数字,保存到int变量guessNum中,以供用户猜测
    (3)创建键盘录入Scanner类的对象
    (4)以下步骤(5)-(6)是一个循环过程,因为用户多少次可以猜对,并不能确定,使用while(true)
    (5)获取用户猜测的通过键盘录入的数字,保存到int变量inputNum中
    (6)使用if语句的第三种个,对用户猜测的保存在inputNum中的数字 和 产生的保存在guessNum中的数字进行比较
        a.如果 inputNum 大于 guessNum 提示"你猜的数据大了"
        b.否则,如果 inputNum 小于 guessNum 提示"你猜的数据小了"
        c.否则,如果 inputNum 等于 guessNum 提示"恭喜你猜中了",并使用break结束循环
        注意: inputNum 等于 guessNum 条件 省略不写
	
```

##### 图解分析:

![image-20200427143245135](img/image-20200427143245135.png)

##### 实现代码:

```java
public class Demo03GuessNum {
    public static void main(String[] args) {
        //(1)创建产生随机数字的Random类的对象
        Random r = new Random();

        //(2)产生一个[1,100]之间的随机数字,保存到int变量guessNum中,以供用户猜测
        //[1,100] --> [0, 99] + 1 --> [0,100) + 1 --> r.nextInt(100) + 1
        int guessNum = r.nextInt(100) + 1;

        //(3)创建键盘录入Scanner类的对象
        Scanner sc = new Scanner(System.in);
        //(4)以下步骤(5)-(6)是一个循环过程,因为用户多少次可以猜对,并不能确定,使用while(true)
        while (true) {
            //(5)获取用户猜测的通过键盘录入的数字,保存到int变量inputNum中
            System.out.println("请输入您猜测的数字(1-100之间的整数):");
            int inputNum = sc.nextInt();

            //(6)使用if语句的第三种个,对用户猜测的保存在inputNum中的数字 和 产生的保存在guessNum中的数字进行比较
            if (inputNum > guessNum) {
                //a.如果 inputNum 大于 guessNum 提示"你猜的数据大了"
                System.out.println("你猜的数据大了");
            } else if (inputNum < guessNum) {
                //b.否则,如果 inputNum 小于 guessNum 提示"你猜的数据小了"
                System.out.println("你猜的数据小了");
            } else {
                //c.否则,如果 inputNum 等于 guessNum 提示"恭喜你猜中了",并使用break结束循环
                //注意: inputNum 等于 guessNum 条件 省略不写
                System.out.println("恭喜你猜中了");
                //使用break结束循环
                break;
            }
        }

    }
}

```



##### 总结

```java
能够知道循环嵌套的执行流程
    外层循环第一次: i=1 i<=2 --> 1<=2 --> true --> 执行外层循环的循环体(内层循环)
        内层循环:
			j=1,2,3 (执行内层循环的循环体3次),
					4(j<=3 --> 4<=3 --> false: 结束内层for循环),执行外层for循环的步进表达式i++,i变成2
   
    外层循环第二次: i=2 i<=2 --> 2<=2 --> true --> 执行外层循环的循环体(内层循环)
        内层循环:
			j=1,2,3 (执行内层循环的循环体3次),
					4(j<=3 --> 4<=3 --> false: 结束内层for循环),执行外层for循环的步进表达式i++,i变成3
                        
    外层循环第三次: i=3 i<=2 --> 3<=2 --> false --> 结束外层循环,执行外层循环后面的其它语句
    
    for(int i = 1;i<=2;i++) {
        
        for(int j = 1;j<=3;j++) {
            
            sout("i="+i+",j="+j);
            
        }
    }
	其它语句;

能够知道break和continue的作用
    1.break
    	(1)使用在switch语句中,结束switch语句的执行,直接执行switch后面的其它内容
    	(2)使用在循环语句中,结束循环语句的执行,直接执行循环语句后面的其它内容
    		注意: 一旦执行break,本次循环循环体中break后面的代码不再执行,而且剩余次数的循环也不再执行,直接结束(跳出)循环
    	(3)不能使用在除了switch和循环以外的其它地方
    2.continue
        (1)只能使用在循环语句中,提前结束本次循环,继续进行下一次循环
            注意: 一旦执行continue,本次循环循环体中continue后面的代码不再执行,继续执行下一次循环的步进表达式
    
能够完成猜数字小游戏程序
    注意: Random产生随机数字的范围问题
    练习: 产生10个[99,199]范围内的数字(包含99和199)
        0,1,2,3....100
        + 99
        -----------
        99,100,101,102...199
        
        [99,199] --> [0,100] + 99 --> [0,101) + 99 --> r.nextInt(101) + 99
                                       
```

