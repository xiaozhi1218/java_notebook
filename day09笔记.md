# day09 【方法重载、Debug调试】

##### 今日复习指南

```java
1.方法重载用(0.5个小时内完成,多写几遍)
	Demo02MethodOverLoad.java		定义四个重载的求和方法
    Demo05OverLoadTest.java			定义四个重载的判断是否相同的方法
    
2.方法练习(1.0个小时内完成,多写几遍)
    Demo02PrintArray.java			定义方法打印int数组的内容
    Demo03PrintArrayMax.java 		定义方法获取int数组最大值
    
3.方法参数区别和debug调试(0.5个小时内完成,演示效果)
    Demo01DeBugSum.java
    Demo02DeBug.java
```



##### 今日内容

```java
方法的重载【重点】
方法的参数传递【难点】
方法练习【重点】
Debug调试【理解】
```

### 第一章 方法重载【理解】

##### 1.1 方法重载的引入

```java
需求:
	1.定义一个获取两个int数字之和的方法
    2.定义一个获取三个int数字之和的方法
    3.定义一个获取两个double数字之和的方法
    4.定义一个获取三个double数字之和的方法
定义一个获取两个int数字之和的方法
	三要素:
		1.方法名称:     getTwoIntNumSum
        2.参数列表:     int a,int b
        3.返回值类型:   int

发现问题:
	以下四个方法都是完成求和功能,但是参数列表是互不相同的,
	但是我们给每个方法起了一个相当之复杂的名字,
    导致程序员学习和使用方法的成本增加(记不住,太复杂)

解决方案:
    方法重载
public class Demo01MethodProblem {
    public static void main(String[] args) {
        //打印/输出调用方法: 传递常量
        System.out.println(getTwoIntNumSum(10,20));
        System.out.println(getThreeIntNumSum(10,20,30));
        System.out.println(getTwoDoubleNumSum(10.0,20.0));
        System.out.println(getThreeDoubleNumSum(10.0,20.0,30.0));
    }

    //1.定义一个获取两个int数字之和的方法
    public static int getTwoIntNumSum(int a, int b) {
        return a + b;
    }

    //2.定义一个获取三个int数字之和的方法
    public static int getThreeIntNumSum(int a, int b,int c) {
        return a + b + c;
    }

    //3.定义一个获取两个double数字之和的方法
    public static double getTwoDoubleNumSum(double a, double b) {
        return a + b;
    }

    //4.定义一个获取三个double数字之和的方法
    public static double getThreeDoubleNumSum(double a, double b,double c) {
        return a + b + c;
    }
}
	

```



##### 1.2 方法重载的概念

```java
方法重载
	1.概念:
		在同一个类中,多个功能相同,但是参数列表不同的多个方法,可以使用相同的名称,这种多个同名不同参的方法,
		可以同时存在一个类中的现象,就叫做方法重载
            
        比如:
        	比如某个类中已经有了一个名称为method的方法,还可以再定义名称为method的方法,
			但是要求这些名称为method的方法的参数列表必须不同

	2.作用/目的:
		(1)减少程序员的学习和使用成本(原来需要记住四个名称复杂的方法,现在只需要记住一个名称简单的方法)
        (2)减少了方法名称的数量

    3.调用
    	(1)根据名称找到对应的方法
        (2)根据参数的数量找到对应的方法
        (3)根据参数的类型确定最终要调用的方法
                (首先: 做类型完全匹配 其次: 完全匹配的找不到,再做自动类型提升的匹配)
    	
public class Demo02MethodOverLoad {
    public static void main(String[] args) {
        //打印/输出调用方法: 传递常量
        System.out.println(getSum(10,20));
        System.out.println(getSum(10,20,30));
        System.out.println(getSum(10.0,20.0));
        System.out.println(getSum(10.0,20.0,30.0));
    }

    //1.定义一个获取两个int数字之和的方法
    public static int getSum(int a, int b) {
        System.out.println("...两个int.....");
        return a + b;
    }

    //2.定义一个获取三个int数字之和的方法
    public static int getSum(int a, int b,int c) {
        System.out.println("...三个int.....");
        return a + b + c;
    }

    //3.定义一个获取两个double数字之和的方法
    public static double getSum(double a, double b) {
        System.out.println("...两个double.....");
        return a + b;
    }

    //4.定义一个获取三个double数字之和的方法
    public static double getSum(double a, double b,double c) {
        System.out.println("...三个double.....");
        return a + b + c;
    }
}



```

