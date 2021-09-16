# day05 【循环语句】

##### 今日复习指南

```java
1.for循环(1.5个小时内完成,80%的内容搞定,while的重要程度比for要低)
	(1)Demo03ForSum5.java				求1-5的数字之和
    (2)Demo07CountSXH.java        		打印并统计所有的水仙花数字及个数	
2.while语句(半个小时内完成,20%的内容搞定):
	(1)Demo02WhileZFCount.java			珠穆拉玛峰案例
3.其它知识(15分钟)
    (1)循环区别
    (2)死循环
```

##### 今日内容

```java
循环的概念和组成【理解】
for循环语句【重点中的重点】
while循环语句【重点】
do while循环语句【了解】
```

### 第一章 循环结构【理解】

##### 1.1 循环概述

```java
圆周率: 无限不循环小数 3.1415926...
10除以3的结果: 3.33333... 无限循环小数

循环的概念: 重复性的执行某些固定的功能,当条件不成立时,结束循环
说白了: 条件成立执行操作,条件不成立停止操作
```

##### 1.2 循环组成

```java
1.循环的组成(手写100遍HelloWorld案例): :
	(1)【初始化表达式1】准备工作:笔墨伺候,最优先唯一执行一次的操作
	(2)【循环条件2】条件判断:每次书写前,判断一下,要不要写
    (3)【循环体3】循环所要进行的操作:手写一个HelloWorld案例 
	(4)【步进表达式4】扫尾的工作:每写一次HelloWorld,计数(+1)

2.执行流程:
	1,2(循环条件: true),3,4 --> 2(循环条件: true),3,4 --> ... --> 
        直到布尔表达式2(循环条件: false),结束循环,执行循环后面的其它语句

3.循环的分类:
	(1)for循环【最最常用】
    (2)while循环【一般常用】
    (3)do-while循环【不常用】
```

### 第二章 循环语句1--for【必须掌握】

##### 2.1 **for循环语句介绍**

```java
1.for循环格式:
	for(初始化表达式1;布尔表达式2;步进表达式4){
        循环体3;
    }

2.执行流程:
	1,2(循环条件: true),3,4 --> 2(循环条件: true),3,4 --> ... --> 
        直到布尔表达式2(循环条件: false),结束循环,执行循环后面的其它语句
        
```

##### 图解分析：

![image-20200426093440701](img/image-20200426093440701.png)



##### 2.2 for循环练习1

```java
需求:
	在控制台输出5次HelloWorld 
public class Demo01ForHello {
    public static void main(String[] args) {
        System.out.println("HelloWorld.....1");
        System.out.println("HelloWorld.....2");
        System.out.println("HelloWorld.....3");
        System.out.println("HelloWorld.....4");
        System.out.println("HelloWorld.....5");
        System.out.println("----------------------");

        //使用for循环
        //count: 1,2,3,4,5  6<=5 --> false --> 结束for循环
        for (int count = 1; count <= 5; count++) {
            System.out.println("HelloWorld....."+count);
        }
        System.out.println("----------------------");

        //使用for循环
        //times: 0,1,2,3,4    5<5 --> false --> 结束for循环
        for (int times = 0; times < 5; times++) {
            System.out.println("HelloWorld....."+times);
        }

        System.out.println("main.......end............");
    }
}

```

##### 2.3 for循环练习2

```java
需求:
	在控制台输出1-5和5-1的数据
        
public class Demo02ForPrint5 {
    public static void main(String[] args) {
        //for循环输出1-5
        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
        }
        System.out.println("----------");

        //for循环输出5-1
        for (int j = 5; j >= 1; j--) {
            System.out.println(j);
        }

        System.out.println("main....end....");
    }
}

```

##### 2.4 for循环练习3

