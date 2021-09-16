# day08 【方法】

##### 今日复习指南

```java
1.有参数无返回值方法的定义和调用(0.5个小时内完成,多写几遍)	
    itheima03包中Demo01PrintOu.java   打印一个int数字是否是偶数
    itheima03包中Demo02PrintMax.java  打印两个int数字的最大值
    
2.有参数有返回值方法的定义和调用(1.5个小时内完成,多写几遍)   
    itheima04包中Demo01GetOu.java   获取一个int数字是否是偶数
    itheima04包中Demo02GetMax.java  获取两个int数字的最大值
3.其它知识
    (1)方法的调用方式
    (2)形参和实参的区别
```



##### 今日内容

```java
方法的概念【重要】
无参数无返回值方法的定义和调用【重要】
有参数无返回值方法的定义和调用【重要】
有参数有返回值方法的定义和调用【重要重要重要重要重要】
```

### 第一章 方法入门【理解】

##### 1.1 方法引入

```java
/*
    代码功能:模拟游戏中打怪物的场景

    发现问题:
        打怪物的代码是相同的,打了3次怪物,写了3次相同的代码,导致程序代码冗余,阅读性差

    怎么解决问题呢?
      1.能否将发射炮弹的代码,做成一个方法/功能
      2.使用的时候直接调用即可
	========================================================================
				这个代码大家不用写,直接拷贝
	========================================================================
 */
public class Demo01NoMethod {
    /*
        main是一个主方法,由JVM调用,是程序的入口
            1.public static:修饰符,目前固定写法
            2.void:返回值类型,表示方法内部的代码执行完毕,没有最终的结果,返回给调用者
            3.main:方法名称:固定写法
            4.String[] args:方法的参数
    */
    public static void main(String[] args) {
        System.out.println("游戏开始...");

        System.out.println("看到了一个怪物...血牙野猪...");
        System.out.println("准备发射5发炮弹");
        System.out.println("发射第1发炮弹* * * *");
        System.out.println("发射第2发炮弹* * * *");
        System.out.println("发射第3发炮弹* * * *");
        System.out.println("发射第4发炮弹* * * *");
        System.out.println("发射第5发炮弹* * * *");
        System.out.println("发射5发炮弹结束");
        System.out.println("...血牙野猪被打倒...");

        System.out.println("...走啊走啊走啊走...");
        System.out.println("看到了一个怪物...黄金虎鲨...");
        System.out.println("准备发射5发炮弹");
        System.out.println("发射第1发炮弹* * * *");
        System.out.println("发射第2发炮弹* * * *");
        System.out.println("发射第3发炮弹* * * *");
        System.out.println("发射第4发炮弹* * * *");
        System.out.println("发射第5发炮弹* * * *");
        System.out.println("发射5发炮弹结束");
        System.out.println("...黄金虎鲨被打倒...");

        System.out.println("...走啊走啊走啊走...");
        System.out.println("看到了一个怪物...吞天巨狼...");
        System.out.println("准备发射5发炮弹");
        System.out.println("发射第1发炮弹* * * *");
        System.out.println("发射第2发炮弹* * * *");
        System.out.println("发射第3发炮弹* * * *");
        System.out.println("发射第4发炮弹* * * *");
        System.out.println("发射第5发炮弹* * * *");
        System.out.println("发射5发炮弹结束");
        System.out.println("...吞天巨狼被打倒...");
        System.out.println("...走啊走啊走啊走...");

        System.out.println("游戏结束...");
    }
}
```

