# day07 【数组】

##### 今日复习指南

```java
1.简化格式初始化数组的使用(0.5个小时内完成,多写几遍)
	Demo06ArrayUse.java    
    
2.数组的遍历(0.5个小时内完成,多写几遍)
    Demo01EachArray.java
    
3.数组的最大值(1个小时,多写几遍)
    Demo03ArrayMax.java
```



##### 今日内容

```java
数组的概念和数组变量的定义【重点】
数组的初始化及使用【重点的重点】		---------------最核心的内容--------------
数组的内存图【理解】
数组的常见问题【理解】
数组的练习【重点的重点】			   ---------------最核心的内容--------------
    
快捷键：
    生产输出语句： 表达式.sout
    数组遍历:
    	数组名.fori: 正着遍历
    	数组名.forr: 倒着遍历
```

### 第一章 数组定义和访问【理解】

##### 1.1 容器的概念

```java

变量中只能存储一个数据,新的数据进来,老的数据将被替换,如果需要存储多个数据,需要使用容器。

容器概念
	容器：是将多个数据存储到一起，每个数据称为该容器的元素。
    生活中的容器：水杯，衣柜，鞋柜，教室

数组：
	1.概念： java中的数组就是一个容器，可以存储多个数据，但是数据的类型必须一致
    2.特点：
    	(1)可以存储多个数据
        (2)多个数据的类型必须保持一致
        (3)数组一旦创建,长度是永远不可以发生改变
    
public class Demo01Box {		//-----------------------此代码不用敲--------------------------------
    public static void main(String[] args) {
        //定义一个int变量num,并初始化
        //一个变量中只能存储一个数据
        int num = 10;
        System.out.println(num);

        //新的数据进来,老的数据将被替换
        num = 20;
        System.out.println(num);


        //比如我们班有80个学生需要参加考试,每个学生对应一个成绩(整数)
        //可以定义80个int变量
        int a = 80;
        int b = 90;
        int c = 70;
        int d = 50;
        int e = 85;
        int f = 95;
        int g = 59;
        int h = 63;

        //需要求总分
        int sum = a + b + c + d + e + f + g + h;

        //需要求平均分
        int avg = sum/80;

        //需要求最高分和最低分: 实现起来非常麻烦


    }
}
           
```

##### 1.2 数组变量的定义

```java
1.数组变量定义格式一：			---------------推荐使用-------------
    数据类型[] 数组名称;	

2.数组变量定义格式二：
    数据类型 数组名称[];
	

1.定义一个存储int类型数组的变量arrayA
2.定义一个存储double类型数组的变量arrayB
3.定义一个存储char类型数组的变量arrayC
    
public class Demo02Array {
    public static void main(String[] args) {
        //定义int变量num
        int num;
        //System.out.println(num);//错误:变量未初始化,不能使用

        //(1)定义一个存储int类型数组的变量arrayA
        //int类型数组: 该容器中只能存储的是int类型的数字
        int[] arrayA;
        //System.out.println(arrayA);//错误的: arrayA只是一个用来存储数组的变量,但是目前没有向arrayA中存储数组

        //(2)定义一个存储double类型数组的变量arrayB
        //double类型数组: 该数组容器中只能存储double类型的数据
        double arrayB[];

        //(3)定义一个存储char类型数组的变量arrayC
        //char类型数组: 该数组容器中只能存储char类型的数据
        char[] arrayC;
    }
}

```

##### 图解:

![image-20200515100251817](img/image-20200515100251817.png)

##### 1.3 数组的第一种初始化方式