```java
需求:
	求1-5之间的数据和，并把求和结果在控制台输出
        
实现步骤:
	1.定义int变量sum,用来求和,初始值0
	2.使用for循环获取1-5的数字
	2.1把当前数字累加到求和变量中
	3.打印求和变量sum
        
public class Demo03ForSum5 {
    public static void main(String[] args) {

        //1.定义int变量sum,用来求和,初始值0
        int sum = 0;

        /*
            第一次: sum = 0   i = 1
                 i <= 5 --> 1<=5 --> true --> sum = sum + i = 0 + 1 = 1  i = 2

            第二次: sum = 1   i = 2
                i <= 5 --> 2<=5 --> true --> sum = sum + i = 1 + 2 = 3  i = 3

            第三次: sum = 3   i = 3
                i <= 5 --> 3<=5 --> true --> sum = sum + i = 3 + 3 = 6  i = 4

            第四次: sum = 6   i = 4
                i <= 5 --> 4<=5 --> true --> sum = sum + i = 6 + 4 = 10  i = 5

            第五次: sum = 10   i = 5
                i <= 5 --> 5<=5 --> true --> sum = sum + i = 10 + 5 = 15  i = 6

            第六次: sum = 15   i = 6
                i <= 5 --> 6<=5 --> false --> 结束for循环,执行for后面的代码
         */

        //2.使用for循环获取1-5的数字
        for (int i = 1; i <= 5; i++) {
            //2.1把当前数字累加到求和变量sum中
            sum = sum + i;
        }

        //3.打印求和变量sum
        System.out.println("1-5的数字之和: "+sum);
    }
}

```

图解分析:

![image-20200426102848056](img/image-20200426102848056.png)



##### 2.5 for循环练习4

```java
需求:
	求1-100之间的偶数和，并把求和结果在控制台输出
        
实现步骤:
	1.定义int变量sum,用来累加求和,初始值0
    2.使用for获取1-100之间的数字
    2.1判断如果当前数字是偶数,把当前数字累加到求和变量sum中
    3.for循环结束,打印求和变量sum的值
        
public class Demo04ForSum100 {
    public static void main(String[] args) {
        //1.定义int变量sum,用来累加求和,初始值0
        int sum = 0;

        //2.使用for获取1-100之间的数字
        for (int i = 1; i <= 100; i++) {
            //2.1判断如果当前数字是偶数
            if (i % 2 == 0) {
                //把当前数字累加到求和变量sum中
                sum += i;
            }
        }
        //3.for循环结束,打印求和变量sum的值
        System.out.println("1-100之间的偶数数字之和: "+sum);
        System.out.println("-------------");

        //1.定义int变量sum2,用来累加求和,初始值0
        int sum2 = 0;

        //2.使用for获取1-100之间的偶数数字
        for (int j = 0; j <= 100; j++,j++/*j+=2*/) {
            //2.1把当前数字(偶数)累加到求和变量sum2中
            //System.out.println(j);
            sum2 += j;
        }
        //3.for循环结束,打印求和变量sum的值
        System.out.println("1-100之间的偶数数字之和: "+sum2);

    }
}
	
```



##### 2.6 for循环练习5