```java
package com.itheima01;

/*
    代码功能:模拟游戏中打怪物的场景

    发现问题:
        打怪物的代码是相同的,打了3次怪物,写了3次相同的代码,导致程序代码冗余,阅读性差

    怎么解决问题呢?
      1.能否将发射炮弹的代码,做成一个方法/功能
      2.使用的时候直接调用即可
	========================================================================
				这个代码大家不用写,直接拷贝
	========================================================================

	注意:
	    1.方法定义完毕后不调用不执行
	    2.调用格式:
            方法名称(...);
        3.方法可以调用任意多次
 */
public class Demo02UseMethod {
    /*
        main是一个主方法,由JVM调用,是程序的入口
            1.public static:修饰符,目前固定写法
            2.void:返回值类型,表示方法内部的代码执行完毕,没有最终的结果,返回给调用者
            3.main:方法名称:固定写法
            4.String[] args:方法的参数
    */
    public static void main(String[] args) {
        /*int num = 0;
        System.out.println(num);
        int[] arr = {10,20};
        System.out.println(arr);*/
        System.out.println("游戏开始...");

        System.out.println("看到了一个怪物...血牙野猪...");

        //调用方法,发射炮弹
        fire();

        System.out.println("...血牙野猪被打倒...");

        System.out.println("...走啊走啊走啊走...");
        System.out.println("看到了一个怪物...黄金虎鲨...");

        //调用方法,发射炮弹
        fire();

        System.out.println("...黄金虎鲨被打倒...");

        System.out.println("...走啊走啊走啊走...");
        System.out.println("看到了一个怪物...吞天巨狼...");

        //调用方法,发射炮弹
        fire();

        System.out.println("...吞天巨狼被打倒...");
        System.out.println("...走啊走啊走啊走...");

        System.out.println("游戏结束...");
    }
    /*
        模拟main方法,定义一个发射炮弹的方法fire
     */
    public static void fire() {
        System.out.println("准备发射5发炮弹");
        for (int i = 1; i <= 5; i++) {
            System.out.println("发射第"+i+"发炮弹* * * *");
        }
        System.out.println("发射5发炮弹结束");

        return ;//结束方法,返回到方法的调用处
    }
}
```



图解:

![image-20200516092757974](img/image-20200516092757974.png)



##### 1.2 方法的概念和格式

```java
1.方法的概念:
	就是将具有独立功能的代码块组织成为一个整体，使其具有特殊功能的代码集。
    将具有特殊功能的一段代码,使用大括号{}括起来,添加必要的修饰符,起个名字, 方便使用   
        
2.方法的格式:
	修饰符 返回值类型 方法名称(参数列表) {
    	功能代码;
        return ;//如果返回值类型是void,建议省略不写
    }

3.格式解释:
	(1)修饰符: public static 目前固定写法,先记住
    (2)返回值类型: 方法的功能代码执行完毕后,产生的需要返还给方法的调用者的结果数据的具体类型
        目前定义的方法没有返回值,返回值类型固定写为void
    (3)方法名称: 
		给方法起个名字(符合标识符的命名规范,小驼峰原则(第一个单词首字母小写,其它单词首字母大写)),方便使用
    (4)参数列表: 目前没有参数,不需要写参数列表,但是必须保留小括号()
    (5)功能代码: 完成特殊功能的一行/多行代码
    (6)return ;:
		a.结束方法
        b.返回到方法的调用处
```



##### 1.3 无返回值无参数方法的定义和调用

```java
1.练习:
	定义方法method,方法内部输出一句话"我是一个方法"
        
/*
    无返回值无参数方法的定义和调用
        无参数:
            目前没有参数,不需要写参数列表,但是必须保留小括号()
        无返回值:
            目前定义的方法没有返回值,返回值类型固定写为void
            方法内部没有数据返还给调用者,没有返回值,返回值类型固定写为void

    1.练习:
	    定义方法method,方法内部输出一句话"我是一个方法"
    2.注意:
	    (1)方法定义完毕后不调用不执行
	    (2)调用格式:
            方法名称(...);
        (3)方法可以调用任意多次
 */
public class Demo03Method {

    public static void main(String[] args) {

        System.out.println("main...start...");

        //调用方法
        method();

        System.out.println("main...end...");

    }

    //定义方法method,方法内部输出一句话"我是一个方法"
    public static void method() {

        System.out.println("我是一个方法");

        return ;//结束方法,返回到方法的调用处,建议省略
    }
}

```

##### 1.4 无返回值无参数方法的调用图解

![image-20200516095454283](img/image-20200516095454283.png)

##### 1.5 无参数无返回值的方法练习-打印数字是否是偶数