```java
1.创建一个int类型的数组,可以存储3个int数据,给该数组起个名称叫做arrayA
2.创建一个double类型的数组,可以存储7个double数据,给该数组起个名称叫做arrayB
3.创建一个char类型的数组,可以存储5个char数据,给该数组起个名称叫做arrayC
    
数组的第一种初始化方式(动态初始化: 指定数组的长度)
	1.格式:
    	数据类型[] 数组名称 = new 数据类型[长度];

    2.格式解释:
    	(1)左侧数据类型: 规定了数组中可以存储哪种类型的数据
        (2)左侧[]: 表示数组的意思
        (3)数组名称: 就是给数组起个名字(相当于门牌号),方便找到并使用数组
        (4)=: 表示赋值,把具体的=右边new出来的数组容器,
                存储到=左边的数组变量中,但是存储的是数组在内存空间的地址值
        (5)new: 创建数组容器的过程
        (6)右侧数据类型: 和左侧保持一致
        (7)右侧[]中长度: 是一个int数字,表示数组中可以存储数据的数量,也叫作数组长度

3.练习:
	(1)创建一个int类型的数组,可以存储3个int数据,给该数组起个名称叫做arrayA
    (2)创建一个double类型的数组,可以存储7个double数据,给该数组起个名称叫做arrayB
    (3)创建一个char类型的数组,可以存储5个char数据,给该数组起个名称叫做arrayC
		
public class Demo03Array {
    public static void main(String[] args) {
        //(1)创建一个int类型的数组,可以存储3个int数据,给该数组起个名称叫做arrayA
        int[] arrayA = new int[3];

        //(2)创建一个double类型的数组,可以存储7个double数据,给该数组起个名称叫做arrayB
        double[] arrayB = new double[7];

        //(3)创建一个char类型的数组,可以存储5个char数据,给该数组起个名称叫做arrayC
        char[] arrayC = new char[5];
    }
}
            

```



##### 1.4 数组的第二种初始化方式

```java
数组的第二种初始化方式(标准格式静态初始化:指定数组中的每个元素)
	1.格式:
    	数据类型[] 数组名称 = new 数据类型[]{元素1,元素2,元素3,...元素n};

    2.注意:
    	(1)右侧[]中不能写长度: JVM会根据{}中元素的数量计算/推导出数组的长度
        	只要右侧[]中写长度,就会报错

        (2){}中的每个元素之间有逗号(英文状态)隔开,最后一个元素后面没有逗号

    3.练习:
    	(1)创建一个int类型的数组,可以存储多个int数据100,200,300,给该数组起个名称叫做arrayA
        (2)创建一个double类型的数组,可以存储多个double数据1.1,2.2,3.3,4.4,5.5,6.6,7.7,给该数组起个名称叫做arrayB
        (3)创建一个char类型的数组,可以存储多个char数据'真','的','好','想','你',给该数组起个名称叫做arrayC
 
public class Demo04Array {
    public static void main(String[] args) {
        //(1)创建一个int类型的数组,可以存储多个int数据100,200,300,给该数组起个名称叫做arrayA
        int[] arrayA = new int[]{100,200,300};

        //(2)创建一个double类型的数组,可以存储多个double数据1.1,2.2,3.3,4.4,5.5,6.6,7.7,给该数组起个名称叫做arrayB
        double[] arrayB = new double[]{1.1,2.2,3.3,4.4,5.5,6.6,7.7};

        //(3)创建一个char类型的数组,可以存储多个char数据'真','的','好','想','你',给该数组起个名称叫做arrayC
        char[] arrayC = new char[]{'真','的','好','想','你'};

    }
}     
            
```



##### 1.5 数组的第三种初始化方式