```java
需求:
	键盘录入一个三位数字,输出该数字是否是水仙花数字?
        
解释：什么是水仙花数？
	水仙花数，指的是一个三位数[100,999]，个位、十位、百位的数字立方和等于原数
	例如 153 3*3*3 + 5*5*5 + 1*1*1 = 27 + 125 + 1 = 153
        
实现步骤:
	1.创建键盘录入Scanner类的对象(1.导包 2.创建)
    2.获取键盘录入的一个三位整数数字,保存到int变量num中
    3.使用if判断如果num中的数字是三位数字
        3.1 计算num的个位,十位,百位 分别保存到3个int变量ge(个位),shi(十位),bai(百位)中
        3.2 计算个位,十位,百位数字的立方和,保存到int变量sum中
        3.3 判断如果三位数字num 等于 每位数字的立方和sum,输出num是一个水仙花数字
        3.4 判断如果三位数字num 不等于 每位数字的立方和sum,输出num不是一个水仙花数字
    4.如果num中的数字不是三位数字,提示"你输入的不是三位数字,所以不可能是水仙花数字"
        
public class Demo05ISSXH {
    public static void main(String[] args) {
        //1.创建键盘录入Scanner类的对象(1.导包 2.创建)
        Scanner sc = new Scanner(System.in);

        //2.获取键盘录入的一个三位整数数字,保存到int变量num中
        System.out.println("请录入一个三位整数数字: ");
        int num = sc.nextInt();

        //3.使用if判断如果num中的数字是三位数字
        if (num >= 100 && num <= 999) {
            //3.1 计算num的个位,十位,百位 分别保存到3个int变量ge(个位),shi(十位),bai(百位)中
            int ge = num%10;//个位
            int shi = num/10%10;//十位
            int bai = num/100%10;//百位

            System.out.println("个位: "+ge);
            System.out.println("十位: "+shi);
            System.out.println("百位: "+bai);

            //3.2 计算个位,十位,百位数字的立方和,保存到int变量sum中
            int sum = ge*ge*ge + shi*shi*shi + bai*bai*bai;

            //3.3 判断如果三位数字num 等于 每位数字的立方和sum,输出num是一个水仙花数字
            if(sum == num) {
                System.out.println(num+"是一个水仙花数字....");
            } else {
                //3.4 判断如果三位数字num 不等于 每位数字的立方和sum,输出num不是一个水仙花数字
                System.out.println(num+"不是一个水仙花数字....");
            }

        } else {
            //4.如果num中的数字不是三位数字,提示"你输入的不是三位数字,所以不可能是水仙花数字"
            System.out.println("你输入的不是三位数字,所以不可能是水仙花数字....哥屋恩....");
        }
    }
}
        
```

##### 2.7 for循环练习6

```java
需求:
	在控制台输出所有的“水仙花数”
        
解释：什么是水仙花数？
	水仙花数，指的是一个三位数，个位、十位、百位的数字立方和等于原数
	例如 153 3*3*3 + 5*5*5 + 1*1*1 = 27 + 125 + 1 = 153
        
实现步骤:
	1.使用for循环获取所有的三位数字,每个数字保存到int变量num中
    	1.1计算num中数字的个位,十位,百位 分别保存到3个int变量ge(个位),shi(十位),bai(百位)中
        1.2计算个位,十位,百位数字的立方和,保存到int变量sum中
        1.3判断如果三位数字num 等于 每位数字的立方和sum,输出该数字num

public class Demo06PrintSXH {
    public static void main(String[] args) {
        //1.使用for循环获取所有的三位数字,每个数字保存到int变量num中
        for (int num = 100; num <= 999; num++) {

            //1.1计算num中数字的个位,十位,百位 分别保存到3个int变量ge(个位),shi(十位),bai(百位)中
            //123
            int ge = num%10;//个位
            int shi = num/10%10;//十位
            int bai = num/100%10;//百位

            //1.2计算个位,十位,百位数字的立方和,保存到int变量sum中
            int sum = ge*ge*ge + shi*shi*shi + bai*bai*bai;
            //1.3判断如果三位数字num 等于 每位数字的立方和sum,输出该数字num
            if(sum == num) {
                System.out.println(num);
            }
        }
    }
}

```

##### 2.8 for循环练习7