```java
需求:
	定义一个方法，打印输出该方法内部的数据(方法内部定义的变量)是否是偶数

/*
    无返回值无参数方法的定义和调用
        无参数:
            目前没有参数,不需要写参数列表,但是必须保留小括号()
        无返回值:
            目前定义的方法没有返回值,返回值类型固定写为void
            方法内部没有数据返还给调用者,没有返回值,返回值类型固定写为void

    1.练习:
	    定义一个方法，打印输出该方法内部的数据(方法内部定义的变量)是否是偶数

    2.注意:
	    (1)方法定义完毕后不调用不执行
	    (2)调用格式:
            方法名称(...);
        (3)方法可以调用任意多次

    练习中如果没有明确数据类型,默认int类型
 */
public class Demo01PrintOu {

    public static void main(String[] args) {

        System.out.println("main...start...");

        //调用方法
        printOu();

        System.out.println("main...end...");

    }

    //定义一个方法，打印输出该方法内部的数据(方法内部定义的变量)是否是偶数
    public static void printOu() {

        int num = 12;

        boolean result = (num%2==0) ? true : false;

        System.out.println(num+"是偶数吗? "+result);

        return ;//结束方法,返回到方法的调用处,建议省略
    }
}

```

图解分析:

![image-20200516101539927](img/image-20200516101539927.png)

##### 1.6 无参数无返回值的方法练习-打印最大值

```java
需求:
	定义一个方法，打印该方法内部的两个数据(方法内部定义的变量)的最大值
/*
    无返回值无参数方法的定义和调用
        无参数:
            目前没有参数,不需要写参数列表,但是必须保留小括号()
        无返回值:
            目前定义的方法没有返回值,返回值类型固定写为void
            方法内部没有数据返还给调用者,没有返回值,返回值类型固定写为void

    1.练习:
	    定义一个方法，打印该方法内部的两个数据(方法内部定义的变量)的最大值

    2.注意:
	    (1)方法定义完毕后不调用不执行
	    (2)调用格式:
            方法名称(...);
        (3)方法可以调用任意多次

    练习中如果没有明确数据类型,默认int类型
 */
public class Demo02PrintMax {

    public static void main(String[] args) {

        System.out.println("main...start...");

        //调用方法
        printMax();

        System.out.println("main...end...");
    }

    //定义一个方法，打印该方法内部的两个数据(方法内部定义的变量)的最大值
    public static void printMax() {

        int a = 100, b = 200;

        int max = (a>b) ? a : b;

        System.out.println("最大值: "+max);

        return ;//结束方法,返回到方法的调用处,建议省略
    }

}

```

图解:

![image-20200516102543118](img/image-20200516102543118.png)

### 第二章 方法详解【理解】

##### 2.1 方法的格式详解

```java
1.方法的概念:
	就是将具有独立功能的代码块组织成为一个整体，使其具有特殊功能的代码集。
    将具有特殊功能的一段代码,使用大括号{}括起来,添加必要的修饰符,起个名字, 方便使用   
        
2.方法的格式:
	修饰符 返回值类型 方法名称(数据类型1 变量名称1,数据类型2 变量名称2...) {
    	功能代码;
        return 返回值;//如果return 后面 有具体的结果数据,不能省略return
    }
	注意:
		(1)方法没有参数,不用写参数列表,但是必须保留小括号()
        (2)方法内部没有返回值返还给调用者,返回值类型必须固定写为void

3.格式解释:
	(1)修饰符: public static 目前固定写法,先记住
    (2)返回值类型: 告诉方法的调用者,我方法结束后,给你一个什么类型的数据
		方法的功能代码执行完毕后,产生的需要返还给方法的调用者的结果数据的具体类型
        举例:
			如果方法内部返回整数数字100,返回值类型写为int
            如果方法内部返回小数数字6.6,返回值类型写为double
            如果方法内部返回true/false,返回值类型写为boolean
    (3)方法名称: 
		给方法起个名字(符合标识符的命名规范,小驼峰原则(第一个单词首字母小写,其它单词首字母大写)),方便使用
    
    (4)参数列表: 你调用我这个方法时,需要给我几个什么样子的数据
        就是在定义方法时,小括号()中定义了一个/多个变量    
		定义方法参数列表举例:
			(int a): 调用方法时,必须传递给方法一个int类型的数据
            (int a,int b): 调用方法时,必须传递给方法两个int类型的数据
            (double a,double b): 调用方法时,必须传递给方法两个double类型的数据
                
    (5)功能代码: 完成特殊功能的一行/多行代码
    (6)return 返回值/结果数据;:
		a.结束方法
        b.把return 后面的返回值/结果数据,返还到方法的调用处
            
4.方法的理解(工厂/机器)
    (1)生产汽车的工厂:
		原材料: 发动机,变速箱,车架...
        产出物: BMW750Li S600 ZT700
    (2)榨汁机:
		原材料: 水果,水,糖,冰块...
        产出物: 果汁(苹果汁,桃汁,梨汁...)  
    
    	原材料是进入工厂/机器的东西,相当于调用方法时传递的数据		参数列表
        产出物是从工厂/机器中出来的东西,相当于调用方法后的返回值		返回值 --- 返回值类型 
            
5.定义方法的三要素
	(1)方法名称: 
	(2)参数列表:
	(3)返回值类型:

6.注意:
	    (1)方法定义完毕后不调用不执行
	    (2)调用格式:
            方法名称(参数1,参数2...);
        (3)方法可以调用任意多次
```