```java
数组的第三种初始化方式(简化格式静态初始化:指定数组中的每个元素)
	1.格式:
    	数据类型[] 数组名称 = {元素1,元素2,元素3,...元素n};

    2.练习:
    	(1)创建一个int类型的数组,可以存储多个int数据100,200,300,给该数组起个名称叫做arrayA
        (2)创建一个double类型的数组,可以存储多个double数据1.1,2.2,3.3,4.4,5.5,6.6,7.7,给该数组起个名称叫做arrayB
        (3)创建一个char类型的数组,可以存储多个char数据'真','的','好','想','你',给该数组起个名称叫做arrayC

    3.注意:
    	(1)右侧不用写长度,JVM根据{}中数组元素的数量推导长度
        (2)虽然没有写new,底层仍然有new的过程
        (3)动态初始化和标准格式的静态初始化,可以分两步完成
        (4)简化格式静态初始化,不能分成两步完成
	
public class Demo05Array {
    public static void main(String[] args) {
        //(1)创建一个int类型的数组,可以存储多个int数据100,200,300,给该数组起个名称叫做arrayA
        int[] arrayA = {100,200,300};

        //(2)创建一个double类型的数组,可以存储多个double数据1.1,2.2,3.3,4.4,5.5,6.6,7.7,给该数组起个名称叫做arrayB
        double[] arrayB = {1.1,2.2,3.3,4.4,5.5,6.6,7.7};

        //(3)创建一个char类型的数组,可以存储多个char数据'真','的','好','想','你',给该数组起个名称叫做arrayC
        char[] arrayC = {'真','的','好','想','你'};

        //定义int变量,未赋值
        int num;
        num = 10;//赋值
        System.out.println(num);//10
        num = 100;//重新赋值
        System.out.println(num);//100
        System.out.println("-------------------");
        //定义数组变量,未赋值
        int[] arr;
        arr = new int[3];//动态初始化指定数组长度
        arr = new int[]{10,20,30};//标准格式静态初始化

        System.out.println("-------------------");
        int[] arr2;
        //arr2 = {100,200,300};//错误: 简化格式静态初始化,不能分成两步完成

    }
}

```



##### 1.6 数组的使用

```java
简化格式静态初始化数组的使用
	1.数组名称: 代表数组在内存空间的地址值,是一个十六进制的整数数字
    2.索引编号:是一个整数数字
            数组中的每个数据,称之为数组元素
            数组为每个元素进行编号(专业术语叫做索引),该编号从0开始到最大值(数组长度 减 1)
	3.数组元素:
    	数组名称[索引编号]
        举例:
        	array[3]: 数组array中索引编号为3的元素
	4.获取数组长度:
    	数组内部有个length属性,专门记录数组的长度
        数组名称.length: 是一个int数字,代表数组的长度
            
public class Demo06ArrayUse {
    public static void main(String[] args) {
        /*int num = 10;
        System.out.println(num);//10*/

        //创建int数组array,元素分别为10,20,30
        int[] array = {10,20,30};//10的索引编号是0,20的索引编号是1,30的索引编号是2

        System.out.println(array);//[I@1540e19d: 数组在内存空间的地址值,是一个十六进制的整数数字

        //打印10
        System.out.println(array[0]);//打印数组array中索引编号为0的元素值: 10

        //打印20
        System.out.println(array[1]);//打印数组array中索引编号为1的元素值: 20

        //打印30
        System.out.println(array[2]);//打印数组array中索引编号为2的元素值: 30

        System.out.println("--------------");

        //把10 修改成 100
        array[0] = 100;//把整数数字100,存储到数组array中索引编号为0的元素中

        //把20 修改成 200
        array[1] = 200;//把整数数字200,存储到数组array中索引编号为1的元素中

        //把30 修改成 300
        array[2] = 300;//把整数数字200,存储到数组array中索引编号为2的元素中


        //打印100
        System.out.println(array[0]);//打印数组array中索引编号为0的元素值: 100

        //打印200
        System.out.println(array[1]);//打印数组array中索引编号为1的元素值: 200

        //打印300
        System.out.println(array[2]);//打印数组array中索引编号为2的元素值: 300

        //获取数组的长度
        int count = array.length;
        System.out.println("数组长度: "+count);
        System.out.println("数组长度: "+array.length);

        System.out.println(array[array.length-1]);//30
    }
}

```





### 第二章 数组原理内存图【理解】

##### 2.1 java中的内存分配

```java
1.方法区: 存储可以运行的class文件。
2.方法栈: 方法运行时使用的内存，比如main方法运行，进入方法栈中执行。
3.堆内存 存储对象或者数组，new来创建的，都存储在堆内存。
4.寄存器 给CPU使用，和我们开发无关							  不关心
5.本地方法栈 JVM在使用操作系统功能的时候使用，和我们开发无关。		不关心
今天主要使用:
	1.栈内存
	2.堆内存
        
```