##### 1.3 方法重载的注意事项

```java
方法重载中参数列表不同有哪些情况?
	1.参数数量不同
    2.参数类型不同
    3.多个类型,顺序不同
public class Demo03OverLoadNotice {
    public static void main(String[] args) {
        method(10,10.0);
    }

    //1.此方法只有一个int类型参数
    public static void method(int a) {

    }
    //2.此方法只有两个int类型参数
    //方法2和方法1参数的数量是不同的,可以构成重载
    public static void method(int a,int b) {

    }
    //3.此方法只有一个double类型参数
    //方法3和方法2参数的数量是不同的,可以构成重载
    //方法3和方法1参数虽然都是只有一个,但是类型不同,可以构成重载
    public static void method(double a) {

    }

    //4.此方法有一个int类型参数和一个double类型参数
    public static void method(int a,double b){

    }
    //5.此方法有一个double类型参数和一个int类型参数
    //方法5和方法4,虽然参数都是2个,但是类型的顺序不同
    public static void method(double a,int b){

    }
}

```

```java
方法重载与哪些因素无关?
	1.与参数的名称无关
    2.与返回值类型无关
    3.与修饰符无关

总结：
    在多个方法同名的前提下,
    只看多个方法的参数(除了名称以外)有区别,就构成重载
        
public class Demo04OverLoadNotice {
    public static void main(String[] args) {

    }

    //1.此方法只有一个int类型参数
    public static void method(int a) {

    }
    //2.此方法只有一个int类型参数
    //方法2和方法1,只有参数的名称不同,无法构成重载
    /*public static void method(int num) {

    }*/
    //3.此方法只有一个int类型参数
    //方法3和方法1,只有返回值类型不同,无法构成重载
    /*public static int method(int a) {
        return 0;
    }*/

    //4.此方法只有一个int类型参数
    //方法4和方法1,只有修饰符不同,无法构成重载
    /*void method(int a) {

    }*/
}

```





##### 1.4 方法重载的练习-比较两个数据是否相等

```java
需求:
	使用方法重载的思想，设计比较两个数据是否相等的方法，兼容全整数类型(byte,short,int,long）

实现步骤:
	1.使用方法重载的思想,定义比较两个byte数据的方法compare
    2.使用方法重载的思想,定义比较两个short数据的方法compare
    3.使用方法重载的思想,定义比较两个int数据的方法compare
    4.使用方法重载的思想,定义比较两个long数据的方法compare
    5.分别调用以上四个方法

使用方法重载的思想,定义比较两个byte数据是否相同的方法compare
三要素:
	1.方法名称:    compare
    2.参数列表:    byte a,byte b
    3.返回值类型:  boolean
public class Demo05OverLoadTest {
    public static void main(String[] args) {
        //5.分别调用以上四个方法
        System.out.println(compare(10,20));
        System.out.println(compare((byte)10,(byte)20));
        System.out.println(compare((short)10,(short)20));
        System.out.println(compare(10L,20L));
    }

    //1.使用方法重载的思想,定义比较两个byte数据的方法compare
    public static boolean compare(byte a, byte b) {
        System.out.println("...两个byte...");
        boolean result = (a == b) ? true : false;
        return result;
    }

    //2.使用方法重载的思想,定义比较两个short数据的方法compare
    public static boolean compare(short a, short b) {
        System.out.println("...两个short...");
        boolean result;
        if (a == b) {
            result = true;
        } else {
            result = false;
        }
        return result;
    }

    //3.使用方法重载的思想,定义比较两个int数据的方法compare
    public static boolean compare(int a, int b) {
        System.out.println("...两个int...");
        if (a == b) {
            return true;
        } else {
            return false;
        }
    }

    //4.使用方法重载的思想,定义比较两个long数据的方法compare
    public static boolean compare(long a, long b) {
        System.out.println("...两个long...");
        return a == b;
    }
}
                                      
```



### 第二章 方法的参数传递【理解】