##### 2.2 带参数的方法练习-打印数字是否是偶数

```java
需求:
	 定义一个方法，该方法接收一个int参数，方法内部打印输出该数据是否是偶数
/*
    带参数无返回值的方法练习
        方法是否需要参数:
            分析方法需求中是否具有不确定的东西

        方法是否需要返回值:
            如果方法需求中能够明确看到打印/输出二字,说明该方法不需要返回值,返回值类型固定写为void

    1.练习:
	    定义一个方法，打印一个整数数字是否是偶数

    2.三要素:
        (1)方法名称: printOu
	    (2)参数列表: int num
	    (3)返回值类型: void

    练习中如果没有明确数据类型,默认int类型
 */
public class Demo01PrintOu {

    public static void main(String[] args) {

        System.out.println("main...start...");

        //调用方法: 传递的是常量
        printOu(11 );

        //调用方法方法: 传递变量
        int a = 12;
        printOu(a);

        System.out.println("main...end...");

    }

    //定义一个方法，打印一个整数数字是否是偶数
    /*
        你调用我的方法printOu时,必须给我传递一个int类型的数据,
        我printOu方法内部执行完毕后直接打印输出结果
        你: 方法的调用者
        我: 方法本身
        有进无出
     */
    public static void printOu(int num) {

        boolean result = (num%2==0) ? true : false;

        System.out.println(num+"是偶数吗? "+result);

        return ;//结束方法,返回到方法的调用处
    }
}

```

图解:

![image-20200516112242265](img/image-20200516112242265.png)

##### 2.3 带参数的方法练习-打印最大值

```java
需求:
	 定义一个方法用于打印两个int数中的较大数，数据来自于方法参数
/*
    带参数无返回值的方法练习
        方法是否需要参数:
            分析方法需求中是否具有不确定的东西

        方法是否需要返回值:
            如果方法需求中能够明确看到打印/输出二字,说明该方法不需要返回值,返回值类型固定写为void

    1.练习:
	    定义一个方法用于打印两个int数字中的较大数，数据来自于方法参数

    2.三要素:
        (1)方法名称: printMax
	    (2)参数列表: int a,int b
	    (3)返回值类型: void

    练习中如果没有明确数据类型,默认int类型
 */
public class Demo02PrintMax {

    public static void main(String[] args) {

        System.out.println("main...start...");

        //调用方法: 传递的是常量
        printMax(10,20);

        //调用方法方法: 传递变量
        int m = 100;
        int n = 200;
        printMax(m,n);


        System.out.println("main...end...");

    }

    //定义一个方法用于打印两个int数字中的较大数，数据来自于方法参数
    /*
        你调用我的方法printMax时,必须给我传递两个int类型的数据,
        我printMax方法内部执行完毕后直接打印输出最大值的结果
        你: 方法的调用者
        我: 方法本身
     */
    public static void printMax(int a, int b) {

        int max = (a>b) ? a : b;

        System.out.println("最大值: "+max);

        return ;//结束方法,返回到方法的调用处
    }
}

```

图解:

![image-20200516113747053](img/image-20200516113747053.png)



##### 2.4 带返回值的方法练习-获取数字是否是偶数