##### 图解:

![image-20200515121702080](img/image-20200515121702080.png)

##### 2.2 一个数组内存图

```java
/*
    一个数组内存图

    注意:
	    1.数组名称保存数组在堆内存中的地址值
	    2.通过数组名称找到堆内存中的具体数组,然后通过索引编号找到对应的具体的某个元素

    数组元素有默认值:
        1.整数:       0
        2.小数:       0.0
        3.字符:       空白字符
        4.布尔:       false
 */
public class Demo01OneArray {
    public static void main(String[] args) {
        //创建int数组one,长度为2
        int[] one = new int[2];//第一个元素索引是0,第二个元素索引1

        System.out.println(one);//地址值:[I@1540e19d
        System.out.println(one[0]);//打印数组one中索引编号为0的元素的值,默认值: 0
        System.out.println(one[1]);//打印数组one中索引编号为1的元素的值,默认值: 1

        one[0] = 10;//把整数数字10,存储到数组one中索引编号为0的元素中,默认值0被覆盖
        one[1] = 20;//把整数数字20,存储到数组one中索引编号为1的元素中,默认值0被覆盖

        System.out.println(one);//地址值:[I@1540e19d
        System.out.println(one[0]);//打印数组one中索引编号为0的元素的值: 10
        System.out.println(one[1]);//打印数组one中索引编号为1的元素的值: 20
    }
}

```

##### 图解:

![image-20200515121737000](img/image-20200515121737000.png)

##### 2.3 两个数组内存图

```java
/*
    两个数组内存图(每个数组都有自己独立的内存空间,互不影响,互不干扰)
    
    注意:
	    1.数组名称保存数组在堆内存中的地址值
	    2.通过数组名称找到堆内存中的具体数组,然后通过索引编号找到对应的具体的某个元素

    有两套房子,一套在延庆(钥匙是one),一套在平谷(钥匙是two)
        one: 你自己拿着  打开的是延庆的房子
        two: 你对象拿着  打开的是平谷的房子  
 */
public class Demo02TwoArray {
    public static void main(String[] args) {
        //创建int数组one,长度为2
        int[] one = new int[2];//在北京延庆购买了一套两居室的房子,one是打开这套房子的钥匙

        System.out.println(one);//[I@1540e19d
        System.out.println(one[0]);//0
        System.out.println(one[1]);//0

        one[0] = 10;
        one[1] = 20;

        System.out.println(one);//[I@1540e19d
        System.out.println(one[0]);//10
        System.out.println(one[1]);//20
        System.out.println("--------------");

        //又创建一个int数组two,长度为2
        int[] two = new int[2];//在北京平谷购买了一套两居室的房子,two是打开这套房子的钥匙

        System.out.println(two);//[I@677327b6
        System.out.println(two[0]);//0
        System.out.println(two[1]);//0

        two[0] = 100;
        two[1] = 200;

        System.out.println(two);//[I@677327b6
        System.out.println(two[0]);//100
        System.out.println(two[1]);//200
    }
}
```

##### 图解:省略,就是把一个对象的内存图复制两份,每个数组之间没有任何关系

##### 2.4 两个变量指向一个数组