```java
需求:
	在控制台输出所有的“水仙花数”及总个数
        
解释：什么是水仙花数？
	水仙花数，指的是一个三位数，个位、十位、百位的数字立方和等于原数
	例如 153 3*3*3 + 5*5*5 + 1*1*1 = 27 + 125 + 1 = 153
        
实现步骤:
	1.定义int变量count,初始值0,作用是统计水仙花数字的个数
    2.使用for循环遍历获取所有的三位数字,每个数字保存到int变量num中
    2.1计算num中数字的个位,十位,百位 分别保存到3个int变量ge(个位),shi(十位),bai(百位)中
    2.2计算个位,十位,百位数字的立方和,保存到int变量sum中
    2.3判断如果三位数字num 等于 每位数字的立方和sum,输出该数字num,同时计数器count的值增加1
    3.for循环结束后,打印count的值
        
public class Demo07CountSXH {
    public static void main(String[] args) {
        //1.定义int变量count,初始值0,作用是统计水仙花数字的个数
        int count = 0;

        //2.使用for循环遍历获取所有的三位数字,每个数字保存到int变量num中
        for (int num = 100; num <= 999; num++) {
            //2.1计算num中数字的个位,十位,百位 分别保存到3个int变量ge(个位),shi(十位),bai(百位)中
            int ge = num%10;//个位
            int shi = num/10%10;//十位
            int bai = num/100%10;//百位
            //2.2计算个位,十位,百位数字的立方和,保存到int变量sum中
            //2.3判断如果三位数字num 等于 每位数字的立方和sum
            if((ge*ge*ge+shi*shi*shi+bai*bai*bai) == num) {
                //输出该数字num
                System.out.println(num);
                //同时计数器count的值增加1
                count++;
            }
        }
        //3.for循环结束后,打印count的值
        System.out.println("水仙花数字总共有: "+count+" 个");
    }
}

```

##### 计数思想:

![image-20200426113750867](img/image-20200426113750867.png)



### 第三章 循环语句2--while【重点】

##### 3.1 while循环语句介绍

```java
1.while循环格式:
	初始化表达式1;
	while(布尔表达式2) {
        循环体3;
        步进表达式4;
    }
	其它语句;

2.执行流程:
	1,2(循环条件: true),3,4 --> 2(循环条件: true),3,4 --> ... --> 
        直到布尔表达式2(循环条件: false),结束循环,执行循环后面的其它语句
```

##### 图解:

![image-20200426114916593](img/image-20200426114916593.png)



##### 3.2 while循环练习1

```java
需求:
	在控制台输出5次HelloWorld
public class Demo01WhileHello {
    public static void main(String[] args) {
        //使用for
        for (int i = 1; i <= 5; i++) {
            System.out.println("HelloWorld...."+i);
        }
        System.out.println("-------------");

        //使用while
        int j = 1;
        while(j<=5) {//j: 1,2,3,4,5    6<=5 --> false --> 结束while循环
            System.out.println("HelloWorld~~~~~"+j);
            j++;
        }
        System.out.println("main......end.....");
    }
}

        
```

##### 3.3 while循环练习2

```java
需求：
    世界最高山峰是珠穆朗玛峰(8844.43米=8844430毫米)，假如我有一张足够大的纸，它的厚度是0.1毫米。
	请问，我折叠多少次，可以折成珠穆朗玛峰的高度?
    折纸(折叠后的厚度是原有厚度的2倍,而不是平方的关系):
		原来: 0.1
		第一次: 0.2
        第二次: 0.4
        第三次: 0.8
        第四次: 1.6
        ...
                
实现步骤:
	0.定义2个double变量zf(珠峰的高度)和paper(纸张的厚度),并根据题目需求进行初始化
    1.定义int变量count,初始值0,作用用来记录折叠纸张的次数
    2.使用while循环,完成折叠纸张最终厚度达到珠峰的高度
       2.1循环条件: 只要折叠后的纸张厚度 小于 珠峰的高度 就必须继续折叠纸张
       2.2循环体: 折叠纸张(原有厚度的2倍: paper = paper*2;)  计数器count增加1
    3.while循环结束打印count的值
public class Demo02WhileZFCount {
    public static void main(String[] args) {
        //0.定义2个double变量zf(珠峰的高度)和paper(纸张的厚度),并根据题目需求进行初始化
        double zf = 8844430;//珠峰的高度
        double paper = 0.1;//纸张的厚度

        //1.定义int变量count,初始值0,作用用来记录折叠纸张的次数
        int count = 0;

        //2.使用while循环,完成折叠纸张最终厚度达到珠峰的高度
        //2.1循环条件: 只要折叠后的纸张厚度 小于 珠峰的高度 就必须继续折叠纸张
        //2.2循环体: 折叠纸张(原有厚度的2倍: paper = paper*2;)  计数器count增加1
        while (paper < zf) {
            //折叠纸张(原有厚度的2倍: paper = paper*2;)
            paper *= 2;
            //计数器count增加1
            count++;
            System.out.println("第"+count+"次折叠后纸张总厚度: "+paper);
        }

        //3.while循环结束打印count的值
        System.out.println("总共折叠纸张的次数: "+count);
        //1.34217728E7: 1.34217728*10^7 --> 13421772.8
        //珠峰高度:                         8844430
        System.out.println("最后折叠纸张的厚度: "+paper);
    }
}
           
```