##### 2.1 方法参数传递

```java
参数传递:
	可以理解当我们要调用一个方法时，我们会把指定的数值，传递给方法中的参数(定义方法时()中定义的变量)，
    这样方法中的参数就拥有了这个指定的值，可以使用该值，在方法中运算了。这种传递方式，我们称为参数传递。
        
形式参数: 定义方法时，()中定义的的变量
实际参数: 调用方法时，()中传入给方法的数值/变量

/*
    注意:
        1.使用=进行赋值的特点:
            把基本类型变量a的值赋值给基本类型变量b时,其实是把a中的值复制一份给变量b,
            之后不管如何修改变量b中的值,都不会影响变量a中的值

        2.变量的作用范围:
            方法内部定义的变量只在所定义的方法内有效(可以使用),出了方法的作用范围,就不能使用了
            局部变量: 方法内部定义的变量或者方法定义时()中定义的变量

 */
public class Demo01Var {
    public static void main(String[] args) {
        //定义int变量a,并初始化
        int a = 20;

        //定义int变量b,未初始化
        int b;

        b = a;//把变量a中的值赋值给变量b

        System.out.println("a="+a);//20
        System.out.println("b="+b);//20

        b = b*10;

        System.out.println("a="+a);//20
        System.out.println("b="+b);//200

        method();

        //System.out.println(num);//错误: num是在method方法内部定义,只在method方法内部有效
    }

    public static void method(/*int m*/) {
        int num = 100;
        System.out.println(num);
        //System.out.println(a);//错误: a是在main方法内部定义,只在main方法内部有效
    }
}
	
```

图解:

![image-20200504104632367](img/image-20200504104632367.png)

##### 2.2 基本类型作为方法参数传递

```java
/*
    基本数据类型作为方法参数
    注意:
        1.基本类型变量: 保存的是具体的数据值
        2.基本类型变量作为形式参数,
            形式参数的改变,不会影响实际参数


    基本类型变量作为形式参数:
        定义方法时,()中定义的参数属于基本类型

    不会影响实际参数: 调用方法时,()中给出的参数
 */
public class Demo02BaseVar {
    public static void main(String[] args) {
        int a = 10;
        int b = 20;
        System.out.println("ms...a="+a);//10
        System.out.println("ms...b="+b);//20
        //调用方法
        change( a , b );
        System.out.println("me...a="+a);//10
        System.out.println("me...b="+b);//20
    }

    public static void change(int a, int b) {
        System.out.println("cs...a="+a);//10
        System.out.println("cs...b="+b);//20
        a = a*10;
        b = b*10;
        System.out.println("ce...a="+a);//100
        System.out.println("ce...b="+b);//200
    }
}

```

##### 图解:

![image-20200504105826431](img/image-20200504105826431.png)

![image-20200518111321501](img/image-20200518111321501.png)

##### 2.2 引用类型作为方法参数传递

```java
/*
    引用数据类型作为方法参数
        注意:
            1.引用类型变量: 保存的是对象在堆内存空间的地址值,进行参数传递的时候,传递的也是地址值
            2.引用类型变量作为形式参数,通过形式参数找到对应的堆内存空间,修改堆内存空间的内容之后,
                通过实际参数看到的一定是修改后的堆内存空间的内容

                引用类型作为形式参数,形式参数的改变,会影响实际参数

        数组:
            1.数组也是一种引用类型: 数组名称保存的也是数组在堆内存空间的地址值
            2.数组作为方法参数或者返回值: 传递的都是数组在堆内存空间的地址值

 */
public class Demo03RefVar {
    public static void main(String[] args) {
        int[] arr = { 10 , 20 };
        //System.out.println(arr);//数组名称: 保存数组在内存中的地址值[I@1540e19d
        System.out.println("ms...arr[0]="+arr[0]);//10
        System.out.println("ms...arr[1]="+arr[1]);//20
        //调用方法
        change( arr );
        System.out.println("me...arr[0]="+arr[0]);//100
        System.out.println("me...arr[1]="+arr[1]);//200
    }

    public static void change(int[] arr ) {
        System.out.println("cs...arr[0]="+arr[0]);//10
        System.out.println("cs...arr[1]="+arr[1]);//20
        arr[0] = arr[0]*10;
        arr[1] = arr[1]*10;
        System.out.println("ce...arr[0]="+arr[0]);//100
        System.out.println("ce...arr[1]="+arr[1]);//200
    }
}

```