```java
/*
    两个引用一个数组内存图
    
    注意1.:
	    1.数组名称保存数组在堆内存中的地址值
	    2.通过数组名称找到堆内存中的具体数组,然后通过索引编号找到对应的具体的某个元素

	注意2:
        1.数组名称保存数组在堆内存空间的地址值
        2.使用数组名进行赋值时,传递的是地址值
        3.使用数组名作为方法参数和返回值,传递的都是地址值  --------后面讲解

    有一套房子,在延庆,但是该房子有两把钥匙,分别是one和two
        one: 你自己拿着  打开的是延庆的房子
        two: 你对象拿着  打开的是延庆的房子

 */
public class Demo03SameArray {
    public static void main(String[] args) {
        //创建int数组one,长度为2
        int[] one = new int[2];//在北京延庆购买了一套两居室的房子,one是打开这套房子的钥匙

        System.out.println(one);//[I@1540e19d
        System.out.println(one[0]);//0
        one[0] = 10;
        System.out.println(one);//[I@1540e19d
        System.out.println(one[0]);//10
        System.out.println("--------------");

        /*
            数组变量one保存的是数组在内存空间的地址值,
            赋值给新的数组变量two,导致数组变量one和two保存相同的内存地址,
            操作的是同一个数组

            one相当于是延庆两居室的房子的钥匙,通过钥匙one又配了一把钥匙two
            这样:
                钥匙one和two,打开的都是延庆两居室的房子
                钥匙one: 你自己拿着
                钥匙two: 你对象拿着
         */
        int[] two = one;

        System.out.println(two);//[I@677327b6
        System.out.println(two[0]);//10
        two[0] = 100;

        System.out.println(two);//[I@677327b6
        System.out.println(two[0]);//100
        System.out.println(one[0]);//100
    }
}

```

##### 图解:

![image-20200515121914077](img/image-20200515121914077.png)



### 第三章 数组操作的常见问题【了解】

##### 3.1 数组越界异常

```java
/*
    数组操作的常见问题一:
        数组索引越界(超出了范围)异常
        1.问题描述: java.lang.ArrayIndexOutOfBoundsException类,数组索引越界异常类
        2.产生原因:
            使用索引编号范围数组元素时,给出的索引编号不存在(超出了范围)
            索引编号范围: 最小值是0,最大值是数组长度 减 1 (one.length - 1)
        3.解决方案:
            根据控制台的打印信息,找到出现问题的索引,进行修改
 */
public class Demo01ArrayProblem {
    public static void main(String[] args) {
        //创建int数组array,并初始化
        //int[] one = new int[]{100,200,300};
        int[] one = {100,200,300};//100的索引编号是0,200的索引编号是1,300的索引编号是2
        System.out.println(one);//数组名称one代表数组的内存地址值:[I@1540e19d
        System.out.println(one[0]);//100
        System.out.println(one[1]);//200
        System.out.println(one[2]);//300
        //System.out.println(one[5]);//索引5: 不存在,报出数组索引越界异常
    }
}

```

图解:

![image-20200515151208671](img/image-20200515151208671.png)

##### 3.2 数组空指针异常

```java
/*
    数组操作的常见问题二:
        空指针异常
        1.问题描述: java.lang.NullPointerException类,空指针异常类
        2.产生原因:
            null是一个引用类型的常量,可以给任意类型引用变量赋值,
            当把null赋值给数组变量one之后,数组变量one将不再指向堆内存空间的任何数组,
            也就不可以通过one再访问数组元素,只要访问,报出空指针异常

        3.解决方案:
            (1)不要通过值为null的数组变量,访问数组元素
            (2)根据控制台打印的相关异常信息,找到数组变量是null的地方进行修改,
                让数组变量指向一个堆内存空间的数组,就可以访问数组元素了
 */
public class Demo02ArrayProblem {
    public static void main(String[] args) {
        //创建int数组array,并初始化
        //int[] one = new int[]{100,200,300};
        int[] one = {100,200,300};//100的索引编号是0,200的索引编号是1,300的索引编号是2
        System.out.println(one);//数组名称one代表数组的内存地址值:[I@1540e19d
        System.out.println(one[0]);//100
        System.out.println(one[1]);//200
        System.out.println(one[2]);//300

        one = null;
        System.out.println(one);//null
        //System.out.println(one[0]);//错误: 控制针异常
    }
}

	
```

##### 图解:

![image-20200515151340388](img/image-20200515151340388.png)

### 第四章 数组练习【重点】

##### 4.1 数组遍历