### 第四章 循环语句3--do-while

##### 4.1 do-while循环语句介绍

```java
1.do-while循环格式:
	初始化表达式1;
	do {
        循环体3;
        步进表达式4;
    }while(布尔表达式2);

2.执行流程:
	1,3,4 -->  2(循环条件: true),3,4 --> ... --> 
        直到布尔表达式2(循环条件: false),结束循环,执行循环后面的其它语句

```

##### 图解:

![image-20200426141240409](img/image-20200426141240409.png)

##### 4.2 do-while循环练习1

```java
do-while循环练习：
	在控制台输出5次HelloWorld

public class Demo01DoWhileHello {
    public static void main(String[] args) {
        int i = 1;
        do {
            System.out.println("HelloWorld~~~~~"+i);
            i++;
        }while(i<=5);//2,3,4,5   6<=5: false,结束do-while循环,执行后面的语句
        System.out.println("main....end....");
    }
}

```



### **第五章** 循环语句其它知识【理解】

##### 5.1 循环语句的区别

```java
三种循环的区别总结
	1.建议使用的顺序:for,while,do-while 			
	2.循环次数确定的话,建议使用for,循环次数不确定建议使用while 【后面有使用场景】
    	循环次数不确定需要先写成死循环的格式【while好看】    --------后天讲解
	3.do-while循环来讲的话,至少执行一次 
	4.while和do-while循环而言,循环结束后,初始化条件中定义的变量可以继续使用, 
		但是for循环的不能使用(在for循环内部定义初始化语句)
    
public class Demo02Diff {
    public static void main(String[] args) {
        //3.do-while循环来讲的话,至少执行一次

        //for循环: 先判断条件,后执行循环体
        //for循环第一次布尔表达式都不成立(false): 循环体一次都不执行
        //第一次: i>5 --> 3>5 --> false 不执行循环体,直接执行for循环后面的输出语句
        for (int i = 3; i > 5; i++) {
            System.out.println("Hello...for...");
        }
        System.out.println("for...end...");

        //while循环: 先判断条件,后执行循环体
        //while循环第一次布尔表达式都不成立(false): 循环体一次都不执行
        //第一次: j>5 --> 3>5 --> false 不执行循环体,直接执行while循环后面的输出语句
        int j = 3;
        while (j > 5) {
            System.out.println("Hello...while...");
            j++;
        }
        System.out.println("while...end...");

        //do-while循环: 先执行循环体,再判断条件
        //do-while循环第一次布尔表达式都不成立(false): 循环体会至少执行一次(先执行,后判断条件)
        //第一次: 定义int变量k的值3,接着执行{}中的循环体,k的值变成4
        //再执行判断条件k>5 --> 4>5 --> false 结束do-while循环执行do-while后面的输出语句
        int k = 3;
        do{
            System.out.println("Hello...do-while...");
            k++;//4
        } while(k>5);//k>5 --> 4>5 --> false 结束do-while循环执行do-while后面的输出语句
        System.out.println("do-while...end...");
    }
}

public class Demo03Diff {
    public static void main(String[] args) {
        //4.while和do-while循环而言,循环结束后,初始化条件中定义的变量可以继续使用,
        //但是for循环的不能使用(在for循环内部定义初始化语句)
        for (int i = 1; i <= 3; i++) {
            System.out.println("Hello...for...in..."+i);
        }
        //错误: i是在for循环内部定义,只能在for循环内部使用
        //出了for循环,就不可以继续使用
        //System.out.println("Hello...for...out..."+i);
        System.out.println("Hello...for...out...");

        //while循环
        int j = 1;
        while (j <= 3) {
            System.out.println("Hello...while...in..."+j);
            j++;
        }
        //while循环: 初始化语句中定义的变量,while循环结束后仍然可以使用
        System.out.println("Hello...while...out..."+j);

        //do-while循环
        int k = 1;
        do{
            System.out.println("Hello...do-while...in..."+k);
            k++;
        } while(k<=3);
        //do-while循环: 初始化语句中定义的变量,do-while循环结束后仍然可以使用
        System.out.println("Hello...do-while...out..."+k);
    }
}


```