图解:

![image-20200518113950171](img/image-20200518113950171.png)

### 第三章 方法的练习【重点】

##### 3.1 数组遍历练习(不定义方法)

```java
需求(先不定义方法):
	设计一个方法用于数组遍历(打印数组元素)，
    要求遍历的结果是在一行上的。例如：[11, 22, 33, 44, 55]

举例:
	原数组: {11,22,33,44,55}
    打印格式:[11, 22, 33, 44, 55]
实现步骤:
	1.定义int数组array,并初始化
	2.打印"[",不换行
    3.使用for循环遍历数组
    3.1打印数组当前元素,不换行
    3.2如果步骤3.1中打印的元素不是最后一个元素,则需要打印", ",不换行
    4.打印"]",可以换行也可以不换行

问题:
	并没有把按照指定格式打印数组的功能定义成方法,
    导致有多少个数组需要按照指定格式打印,就需要重复性的写几遍同样的代码

解决方案:
	定义方法,实现数组按照指定格式打印
public class Demo01PrintArray {
    public static void main(String[] args) {
        //1.定义int数组array,并初始化
        int[] array = {11,22,33,44,55};
        //2.打印"[",不换行
        System.out.print("[");

        //3.使用for循环遍历数组
        for (int i = 0; i < array.length; i++) {
            //3.1打印数组当前元素,不换行
            System.out.print(array[i]);
            //3.2如果步骤3.1中打印的元素不是最后一个元素
            if(i != array.length-1) {
                //则需要打印", ",不换行
                System.out.print(", ");
            }
        }

        //4.打印"]",可以换行也可以不换行
        System.out.println("]");

        System.out.println("------------------");
        array = new int[] {100,200,300,500,800,900};

        //2.打印"[",不换行
        System.out.print("[");

        //3.使用for循环遍历数组
        for (int i = 0; i < array.length; i++) {
            //3.1打印数组当前元素,不换行
            System.out.print(array[i]);
            //3.2如果步骤3.1中打印的元素不是最后一个元素
            if(i != array.length-1) {
                //则需要打印", ",不换行
                System.out.print(", ");
            }
        }

        //4.打印"]",可以换行也可以不换行
        System.out.println("]");
    }
}
 
```

##### 3.2 数组遍历练习(定义方法)

```java
需求(定义方法):
        设计一个方法用于int数组遍历(打印数组元素)，
        要求遍历的结果是在一行上的。例如：[11, 22, 33, 44, 55]

举例:
	原数组: {11,22,33,44,55}
    打印格式:[11, 22, 33, 44, 55]

定义方法,用来遍历int数组
	三要素:
    	1.方法名称:     printArray
        2.参数列表:     int[] array
        3.返回值类型:   void

打印int数组方法printArray的实现步骤
	1.打印"[",不换行
    2.使用for循环遍历数组
    2.1打印数组当前元素,不换行
    2.2如果步骤2.1中打印的元素不是最后一个元素,则需要打印", ",不换行
    3.打印"]",可以换行也可以不换行

main方法的实现步骤
	1.定义int数组array,并进行初始化
    2.调用printArray方法,传递数组变量array,完成数组按照指定格式打印

public class Demo02PrintArray {
    public static void main(String[] args) {
        //1.定义int数组array,并进行初始化
        int[] array = {11,22,33,44,55};//array中存储的是: 数组在堆内存空间的地址值

        //2.调用printArray方法,传递数组变量array,完成数组按照指定格式打印
        printArray(array);

        int[] array2 = {100,200,300,500,800,999,9999};
        printArray(array2);
    }

    //打印int数组方法printArray的实现步骤
    public static void printArray(int[] array) {
        //1.打印"[",不换行
        System.out.print("[");

        //2.使用for循环遍历数组
        for (int i = 0; i < array.length; i++) {
            //2.1打印数组当前元素,不换行
            System.out.print(array[i]);

            //2.2如果步骤2.1中打印的元素不是最后一个元素,则需要打印", ",不换行
            if (i != array.length - 1) {
                System.out.print(", ");
            }
        }
        //3.打印"]",可以换行也可以不换行
        System.out.println("]");
    }
}
 
```