```java
数组遍历：
	就是将数组中的每个元素分别获取出来，就是遍历。遍历也是数组操作中的基石。
public class Demo01EachArray {
    public static void main(String[] args) {
        //创建int数组array,并初始化
        //10的索引编号是0,20的索引编号是1,30的索引编号是2,50的索引编号是3
        int[] array = {10,20,30,50/*,60,70,80,90,100*/};
        System.out.println(array[0]);
        System.out.println(array[1]);
        System.out.println(array[2]);
        System.out.println(array[3]);
        System.out.println("-----------");
        //发现: 以上代码重复,只有索引0到3是不同的
        //可以使用for循环打印0到3的数字
        for (int i = 0; i < 4; i++) {
            System.out.println("索引编号: "+i+", 对应的元素值: "+array[i]);
        }
        System.out.println("-----------");
        //发现: 以上for循环中数字4写死了,可以使用数组的长度代替
        for (int i = 0; i < array.length; i++) {
            //System.out.println("索引编号: "+i+", 对应的元素值: "+array[i]);
            System.out.println(array[i]);
        }

    }
}

```



##### 4.2 求三个int数字的最大值

```java
需求:
	求三个int数字的最大值

实现步骤:
	1.定义3个int变量a,b,c,并分别初始化
    2.假设变量a的值是最大的,把a保存到int变量max中
    3.如果变量b的值大于max,说明max中的值目前不是最大的,把b的值赋值给max
    4.如果变量c的值大于max,说明max中的值目前不是最大的,把c的值赋值给max
    5.打印max的值
public class Demo02Max {
    public static void main(String[] args) {
        //1.定义3个int变量a,b,c,并分别初始化
        int a = 100, b = 200,c = 300;

        //2.假设变量a的值是最大的,把a保存到int变量max中
        int max = a;

        //3.如果变量b的值大于max,说明max中的值目前不是最大的,把b的值赋值给max
        if (b > max) {
            max = b;
        }
        //4.如果变量c的值大于max,说明max中的值目前不是最大的,把c的值赋值给max
        if (c > max) {
            max = c;
        }
        //5.打印max的值
        System.out.println("最大值: "+max);
    }
}

```

图解:

![image-20200515144417507](img/image-20200515144417507.png)

##### 4.3 数组获取最大值元素

```java
需求:
	求int数组元素最大值
        
实现步骤:
	1.创建int数组array,并初始化
    2.假设索引为0的元素是最大的,保存到int变量max中
    3.使用for循环依次获取后面的(从索引1开始)每个元素
    3.1如果当前元素 大于 max 说明max中的值已经不是最大的了
    3.2把当前元素赋值给变量max
    4.for循环结束后打印max的值
public class Demo03ArrayMax {
    public static void main(String[] args) {
        //1.创建int数组array,并初始化
        int[] array = {5,15,2000,10000,100,4000};

        //2.假设索引为0的元素是最大的,保存到int变量max中
        int max = array[0];

        //3.使用for循环依次获取后面的(从索引1开始)每个元素
        for (int i = 1; i < array.length; i++) {
            //3.1如果当前元素 大于 max 说明max中的值已经不是最大的了
            if (array[i] > max) {
                //3.2把当前元素赋值给变量max
                max = array[i];
            }

        }
        //4.for循环结束后打印max的值
        System.out.println("数组最大值: "+max);
    }
}

```

##### 图解分析:

![image-20200429152819315](img/image-20200429152819315.png)

##### 执行流程:

![image-20200515151009936](img/image-20200515151009936.png)

##### 总结

```java
能够知道数组变量的定义格式
    int[] arrayA;	----推荐使用-----
	int arrayB[];

能够使用两种方式完成数组元素的初始化
    数据类型[] 数组名称 = new 数据类型[长度];//动态初始化,指定长度
	int[] array = new int[3];

	数据类型[] 数组名称 = {元素1,元素2,元素3};//简化格式静态初始化	
	int[] array = {10,20,30};

能够知道数组在内存中的初始化过程(了解) 
能够完成数组的遍历操作
能够完成数组的获取最值操作
```