##### 5.2 死循环

```java
/*
     死循环
        1.概念: 永不休止的循环
        2.分类:
            (1)for循环的死循环格式      for芬芬
                for(;;){...}

            (2)while循环的死循环格式        建议使用
                while(true){...}

            (3)do-while循环的死循环格式
                do{
                    ...
                }while(true);
 */
public class Demo04DeadLoop {
    public static void main(String[] args) {
        //for循环
        /*for (;true;) {
            System.out.println("Hello");
        }*/
        //for循环的死循环格式
        //不写布尔表达式: 默认就是true
        /*for (;;) {
            System.out.println("Hello");
        }*/

        //while循环的死循环格式
        /*int i = 0;
        while(i<3) {
            System.out.println("Hello");
        }*/
        /*while (true) {
            System.out.println("Hello");
        }*/

        //do-while循环的死循环格式
        /*int i = 0;
        do {
            System.out.println("Hello");
        }while(i<3);*/
        do {
            System.out.println("Hello");
        }while(true);
    }
}

```

##### 总结

```java
能够使用for循环完成一个范围的数据求和
    //1.在for外面定义int变量sum,用来累加求和,初始值0
    int sum = 0;
	//2.使用for循环获取指定范围内的每个数字,循环变量是int类型的num
	for(int num = 1;num<=100;num++) {
        //2.1把num中的当前数字累加到求和变量sum中
        sum += num;
    }
	//3.for循环结束,打印sum的值
	sout(sum);
能够使用for循环完成统计水仙花个数 
    //1.在for外面定义int变量count,用来统计数量,初始值0
    int count = 0;
	//2.使用for循环获取每个三位数字,循环变量是int类型的num
	for(int num = 100;num<=999;num++) {
        //2.1计算num中数字的个位,十位,百位
        int ge = num%10;
        int shi = num/10%10;
        int bai = num/100%10;
        //2.2计算个位,十位,百位的立方和,保存到int变量sum中
        int sum = ge*ge*ge + shi*shi*shi + bai*bai*bai;
        //2.3判断如果个位,十位,百位的立方和sum 等于 三位数字num本身 说明是水仙花数字
        if(sum == num) {
            //打印num中的数字
            sout(num);
            //计数器增加1
            count++;
        }
    }
	//3.for循环结束,打印计数器count的值
	sout(count);

能够知道三种循环的区别
    1.for/while: 先进行条件判断,后执行循环体	如果第一次条件不成立,循环体一次都不执行
    2.do-while: 先执行,后判断条件 如果第一次条件不成立,循环体仍然执行一次
        do-while: 循环体,至少执行一次
    3.for循环内部定义的循环变量,for循环外面不可以使用
    4.while/do-while: 初始化表达式中定义的变量,while/do-while外面可以使用
        
能够使用while循环完成珠穆朗玛峰案例
    //1.定义2个double变量,代表珠峰的高度和纸张的厚度
    double zf = 8848330, paper = 0.1;
    //2.在while外面定义int变量count,用来统计数量,初始值0
	int count = 0;
    //3.使用while循环
	while(paper<zf) {
        //3.1折叠一次
        paper *= 2;
        //3.2计数器增加1
        count++;
    }
	//4.while循环结束,打印count的值
	sout(count);
```