```java
需求:
	定义一个方法，该方法接收一个int参数，判断该数据是否是偶数，并返回真假值
/*
    有参数有返回值的方法练习
        方法是否需要参数:
            分析方法需求中是否具有不确定的东西

        方法是否需要返回值:
            如果方法需求中能够明确看到打印/输出二字,说明该方法不需要返回值,返回值类型固定写为void
            如果方法需求中能够明确看到获取/返回/判断二字,说明该方法需要返回值,必须定义具体的返回值类型

    1.练习:
	    定义一个方法，该方法接收一个int参数，判断该数据是否是偶数，并返回真假值

    2.三要素:
        (1)方法名称: getOu
	    (2)参数列表: int num
	    (3)返回值类型: boolean

    练习中如果没有明确数据类型,默认int类型
 */
public class Demo01GetOu {

    public static void main(String[] args) {

        System.out.println("main...start...");

        //调用方法: 传递的是常量
        boolean result = getOu(11);

        System.out.println("11是偶数吗? "+result);

        //调用方法方法: 传递变量
        int a = 12;
        result = getOu(a);
        System.out.println(a+"是偶数吗? "+result);

        System.out.println("main...end...");

    }

    //定义一个方法，该方法接收一个int参数，判断该数据是否是偶数，并返回真假值
    /*
        你调用我的方法getOu时,必须给我传递一个int类型的数据,
        我getOu方法内部执行完毕后,会返还给你一个boolean类型的数据
        你: 方法的调用者
        我: 方法本身
        有进(参数)有出(返回值)
     */
    //boolean: 告诉方法的调用者,方法功能代码执行完毕后,会返回数据的具体类型(会返回一个什么样子的数据)
    public static boolean getOu(int num) {

        boolean result = (num % 2 == 0) ? true : false;

        return result;//结束方法,并且把result中的数据,返还给方法的调用处/者
    }
}

```

图解分析:

![image-20200516120122043](img/image-20200516120122043.png)

##### 2.5 带返回值的方法练习-获取最大值

```java
需求:
	设计一个方法可以获取两个int数的较大值，数据来自于参数
/*
    有参数有返回值的方法练习
        方法是否需要参数:
            分析方法需求中是否具有不确定的东西

        方法是否需要返回值:
            如果方法需求中能够明确看到打印/输出二字,说明该方法不需要返回值,返回值类型固定写为void
            如果方法需求中能够明确看到获取/返回/判断二字,说明该方法需要返回值,必须定义具体的返回值类型

    1.练习:
	    设计一个方法可以获取两个int数的较大值，数据来自于参数

    2.三要素:
        (1)方法名称: getMax
	    (2)参数列表: int a,int b
	    (3)返回值类型: int

    练习中如果没有明确数据类型,默认int类型
 */
public class Demo02GetMax {

    public static void main(String[] args) {

        System.out.println("main...start...");

        //调用方法: 传递的是常量
        int result = getMax(100,200);
        System.out.println("100和200的最大值: "+result);

        //调用方法方法: 传递变量
        int a = 10, b = 20;
        int max = getMax(a,b);
        System.out.println(a+"和"+b+"的最大值: "+max);

        System.out.println("main...end...");

    }

    //设计一个方法可以获取两个int数的较大值，数据来自于参数
    /*
        你调用我的方法getMax时,必须给我传递两个int类型的数据,
        我getMax方法内部执行完毕后,会返还给你一个int类型的数据
        你: 方法的调用者
        我: 方法本身
        有进(参数)有出(返回值)
     */
    //int: 告诉方法的调用者,方法功能代码执行完毕后,会返回数据的具体类型(会返回一个什么样子的数据)
    public static int getMax(int a, int b) {

        int max = (a>b) ? a : b;

        return max;//结束方法,并且把max中的数据,返还给方法的调用处/者
    }
}


```

##### 图解分析:

![image-20200516142013131](img/image-20200516142013131.png)

##### 2.6 方法的注意事项