##### 3.2 方法练习求数组最大值

```java
需求:
	设计一个方法用于获取int数组中元素的最大值

举例:
	原数组: {11,22,33,44,55}
	最大值: 55
        
三要素:
	1.方法名称:     getArrayMax
	2.参数列表:     int[] array
	3.返回值类型:   int

方法getArrayMax的实现步骤:
	1.假设索引0对应的元素是最大的,保存到int变量max中
	2.使用for循环依次获取后面的(从索引1开始)每个元素
	2.1只要当前元素值 大于 max,说明max中的值,已经不是最大的了
	2.2把当前元素值 赋值给 变量max
	3.for循环结束后,返回max

main方法实现步骤:
	1.定义int数组array,并初始化
	2.调用getArrayMax方法,传递数组array,获取最大值,保存到int变量max中
	3.打印最大值max
        
public class Demo03PrintArrayMax {
    public static void main(String[] args) {
        //1.定义int数组array,并初始化
        int[] array = {100,200,300,800,500};

        //2.调用getArrayMax方法,传递数组array,获取最大值,保存到int变量max中
        int max = getArrayMax(array);//数组名array: 存储数组在堆内存中的地址值

        //3.打印最大值max
        System.out.println("数组元素最大值: "+max);
    }

    //设计一个方法用于获取一个int数组中元素的最大值
    public static int getArrayMax(int[] array) {
        //1.假设索引0对应的元素是最大的,保存到int变量max中
        int max = array[0];

        //2.使用for循环依次获取后面的(从索引1开始)每个元素
        for (int i = 1; i < array.length; i++) {
            //2.1只要当前元素值 大于 max,说明max中的值,已经不是最大的了
            if (array[i] > max) {
                //2.2把当前元素值 赋值给 变量max
                max = array[i];
            }
        }
        //3.for循环结束后,返回max
        return max;
    }
}

```



##### 3.3 引用类型变量作为方法参数方法调用图解

![image-20200518142225434](img/image-20200518142225434.png)



### 第四章 Debug调试【重点】

##### 4.1 Debug查看求和

```java
使用步骤:
1.在代码的第一行左侧空白(行号后面)处单击鼠标左键,添加断点
2.右键选择"debug...",进入断点调试界面

public class Demo01DeBugSum {
    public static void main(String[] args) {

        System.out.println("main...start....");
        int a = 10;
        int b = 20;

        int sum = a + b;

        System.out.println("sum="+sum);

        System.out.println("main...end....");
    }
}

```



##### 4.2 Debug查看求和方法

```java
public class Demo02DeBug {
    public static void main(String[] args) {

        System.out.println("main...start...");

        method();

        System.out.println("main...end...");
    }

    public static void method() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
        }
        return ;
    }
}

```



![image-20200410151007486](img/image-20200410151007486.png)



##### 总结

```java
能够知道方法重载的特点
    1.概念:
		在同一个类中,多个功能相同,参数列表不同的方法,可以使用相同的名称
            
    2.参数列表不同有哪些情况:
		(1)数量不同
        (2)类型不同
        (3)多个类型,顺序不同
            
    3.与哪些因素无关:		
        (1)与参数名称无关
        (2)返回值类型无关
        (3)修饰符无关
            
能够使用方法重载完成比较两个整数是否相同并调用方法
    public static boolean compare(int a,int b) {
    	return a == b;        
    }
	public static boolean compare(long a,long b) {
    	return a == b;        
    }
	//...
   
能够使用方法完成数组遍历并调用方法
能够使用方法完成获取int数组最大值并调用方法
    
能够使用断点调试查看循环求和流程
	使用步骤:
		1.在代码的第一行左侧空白(行号后面)处单击鼠标左键,添加断点
		2.右键选择"debug...",进入断点调试界面
    
能够知道方法的参数是基本类型和引用类型的区别
    1.方法参数是基本类型: 形式参数的改变,不会影响实际参数
    2.方法参数是引用类型: 形式参数的改变,会影响实际参数
```