```java
/*
	方法的注意事项
        1.方法不能嵌套定义(在定义方法的内部又定义了其它方法),可以调用其它方法
        2.方法可以嵌套调用
        3.返回值类型，必须要和 return 语句返回的数据的类型要匹配，否则编译失败 。
        4.不能在 return 后面写代码， return 意味着方法结束，所有后面的代码永远不会执行，属于无效代码。
        5.void表示无返回值，可以省略return，也可以单独的书写return，后面不加数据
 */
/*
	方法的注意事项
        1.方法不能嵌套定义(在定义方法的内部又定义了其它方法),可以调用其它方法
        2.方法可以嵌套调用
        3.返回值类型，必须要和 return 语句返回的数据的类型要匹配，否则编译失败 。
        4.不能在 return 后面写代码， return 意味着方法结束，所有后面的代码永远不会执行，属于无效代码。
        5.void表示无返回值，可以省略return，也可以单独的书写return，后面不加数据
 */
public class Demo01Notice {
    public static void main(String[] args) {
        //1.调用getNum方法,获取一个int数字
        int num = getNum();
        //2.调用printNum方法,打印一个int数字
        printNum(num);

        //方法的嵌套调用
        //先执行getNum方法:获取一个整数数字
        //再把整数数字交给printNum方法做打印输出
        printNum(getNum());
    }
    //定义方法
    public static void method() {
        System.out.println("method....");
        //错误: 方法不能嵌套定义方法
        /*public static void show() {
            System.out.println("show....");
        }*/
    }

    //打印int数字
    public static void printNum(int num) {
        System.out.println(num);
    }
    //获取一个int数字
    public static int getNum() {
        return 100;
    }
}
```

```java
/*
	方法的注意事项
        1.方法不能嵌套定义(在定义方法的内部又定义了其它方法),可以调用其它方法
        2.方法可以嵌套调用
        3.返回值类型，必须要和 return 语句返回的数据的类型要匹配，否则编译失败 。
        4.不能在 return 后面写代码， return 意味着方法结束，所有后面的代码永远不会执行，属于无效代码。
        5.void表示无返回值，可以省略return，也可以单独的书写return，后面不能加数据,写个分号
 */
public class Demo02Notice {
    public static void main(String[] args) {

    }

    //3.返回值类型，必须要和 return 语句返回的数据的类型要匹配，否则编译失败 。
    public static double getDoubleNum() {
        //return 6.6;//6.6就是一个double类型的数字
        //return 6.6F;//6.6F是一个float类型的数字,可以自动类型提升为double类型
        return 6;//6是一个int类型的数字,可以自动类型提升为double类型
    }

    //4.不能在 return 后面写代码， return 意味着方法结束，所有后面的代码永远不会执行，属于无效代码。
    public static int getMax(int a,int b) {
        if (a > b) {
            return a;
        } else {
            return b;
        }
        //System.out.println("getMax...end...");//错误的,return后面不能写其他代码
    }

    //5.void表示无返回值，可以省略return，也可以单独的书写return，后面不能加数据,写个分号
    public static void method() {
        System.out.println("method....");
        return ;//建议省略return
    }
}

```



##### 2.7 有返回值的方法调用方式

```java
/*
    有返回值的方法调用方式
        1.赋值调用: 把有返回值的方法的调用结果保存到对应的变量中              ----推荐使用----
            数据类型 变量名称 = 方法名称(参数...);

        2.输出/打印调用: 把有返回值的方法的调用结果直接交给输出语句
            System.out.println(方法名称(参数...));

        3.单独调用: 既不保存方法的结果,也没有对结果进行输出                   -----不推荐使用,没有意义-----
            方法名称(参数...);
 */
public class Demo01DYMethod {
    public static void main(String[] args) {
        System.out.println("main...start...");

        //1.赋值调用: 把有返回值的方法的调用结果保存到对应的变量中
        //数据类型 变量名称 = 方法名称(参数...);
        int result = getSum(10,20);
        //可以对结果数据做其它操作
        //result *= 100;
        System.out.println("和: "+result);

        //2.输出/打印调用: 把有返回值的方法的调用结果直接交给输出语句
        //System.out.println(方法名称(参数...));
        System.out.println(getSum(100,200));

        //3.单独调用: 既不保存方法的结果,也没有对结果进行输出
        getSum(5,10);

        System.out.println("main...end...");
    }

    //定义方法,获取2个int数字之和
    public static int getSum(int a, int b) {
        int sum = a + b;
        return sum;
    }
}

```

##### 2.8 无返回值的方法调用方式

```java
/*
    无返回值的方法调用方式

        1.单独调用: 既不保存方法的结果,也没有对结果进行输出            只能采用单独调用
            方法名称(参数...);

        2.赋值调用: 把有返回值的方法的调用结果保存到对应的变量中       不能赋值调用
            数据类型 变量名称 = 方法名称(参数...);

        3.输出/打印调用: 把有返回值的方法的调用结果直接交给输出语句    不能输出调用
            System.out.println(方法名称(参数...));
 */
public class Demo02DYMethod {
    public static void main(String[] args) {
        System.out.println("main...start...");
        //1.单独调用: 既不保存方法的结果,也没有对结果进行输出
        //方法名称(参数...);
        printSum(10,20);

        //2.赋值调用: 把有返回值的方法的调用结果保存到对应的变量中
        //数据类型 变量名称 = 方法名称(参数...);
        //int a = printSum(5,15);//错误的,int变量只能保存整数,但是printSum方法执行结束没有返回任何结果数据
        //void a = printSum(5,15);//错误的,void根本不是数据类型

        //3.输出/打印调用: 把有返回值的方法的调用结果直接交给输出语句
        //System.out.println(方法名称(参数...));
        //System.out.println(printSum(3,2));//错误: 因为printSum方法执行完毕后,没有任何结果返回

        System.out.println("main...end...");
    }

    //定义方法,打印2个int数字之和
    public static void printSum(int a, int b) {
        int sum = a + b;
        System.out.println("和: "+sum);
        return ;//结束方法,返回到方法的调用处,注意没有带回任何数据
    }
}

```

##### 2.9 形式参数和实际参数的区别

```java
/*
    形式参数和实际参数的区别
        1.形式参数:
            (1)概念: 定义方法时()中定义的参数(定义变量),叫做形式参数
            (2)特点:
                a.定义形式参数的时候,是没有值的
                b.当调用该方法时,形式参数才会有值

        2.实际参数:
            (1)概念: 调用方法时()中给出的参数(常量/变量),叫做实际参数
            (2)特点:
                a.调用方法时,()中写的数据(常量/变量)
                b.必须要有值才可以
 */
public class Demo03ParamDiff {
    public static void main(String[] args) {
        System.out.println("main...start...");
        /*
            2.实际参数:
                (1)概念: 调用方法时()中给出的参数(常量/变量),叫做实际参数
                (2)特点:
                    a.调用方法时,()中写的数据(常量/变量)
                    b.必须要有值才可以
         */
        //调用方法: 传递常量
        printSum(10,20);//10,20叫做实际参数

        //调用方法: 传递变量
        int m = 100,n = 200;

        printSum(m,n);//m,n叫做实际参数


        System.out.println("main...end...");
    }

    /*
        1.形式参数:
            (1)概念: 定义方法时()中定义的参数(定义变量),叫做形式参数
            (2)特点:
                a.定义形式参数的时候,是没有值的
                b.当调用该方法时,形式参数才会有值
     */
    //定义方法,打印2个int数字之和
    public static void printSum(int a, int b) {
        int sum = a + b;
        System.out.println("和: "+sum);
        return ;//结束方法,返回到方法的调用处,注意没有带回任何数据
    }
}

```

![image-20200516151320201](img/image-20200516151320201.png)

![image-20200516151436471](img/image-20200516151436471.png)

##### 总结

```java
能够知道方法定义的通用格式
    修饰符 返回值类型 方法名称(参数列表 ...){
    	功能代码;
    	return 返回值;
	}
能够知道形参和实参的区别
    1.形参: 在定义方法时()中定义的参数(定义变量),称为形式参数 
        特点:
			(1)定义时,是没有值的
            (2)调用方法时,才会有值
    2.实参: 在调用方法时()中给出的参数,称为实参
        特点:
			(1)调用方法时()写的数据/变量
            (2)变量作为实参时,必须有值
		
能够使用方法完成两个较大数的获取并调用方法
    //调用方式: 赋值调用
    int max = getMax(10,20);
	sout(max);
	//调用方式: 打印调用
	sout(getMax(100,200));
    public static int getMax(int a,int b) {
    	int max = (a>b) ? a : b;
        return max;                
    }
```

