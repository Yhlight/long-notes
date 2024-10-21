# 严格说明
1. **在编程中，严格区分中英文字符，请自行安装一个英语输入法**  
2. **如果你有学习过其他语言，请不要吝啬你的学识，进行一定程度的迁移运用**  
3. **此篇笔记不会记录计算机基础知识**  

# IDEA常用快捷键
1. **CTRL+ALT+L  文件格式化（自动对齐等功能）**
2. **CTRL+/  行注释**
3. **SHIFT+F10  编译**

## 常见的DOS命令
WIN+R唤起运行窗口，输入CMD，打开CMD窗口  

如果需要使用管理员权限，需要在运行窗口输入cmd时，按下CTRL+SHIFT+ENTER，打开拥有管理员权限的CMD窗口  

### DOS命令  
#### 进入与回退
1. 切换盘符  
驱动盘符号 + :  
将路径切换到指定的驱动盘  
例如：E:  
注意，只有访问当前盘中的路径才能够使用\yhlight这种无盘符的路径，否则需要写出盘符  

2. 列出文件  
dir + 目录  
列出当前目录下的文件以及文件夹  
例如：dir \yhlight  

3. 进入某目录  
cd + 目录  
例如：cd \yhlight  

4. 进入多级目录  
cd + 多级目录  
例如：cd \yhlight\yh-phobos-master  

5. 回退上一个目录  
cd..  
例如：  
cd \yhlight\yh-phobos-master  
cd..  
目录更新为->\yhlight  

6. 回退至盘符目录  
cd + /或\  
例如：cd / 或cd \  

7. 跨盘符访问  
cd + /d + 其他盘符目录  
例如：cd /d E:\yhlight\yh-phobos-master  

#### 创建与删除
1. 创建  
md + 文件目录名  
md + 某文件  
例如：md \Users\yingh\yinghuolight  

2. 删除  
rd + 文件目录名  
rd + 某文件  
例如：rd xxx.txt  

#### 其他操作
1. 清屏  
cls  

2. 退出命令行窗口  
exit  

3. 调用前后使用过的指令  
↑ ↓（键盘按键）  

4. 删除  
del + 文件目录名  
del + 某文件  

5. 删除同后缀名文件  
del + *.后缀  
例如：del *.txt  
***
## JAVA开发环境的搭建
### JKD的安装（自行选版本）
https://www.oracle.com/cn/java/technologies/downloads/  
进入这个链接后，你可以选择安装高版本JAVA，也可以选择安装JAVA 8  
需要下载的是Windows版本
[![pA3VG0U.png](https://s21.ax1x.com/2024/09/30/pA3VG0U.png)](https://imgse.com/i/pA3VG0U)  

如果你想要安装JAVA 8，请继续往下浏览页面
[![pA3V8mT.png](https://s21.ax1x.com/2024/09/30/pA3V8mT.png)](https://imgse.com/i/pA3V8mT)  

### 路径相关的配置（必要）
JAVA可以安装在任意一个盘，只不过更推荐安装在系统盘，安装在系统盘可以避免很多问题，没必要为了担心一些微不足道的问题而安装在其他盘，具体自行选择  

### JAVA目录的简单认识
**bin**  
这个文件夹放着开发工具，这也是为什么编译与运行java文件要放进bin文件  

**include**  
包含一些库文件  

**jre（java8）**  
这个文件夹JAVA8会有，JAVA8之后的版本没有这个文件夹，高版本那边jre被打散在相关的目录中，jre这个文件夹里面放着运行时的环境文件  

**legal**  
放着一些法律上的条文  

**lib**  
里面放着java包，里面集成了很多指令  

**conf（高版本）**  
存放一些配置文件，这些会影响java的运行  

**jmods（高版本）**  
用于存放JMOD文件。这些JMOD文件是Java模块的打包格式，包含了模块的类、资源、配置文件以及其他与模块相关的信息。  

**源代码**  
目录下有一个名叫src的压缩包，里面放着java的源代码，找不到不用找，反正你用不上  

***

### 配置Path环境变量
**什么是Path环境变量?**  
Path环境变量是window操作系统执行命令时，所要搜寻的路径  

**为什么要配置Path环境变量?**  
希望在命令行使用Java工具时，在任意目录之下都能找到工具包的目录  
好比如说，如果没有设置Path环境变量，编译java文件需要在bin文件目录下进行  
例如  
cd C:\Program Files\Java\jdk-22\bin  
javac test.java  
java test  
需要这样才可以正常运行  
这样对开发很麻烦，肯定是不希望每次都要把java文件丢进bin目录之中再进行运行  

#### 如何配置Path环境变量?
右键此电脑，属性，高级系统设置，环境变量  
此电脑可以在打开任意一个目录后，在左侧的总览目录中找到  

在系统变量中，新建一个变量，名叫JAVA_HOME
变量的值为**Java目录的路径**  
例如  
变量名 JAVA_HOME  
值 C:\Program Files\Java\jdk-22  

然后在系统变量中，你可以找到Path这一栏，点击进行编辑，新建，然后粘贴这一句  

>%JAVA_HOME%\bin  

之后一路返回并保存确认就好了  

这里面其实有一个措施，可以自行选择是否弄，Path环境变量是从上往下进行读取的，为了避免其他与java相关的东西把它挤下去，你可以将它上移到最上边  

***

## Java学习篇
### 你的第一个程序-打印HelloWorld
Java文件是如何编写和运行的？  
首先，你需要通过记事本等文件软件来写Java代码，这里推荐使用[visula studio code](https://code.visualstudio.com/)  

你只需要右键新建一个txt，然后更改为java后缀的文件，再进行编写就可以了，注意，要打开显示扩展名，否则无法进行后缀的更改  

然后使用javac命令将java文件进行编译，生成class（字节码文件）文件  

接着使用java命令运行生成的class文件  

### HelloWorld的打印
将txt命名为HelloWorld.java，注意HelloWorld只是一个名字，可以任意更换，但是需要和代码之中的 **类（class）** 的名字相同，具体往下看  
```
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("HelloWorld");
    }
}
```
这就是打印HelloWorld需要的代码，注意，Java代码是严格区分**大小写**的，class后面接的HelloWorld就是**类**的名字，你可以随意修改，但是最好是和文件名字相同  

举个例子  
文件名字 HelloWorld.java  
类的名字 HelloChina  

javac HelloWorld.java  
生成的class是HelloChina.class  

java HelloChina  
运行需要输入类的名字（要完全相同），而不是文件名字  
明显，这繁琐许多，同时，不仅仅是这些问题，这里进行相关的一些解析  
1. public类一致性需求  
你可以看到，上面的代码是class + 类名，然而，在Java中，还会使用public class + 类名  
在Java中规定，public class 的**类名**要和**文件名**完全相同  

2. 组织性，IDE支持，避免冲突等的需求  

说完这些，现在说一下怎么运行程序  
WIN+R唤起运行窗口，输入CMD，打开CMD窗口  

如果需要使用管理员权限，需要在运行窗口输入cmd时，按下CTRL+SHIFT+ENTER，打开拥有管理员权限的CMD窗口  

检查一下你java文件所在的位置，这里需要你有一些DOS命令的知识，文件的开头就是，这里用一个简单的例子来说明  

d:  
cd D:\yhlight  
javac HelloWorld.java  
java HelloWorld  

打印一个HelloWorld你已经学会了，接下来讨论一下一些相关问题  
1. 为什么HelloWorld需要用双引号？  
这是字符串，字符串需要用双引号  
2. 可不可以打印中文  
当然可以！不过你要检查一下你保存的那个文件的字符编码，cmd使用的字符编码是ASNI，想要cmd正常显示中文，你需要更改你的java文件的字符编码为ASNI，请不要自作聪明，**高版本**是不需要设置就可以输出中文了的，只有在**不行时才需要这么做**  

你可以通过以下方法进行更改  
1. 记事本另存为时，更改文件的字符编码  
2. 设置cmd字符编码  
`chcp 65001`  
1. 运行java时设置编码  
`java -Dfile.encoding=UTF-8 HelloWorld`  

#### 打印HelloWorld代码相关补充
**公共类的使用**  
```
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("HelloWorld");
    }
}
```

**println与print**  
System.out.println("HelloWorld");  
println 输出数据后**进行**换行  

System.out.print("HelloWorld");  
print 输出数据之后**不进行**换行  

**一个文件多个类**  
一个文件允许有多个类，但只允许一个存在一个**公共类**，同时，类之间不能同名  
```
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("HelloWorld");
    }
}

class HelloJava {

    }

class HelloAlice {

    }
```

***

## 注释
### 单行注释 //
用来解释单行代码或使某部分代码不被编译器读取  
// 后面跟的内容不会被编译器读取  

### 多行注释
/*          */  两个符号间的代码全部被注释  
如下  
```
/*
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("HelloWorld");
    }
}
*/
```

### 文档注释（java独有）
```
/**

*/
```
文档注释内容可以被JDK提供的工具javadoc所解析，生成一套以网页文件形式体现的该程序的说明文档。  

文档注释可以用来生成一套网页的介绍信息  
例如  
```
/**
我的首个java程序
@author yinghuolight
@version 1.0
*/

public class HelloWorld {
    /**
    这是main方法，一个类可以有多个方法
    */
    public static void main(String[] args) {
        System.out.println("HelloWorld");
    }
}
```

使用cmd来生成需要使用以下指令  
>javadoc -d mydoc -author -version HelloWorld.java  

mydoc是生成的文件夹名字，随意更改  
这指令只是包括了两个常用的参数，还有很多参数需要自行去探索   
可以尝试使用idea去生成doc文件  

***
## JAVA API文档
API是Java提供的基本编程接口  
Java提供了大量的基础类，可以通过API文档来查阅  

API地址：https://docs.oracle.com/en/java/javase/22/docs/api/index.html  

这里拿的是java22来作为实例，你可以更换22为其他数字以查阅其他版本的API  

也可以通过这个链接来到总览页面 https://docs.oracle.com/en/java/javase  

***
### 学前实例
#### 输出个人信息
```
public class Introduction {
    public static void main(String[] args) {
        System.out.println("姓名：展扬呀");
        System.out.println();
        System.out.println("家里蹲大学在读生，负责文案及相关程序");
        System.out.println("第一次席");
    }
}
```

## 第一大章 变量与运算符
### 标识符
#### 何为标识符
Java中变量、方法、类等要素命名时使用的字符序列，称为标识符  

#### 标识符命名准则
1. 由26个英文字母大小写，0-9，_或$组成  
2. 数字不可以作为开头  
3. 不可以使用关键字和保留字，但能包含关键字和保留字  
4. 严格区分大小写，长度无限制  
5. 不能包括空格  

#### 标识符命名规范
包名：多单词组成时所有字母都小写  
例如: java.lang，com.atguigu.bean  

类名、接口名：多单词组成时，所有单词的首字母大写  
例如: HelloWorld，String，System  

变量名、方法名：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写  
例如: age，name，bookName，main，binarySearch，getName  

常量名：所有字母都大写，多单词时每个单词用下划线连接  
例如: MAX_VALUE，PI，DEFAULT_CAPACITY  

### 变量
#### 变量的类型
##### 基本数据类型
整型  
1. byte  
2. short  
3. int  
4. long  

浮点型  
1. float  
2. double  

字符型  
1. char  

布尔型  
1. boolean  

##### 引用数据类型
类（class）  
数组（array）  
接口（interface）  
枚举（enum）  
注解（annotation）  
记录（record）  

#### 定义变量的细则和规范
变量：内存中的一个存储区域，该区域的数据可以在同一类型范围内不断变化  
变量的三个要素：数据类型，变量名，存储的值  
变量的声明：`数据类型 变量名 = 变量值`  
变量的意义：给一段指定的内存起名，方便操作这段内存  

局部变量：方法内部定义的变量  
全局变量：方法之外定义的变量  

作用域：变量的作用范围  
简单来说就是变量所在的大括号范围  
在这个大括号内变量可以使用  
全局变量的作用域是当前文件  

```
public class Test {
    public static void main(String[] args) {
        int i;
        i = 40;
        int j = 0;
        j = i + 40;
        int sum = i + j;
        char a = 'A';
        System.out.println(i + j);
        System.out.println("i + j = " + sum);
        System.out.println(a);
        //System.out.printf("%d", i);
    }
}
```

##### 定义变量的细则
1. 变量必须要先进行声明再进行使用  
2. 局部变量在使用之前一定要进行初始化  
3. 变量都有它们的作用域，出了作用域范围后无法使用  
4. 变量都有相应的范围，不要跃出范围  

#### 基本数据类型的介绍
**整数类型：byte，short，int，long**  

|类型|占用存储空间|范围|
|:-:|:-:|:-:|
|byte|1个字节（8个bit）|-128 ~ 127|
|short|2个字节|-2^15 ~ 2^15-1|
|int|4个字节|-2^31 ~ 2^31-1|
|long|8个字节|-2^63 ~ 2^63-1|

定义long类型的变量，赋值时要以"l"或者"L"作为后缀  
Java程序中变量通常声明为int类型，除非范围不够  
Java的整型默认为int型  

##### 计算机的存储单位
**字节（byte）** 计算机用于计量存储容量的基本单位，一个字节等于8个bit  
**位（比特位/bit）** 数据存储的最小单位  

**浮点类型：float，double**  
|类型|占用存储空间|范围|
|:-:|:-:|:-:|
|单精度float|4个字节|-3.403E38 ~ 3.403E38|
|双精度double|8个字节|-1.798E308 ~ 1.798E308|

浮点型有两种表现形式：  
十进制数：5.12，512.0f，.512  
科学计数法：5.12e2，512E2，100E-2  

float尾数可以精确到7位有效数字，在很多情况下，精度很难满足  
double精度是float的两倍（double的精度约为15-16位）  

定义float类型的变量，赋值要需要以"f"或"F"作为后缀  
Java的浮点型默认为double类型  

##### 浮点数精度的说明
并不是所有的小数都能精确地用二进制浮点数表示，例如10的负次幂  

浮点类型float，double并不适应于**不容许舍入误差**的金融计算，对于需要精确数字计算或者保留特定位数的精度，需要用**BigDecimal**类  

一些精度相关的实例说明  
这个例子大多数语言都是一样的，不信去试试  
```
public class Test {
    public static void main(String[] args) {
        System.out.println(0.1 + 0.2);
    }
}
```

***

```
public class Test {
    public static void main(String[] args) {
        float ff1 = 123123123f;
        float ff2 = ff1 + 1;
        System.out.println(ff1);
        System.out.println(ff2);
        System.out.println(ff1 == ff2);
    }
}
```

##### 浮点型实例
定义圆周率并赋值为3.14，现在有三个圆的半径为1.2，2.5，6，求它们的面积  
```
public class FloatDoubleExer {
    public static void main(String[] args) {
        double pi = 3.14;
        double r1 = 1.2;
        double r2 = 2.5;
        double r3 = 6.0;
        double s1 = pi * r1 * r1;
        double s2 = pi * r2 * r2;
        double s3 = pi * r3 * r3;
        System.out.println("圆1的面积为" + s1 + " 圆2的面积为" + s2 + " 圆3的面积为" + s3);
    }
}
```
如果可以，请使用单词代替r1，s1  

将华氏温度(80度)转换为摄氏度，并以华氏度和摄氏度为单位分别显示该温度  
**℃=(℉ - 32) / 1.8**  
```
public class FloatDoubleExer {
    public static void main(String[] args) {
        double degreeFahrenheit = 80.0;
        double degreeCentigrade = (degreeFahrenheit - 32) / 1.8;
        System.out.println("华氏温度为" + degreeFahrenheit + "℉");
        System.out.println("摄氏温度为" + degreeCentigrade + "℃");
    }
}
```

#### 字符类型
char类型数据用来表示存储并表示字符，占用两个字节  
Java中所有字符都使用Unicode编码，故一个字符可以存储一个字母，汉字，或符号  

字符型变量一般有四种表现形式  
1.使用单引号('')括起来的单个字符  
例如：  
```
char c1 = 'a';
char c2 = '中';
char c3 = '9';
```

2.直接使用Unicode值（\uXXXX）来表示字符型常量  
XXXX表示一个十六进制整数  

3.Java允许使用转义字符'\'来将字符转变成特殊字符型常量  
`char c3 = '\n';  //\n表示换行`  
人话就是转义字符  

4.ASCII码

#### 布尔类型
boolean类型用来判断逻辑条件  

一般用于这些场景  
1. if条件  
2. while循环  
3. for循环  
4. do while循环  

boolean类型数据只有两个值：true或flase  
不可以使用0或非0的整数代替，这和C语言不同  

扩展：Java虚拟机中没有任何供booleamn值专用的字节码文件，在虚拟机中会把true和flase认为成int替代的整数，即0/1  

```
public class Test {
    public static void main(String[] args) {
        boolean isMarried = true;
        if (isMarried) {
            System.out.println("不可忘却的时刻");
        } else {
            System.out.println("友谊常在");
        }
    }
}
```

#### 基础数据类型运算规则
基础数据类型变量间运算存在着一定的运算规则  
其中包括：  
1.类型提升  
2.强制类型转换  
3.连接  

##### 类型提升
当容量小的变量与容量大的变量做运算时，结果自动转换为容量大的数据类型  
这个容量指的是范围大小，而不是占用的内存大小  
```
public class VariableTest {
    public static void main(String[] args) {
        int i1 = 10;
        int i2 = i1;
        long l1 = i1;
        float f1 = l1;
    }
}
```

`byte,char,short -> int -> long -> float -> double`  

char类型之间运算照样会进行类型提升  
如果你的赋值操作超出原类型范围，不会发生类型提升  
例如：  
long test1 = 123123123123;  
123123123123没有'l'或'L'的后缀，这是int类型，按照原情况，会发生类型提升，转换成long类型，但由于这个值超出了int类型的范围，所以发生报错，没有发生类型提升，float类型不写后缀不会自动类型提升，因为浮点数默认double类型  

整型常量默认为int类型  
浮点型常量默认为double类型  

#### 强制类型转换
有什么办法让范围大的类型的转变成范围小的类型？  
这个时候需要用到强制类型转换
`int i1 = (int) 3.14;`  

##### 精度损失
强制类型转换有可能造成精度损失  
好比如浮点型转成整型会丢掉小数部分，这个措施叫截断  

以下情况会发生精度损失  
1. 浮点型转换整型  
2. 转换的类型范围过小  
```
int i1 = 128;
byte b1 = (byte) i1;
```
byte的范围是-128 ~ 127  
那么最终输出结果是多少？  
-128，最终输出结果是-128  
至于为什么，那就要了解原码反码补码（自己去了解）了  

首先，i1是int类型，int类型占用4个字节  
那么它的二进制表示形式是  
00000000000000000000000010000000  

而byte占用1个字节  
它的二进制形式只有8位  
只能存储10000000  

内存中存放的是补码，打印或显示在屏幕上的是原码  
这里面就需要补码向原码进行转换  
补码等于原码取反+1，然而，对于8个二进制位的10000000来说  
得碍于符号位不参与运算，无法进行补码向原码进行转换  
于是计算机定义8位二进制10000000为-128  
这就是为什么最终输出结果是-128  

等学到后面自然就知道了，这里只是简单说明  

#### 连接
`System.out.println();`在使用中有一个特别的运算  
常量或变量与字符串相加是连接在一起而不是得到运算后的结果  
这需要你使用括号来避免这种情况  
学到String类会知道  
好比如说  
```
public class AirExer {
    public static void main(String[] args) {
        System.out.println("abc" + 5 + 5);
        //输出结果是abc55
        System.out.println("abc" + (5 + 5));
        //输出结果是abc10
    }
}
```

### String类
String不属于基本数据类型，属于引用数据类型  

`String s1 = "字符串";`  

字符串：由一个或多个字符组成并被双引号括起来的字符或字符串  
Java允许字符串为0个字符  
```
public class StringTest {
    public static void main(String[] args) {
        String s1="a";
        String s2="aa";
        String s3="";
        String s4="我是展扬";
        System.out.println(s1);
        System.out.println(s2);
        System.out.println(s3);
        System.out.println(s4);
    }
}
```

#### String与基本数据类型变量之间的运算
String与基本数据类型变量都能够进行运算，但String只能与基本数据类型变量进行连接运算，使用"+"表示  
例如：  
```
public class StringTest {
    public static void main(String[] args) {
        int num = 10;
        boolean b1 = true;
        String s1 = "我是展扬";
        String s2 = s1 + b1 + num;
        System.out.println(s1 + num);
        System.out.println(s1 + b1 + num);
        //不允许System.out.println(b1 + num + s1);
        //这违反了基本数据类型运算规则
        System.out.println(s2);
    }
}
```

String允许与整型相连接，最终输出字符整型  
但在实际运用中，有可能需要让字符10恢复为数字10，这需要使用Integer类  
```
public class StringTest {
    public static void main(String[] args) {
        int num = 10;
        String s1 = "";
        String s2 = s1 + num;
        System.out.println(s2);
        //最终输出"10"，字符10
        int num2 = Integer.parseInt(s2);
    }
}
```
##### String类的练习
**输出个人信息**
```
public class StringExer {
    public static void main(String[] args) {
        String name = "Rainbow";
        int age = 21;
        char gender = '男';
        double weight = 65;
        boolean isMarried = false;
        String phoneNumber = "11451419810";
        System.out.println("姓名：" + name + " "
                + "年龄：" + age + " "
                + "性别：" + gender + " "
                + "体重：" + weight + " "
                + "是否已婚：" + isMarried + " "
                + "电话号码：" + phoneNumber);
    }
}
```

### 计算机的存储
计算机中存储和运算的所有数据都要转为二进制，二进制是计算机的基础  

生活中常用的进制有以下几种  
1.十进制  
数字组成：0-9  
进位规则：逢10进1  

2.二进制  
数字组成：0-1  
进位规则：逢2进1，0b或0B开头（Java表示方法）  

3.八进制  
数字组成：0-7  
进位规则：逢8进1，0开头（Java表示方法）  

4.十六进制  
数字组成：0-9，a-f（不分大小写）  
进位规则：逢16进1，0x或0X开头  
```
public class BinaryTest {
    public static void main(String[] args) {
        int num1 = 103;
        int num2 = 0b10;
        int num3 = 023;
        int num4 = 0x23a;
        System.out.println(num1);
        System.out.println(num2);
        System.out.println(num3);
        System.out.println(num4);
    }
}
```
#### 二进制
在Java中，这是一个二进制表示的10
0b00000000000000000000000000001010  
0b是Java辨识为二进制的标志  
00000000000000000000000000001010是10的二进制表示方法  

int类型占用空间内存4个字节，即32个bit位，二进制里面每一位都是比特位  
二进制位中，最左一位是符号位，0为正，1为负  
00000000000000000000000000001010  //最左一位  

**二进制转换十进制**  
00001010  这是10的二进制表示方法，二进制如何转换成十进制？
你可以通过以下示例来得出结论  
```
1*2^3+0*2^2+1*2^1+0*2^0=10

1 * 2 ^ 3 + 1 * 2 ^ 1 = 10
```
通过上述例子你应该已经知道二进制是如何换算十进制了的  

#### 原码反码补码
原码，反码，补码  
数据在内存中的储存方式为补码  
而呈现出来的数字则是原码  
原码，反码，补码与二进制有关  
二进制位中，最左位决定正负  
正数的原，反，补码均不变  
负数的反码为符号位不变，每一位取反  
负数的补码为该数绝对值取反再加1  

实例：  
85  
原码：0000000001010101  
反码：0000000001010101  
补码：0000000001010101  

-85  
原码：1000000001010101  
反码：1111111110101010  
补码：1111111110101011  

-144  
原码：1000000010010000  
反码：1111111101101111  
补码：1111111101110000  

负数补码的规律是该数绝对值取反再加1  
综合-85及-144的补码，可以得到加1的规律为  
1111111110101010+0000000000000001=1111111110101011  
结尾为0直接变更为1  
1111111101101111+0000000000000001=1111111101110000  
当结尾为1时，加1会变为2  
但二进制仅由0/1组成，无法出现0/1之外的数字  
此时要应用逢二进一规则  
即本位为2时，向前进一位1，同时本位归零  

数据存放补码的原因  
计算机处理器中是没有减法的处理，只是有加法的处理  
在计算机中相关的减法运算都是加法模拟的  
这一点直接说明了补码的重要性  
好比如说，1-1  
1      00000001  
-1     10000001  
1+(-1) 10000010  
最终结果是-2，如果使用原码来进行运算  

如果是补码  
1      00000001  
-1     11111111  
1+(-1) 00000000  
最终结果是0  

如果要从更深层来说，可以这么讲  
在计算机系统中，使用补码，可以将符号位和数值域统一处理  
同时，加法和减法也可以统一处理  
此外，补码和原码相互转换，其运算过程是相同的，不需要额外的硬件电路  

### 操作符/运算符
#### 算术操作符  
```
+    -    *    /    %
加   减   乘   除   取余
```

`前置++  后置++  前置--  后置--`  
++a和a++有着很大区别  
前后是赋值的先后，++a是先赋值，后使用  
a++先使用，后赋值  
例：  
int a = 10;  
int b = ++a;  //先赋值，后使用，b = 10，a再=11  

例如2：  
int a = 10;  
int b = a++;  
先使用后赋值，这里b=11，a=11  

#### 位操作符  
```
<<         >>
左移操作符 右移操作符

&      |      ^
按位与 按位或 按位异或

~  
按位取反
```
位操作符都是对二进制位进行更改  
左右移，二进制位进行左移右移，n >> 3表示右移三位  

右移操作符有两种移动方式  
1.算术右移  
右边丢弃，左边补原符号位  
这一种用于有符号的  
2.逻辑右移  
右边丢弃，左边补零  
这一种用于无符号的  
例如：  
0000000000000011  
n << 3  
0000000000011000  

1111111111111101  
n >> 3  
1111111111111111

左移操作符也有这两种，只是不需要考虑符号位，只需要在右边填补0  

按位与的作用是对两者的二进制位进行比较，若此位两者皆为0，则此位为0  
若此位两者分别为1,0，则此位为0，若此位两者皆为1，则此位为1，重新组成一个二进制位  
例如：  
```
int a = 3 & 5;  
3   0000000000000011  
5   0000000000000101  
a   0000000000000001  
```
a的结果为1  

按位或的作用是对两者的二进制位进行比较，若此位两者之中至少有一位为1，则此位为1  
若两者皆为0，则此位为0，重新组成一个二进制位  

按位异或的作用对两者的二进制位进行比较，若此位两者相同，则此位为0，若此位两者不同  
则此位为1，重新组成一个二进制位  

按位取反就是0变1，1变0，包括符号位  

#### 赋值操作符  
```
=   +=   -=   *=   /=   %=   <<=   >>=   &=   ^=   |=
```
+= ^=这类属于复合赋值，具体意思对应上文再结合赋值便可知道  
例如 int a = 2  a = a + 5 -> a += 5  
在Java中，+=同样可以被理解成m += 5 -> m = m + 5  
但是不同的是，m += 5不需要考虑类型问题，Java自动更改了类型  
而m = m + 5则需要考虑类型提升等问题  
所以说下面这种会报错的情况反而是可以的  
这一点和C语言是不同的  
```
public class ArbitraryTest {
    public static void main(String[] args) {
        byte a = 5;
        a += 5;  //允许
        //a = a + 5;  不允许
        System.out.println(a);
    }
}
```
让一个数自增推荐选m += 5这种形式  

#### 逻辑运算符  
```
&和&&  |和||  !          ^
并     或者   逻辑相反    异或
```
&是逻辑与，左右的表达式都会进行计算  
&&是短路与，当左侧满足时，右侧不再理会  
哈？你问为什么要写&&和&，那是因为我一开始压根就没写&  

逻辑运算符针对的都是boolean类型的变量进行的操作  
逻辑运算符运算的结果也是boolean类型  
```
public class ArbitraryTest {
    public static void main(String[] args) {
        int a = 20;
        int b = 20;
        boolean bo1 = (++a % 3 == 0) && (a++ % 7 == 0);
        System.out.println("a=" + a + " bo1=" + bo1);
        boolean bo2 = (b++ % 3 == 0) && (++b % 7 == 0);
        System.out.println("b=" + b + " bo2=" + bo2);
    }
}
```

#### 关系运算符  
```
==   !=     >    <    >=     <=
等于 不等于 大于 小于 大于等 小于等
```
Java中，=是赋值，==才是等于  

#### 条件运算符
`(条件表达式)?表达式1:表达式2`  
条件表达式如果是true，运算结果是表达式1，否则是2  

#### 运算符综合练习
输出某个三位数的个，十，百位  
```
public class AirExer {
    public static void main(String[] args) {
        int num = 153;
        int re1 = num % 10;
        int re2 = num / 10 % 10;
        int re3 = num / 100;
        System.out.println(re1);
        System.out.println(re2);
        System.out.println(re3);
    }
}
```
请问89个小时等于多少天多少小时  
```
public class AirExer {
    public static void main(String[] args) {
        int num = 89;
        int day = num / 24;
        int hour = num % 24;
        System.out.println(day + "天" + hour + "小时");
    }
}
```
***
## Scanner类
Scanner是官方提供的一个类，用来获取和解析用户输入的数据  
你可以通过Scanner来获取键盘的输入  

### 如何使用Scanner
**导入包**  
`import java.util.Scanner;`  
在文件的开头书写，导入Scanner包  

**创建类实例**  
`Scanner 变量名 = new Scanner(System.in);`  

**调用类方法**  
如果你需要接收一个字符串，你可以使用next()或nextLine()  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        String str1 = "荧火light";
        Scanner scan = new Scanner(System.in);
        str1 = scan.next();
        //str1 = scan.nextLine();
    }
}
```
next()和nextLine()的区别  
next()方法用于读取下一个“标记”，空格，制表符，换行符是常见的标记  
它会返回下一个有效字符，直到遇到空格  
什么意思？  
"  Hello World"，调用next()将返回"Hello"，下一次调用将返回"World"  
就是next()会忽略开头的空白字符，并从第一个非空白字符开始读取，直到下一个空白字符为止  

nextLine()方法用于读取整行输入，包括空格，直到遇到换行符为止  
它会返回读取到的整行字符串，除了换行符  
"Hello World"，调用nextLine()将返回"Hello World"  

如果你需要接收一个整型或浮点型，你需要用相应的关键词  
你可以在[JAVA API](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Scanner.html)文档中查阅使用什么关键字  
这里简单举个例子：   
``` 
Scanner 变量名1 = new Scanner(System.in);
int 变量名2 = 变量名1.nextInt();
double 变量名2 = 变量名.1nextDouble();
boolean 变量名2 = 变量名1.nextBoolean();
//没有nextChar，如果要接收char，用next().charAt(0);
```
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int scanTest = 0;
        Scanner scan = new Scanner(System.in);
        scanTest = scan.nextInt();
        scan.close();
    }
}
```
**关闭资源**  
`变量名.close();`  
Scanner输入流所输入的内容在运行中是不关闭的  
这可能会造成内存泄漏，在不需要使用Scanner时，建议关闭它  

### 如何获取随机数
随机数的使用是不可缺少的，在Java中可以通过Math类来生成随机数  
`double 变量名 = Math.random();`  
random调用会返回一个[0.0,1.0)范围的double类型的随机数  
我查阅了JDK 23的API文档，这一句是Math类提供的唯一一条与随机数有关的语句  
如果你不想使用Math类，也可以使用Random类[java.util.Random](https://docs.oracle.com/en/java/javase/23/docs/api/java.base/java/util/Random.html#%3Cinit%3E())  

使用Math类生成随机数需要变通一下  
例如：生成0-100范围的整型随机数  
`int randomNum = (int) (Math.random() * 101);`  
应该能够理解为什么*101能够得出0-100的范围吧  
random调用会返回一个[0.0,1.0)范围的double类型的随机数  
*101就是[0.0,101.0)，转成int类型就是[0,100]，因为101取不到啊  

获取[a,b]范围的通用公式  
`int 变量名 = (int) (Math.random() * (b - a + 1) + a);`  

#### 使用Random类生成随机数
```
Random 变量名1 = new Random();
//括号写范围，只能写一个数字，写10就是生成[0,10)范围的整型数
int 变量名2 = 变量名1.nextInt();
double 变量名2 = 变量名1.nextDouble()
boolean 变量名2 = 变量名1.nextBoolean()
```
实例：生成[-100,100]的数  
```
import java.util.Random;

public class ArbitraryTest {
    public static void main(String[] args) {
        Random randomNum = new Random();
        int randomNumNest = (randomNum.nextInt(201) - 100);
        System.out.println(randomNumNest);
    }
}
```
***
## 第二章 流程控制
流程控制语句是用来控制程序中各语句执行顺序的语句，可以把语句组合成能完成一定功能的小逻辑模块  
程序设计中规定了三种流程结构  
- 顺序结构  
从上往下逐个执行，中间没有判断和条状  
- 分支结构  
选择性执行某段语句  
- 循环语句  
循环执行某段代码  

### 分支语句
**关键词：if,else,else if,switch**  
```
        if (条件表达式) {
            代码块;
        } else if (条件表达式) {
            代码块;
        } else if (条件表达式) {
            代码块;
        } else {
            代码块;
        }
```
**else if**通常在需要多分支时使用  
除了**if**可以独立外，其他语句都无法脱离**if**使用  

#### if，else，else if的使用
if，else if存在着判断条件，如果判断条件成立，执行这一段代码块，其他则是不执行，起到分支的作用  

如果if语句条件成立，那么else if和else都不执行  
如果if不成立，else if成立，执行else if，其他不执行  
如果if和多个else if都不成立，执行else  
实际例子：  
成年人心率的正常范围是每分钟60-100次，体检时  
如果心率不在此范围内，则需要进一步检查  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int i = 0;
        Scanner scan = new Scanner(System.in);
        i = scan.nextInt();
        if (i >= 60 && i <= 100) {
            System.out.println("情况正常");
        } else if (i < 30 || i > 130) {
            System.out.println("？您？");
        } else {
            System.out.println("莫得惊艳点");
        }
    }
}
```
上述代码中，if-else结构需要执行的语句就一句，你可以省略大括号  
```
        if (i >= 60 && i <= 100)
            System.out.println("情况正常");
        else if (i < 30 || i > 130)
            System.out.println("？您？");
        else
            System.out.println("莫得惊艳点");
```
我个人建议是加上大括号，除非你这个结构是绝对不会进行更改  
并且只是简单的逻辑判定，没有用在很复杂的结构  
if-else的匹配是就近原则，只有在使用大括号时才允许忽略就近原则  
就近原则就是else默认匹配最近的if  

在多分支选择中 有可能会出现中间值  
按照日常使用 我们会下意识使用  
d <= xx < k  
这种表达是不得当的  
为什么？  
<=和<都是二元操作符，也就是只能两个间运算  
d <= xx已经进行了运算，返回了一个boolean值用来表示是与否  
这时候表达式就变成boolean < k，Java不允许boolean值与整型运算  
正确表达应该是  
xx >= d && xx < k  //&& 并  
然后就是建议条件尽可能写成**左闭右开**的形式  
能写成x < 10就不要写成x <= 9  
（与C语言不同，C语言是返回常量）  

##### 嵌套使用
首先要牢记的前提是  
除了**if**可以独立外，其他语句都无法脱离**if**使用  
在这里前提下，你可以任意加入if-else结构  
可以在if中加入if，也可以在else if和else中加入if    

来做道题  
输入三个整数，给他们排序  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int num1 = 0;
        int num2 = 0;
        int num3 = 0;
        int tmp = 0;
        Scanner scan = new Scanner(System.in);
        num1 = scan.nextInt();
        num2 = scan.nextInt();
        num3 = scan.nextInt();
        if (num1 < num2) {
            tmp = num1;
            num1 = num2;
            num2 = tmp;
        }
        if (num1 < num3) {
            tmp = num1;
            num1 = num3;
            num3 = tmp;
        }
        if (num2 < num3) {
            tmp = num2;
            num2 = num3;
            num3 = tmp;
        }
        System.out.println("num1=" + num1 + " num2=" + num2 + " num3=" + num3);
    }
}
```
这里我不打算使用嵌套，这道题嵌套写起来其实是比较麻烦的  
我选择更有简洁性的多if语句，尽管效率未必有if-else高  
在实际开发中，是不会出现超过三层的if-else结构，如果超过了，建议对代码进行更改  

#### switch-case结构
```
        switch (表达式) {
            //表达式只能是char，byte，short，int，String，枚举
            case 常量1:
                代码块;
            case 常量2:
            case 常量3:
                代码块2;
            default:
                代码块;
            //default是默认，当输入switch的值均不符合分支时
            //可以设定default分支来回应
```
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int input = 0;
        Scanner scan = new Scanner(System.in);
        input = scan.nextInt();
        switch (input) {
            case 1:
                System.out.println("第一个分支结果");
            case 2:
            case 3:
                System.out.println("第二个分支结果");
            default:
                System.out.println("其他结果");
        }
    }
}
```
上述就是一个switch-case结构的简单例子，如果你有运行过  
你会发现输出结果是全部分支而不是想要的分支结果  
这个时候需要用到**break**  
鉴于我switch结构用得少，我不知道什么情况需要输出多个分支  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int input = 0;
        Scanner scan = new Scanner(System.in);
        input = scan.nextInt();
        switch (input) {
            case 1:
                System.out.println("第一个分支结果");
                break;
            case 2:
            case 3:
                System.out.println("第二个分支结果");
                break;
            default:
                System.out.println("其他结果");
                break;
        }
    }
}
```
**break**可以终止switch语句，**case**相当于switch的入口，决定switch从哪里开始  
而**break**则是出口，决定从哪里跳出switch，**break**语句并不是必要的  
你可以不添加**break**以此来输出多个分支结果  
switch语句的效率是比if-self要高的，可以选择性使用  

##### switch综合练习
不允许使用if-self结构，使用switch结构来实现以下功能  
1. 允许自由输入数据  
2. 若数据大于60，打印达标，若低于60，打印不合格  
```
import java.util.Scanner;

//方法1
public class ArbitraryTest {
    public static void main(String[] args) {
        int input = 0;
        Scanner scan = new Scanner(System.in);
        input = scan.nextInt();
        scan.close();
        switch (input / 10) {
            case 0:
            case 1:
            case 2:
            case 3:
            case 4:
            case 5:
                System.out.println("不合格");
                break;
            case 6:
            case 7:
            case 8:
            case 9:
            case 10:
                System.out.println("达标");
                break;
            default:
                System.out.println("成绩出错");
        }
    }
}
```
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int input = 0;
        Scanner scan = new Scanner(System.in);
        input = scan.nextInt();
        scan.close();
        switch (input / 60) {
            case 0:
                System.out.println("不合格");
                break;
            case 1:
                System.out.println("达标");
                break;
            default:
                System.out.println("成绩出错");
        }
    }
}
```

### 循环语句
关键词：for，while，do...while  
循环结构有三种：  
1. for循环  
2. while循环  
3. do while循环  

#### for循环
```
        for (初始部分; 判断条件; 调整部分) {
            代码块;
        }
```
初始部分：相当于初始化条件  
判断条件：循环进行的条件  
调整部分：每次循环进行什么调整  
你可以通过下面的例子快速理解：  
（使用了数组内容知识）  
```
public class ArbitraryTest {
    public static void main(String[] args) {
        int i = 0;
        int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        //或者int[] arr = new int[10];
        for (i = 0; i < 10; i++) {
            System.out.print(arr[i] + " ");
        }
    }
}
```
for循环进行流程是这样的  
初始部分->判断条件->满足条件->调整部分->判断条件->满足条件->调整部分->判断条件->不满足条件->不进入循环  

值得一提，for循环三个条件可有可无  
你可以省略初始化部分，也能省略判断条件，三个都省略也是能运行的  
知道就行，实战还是别乱拿来耍  

#### while循环
```     初始部分;
        while (循环条件) {
            代码块;
            调整部分;
        }
```

在循环结构中，也可以使用**break**语句  
可以用来跳出循环  
除了**break**语句外，还有**continue**语句  
与**break**语句不同，**break**是永久终止循环  
而**continue**是跳过自身后面的代码，直接进入判断部分  

来做道题  
输出1-100间所有偶数的和，同时输出偶数个数  
```
public class ArbitraryTest {
    public static void main(String[] args) {
        int i = 0;
        //你可以在初始部分直接定义
        int count = 0;
        int sum = 0;
        for (i = 1; i <= 100; i++) {
            if (i % 2 == 0) {
                sum += i;
                count++;
            }
        }
        System.out.println("偶数之和为" + sum + " 偶数个数为" + count);
    }
}
```

##### 循环结构综合练习
1.输出所有水仙花数，水仙花数是一个三位数，其各个位上数字立方和等于其本身  
```
public class ArbitraryTest {
    public static void main(String[] args) {
        int i = 0;
        for (i = 100; i < 1000; i++) {
            if (i == (i / 100) * (i / 100) * (i / 100)
                    + ((i / 10) % 10) * ((i / 10) % 10) * ((i / 10) % 10)
                    + (i % 10) * (i % 10) * (i % 10)) {
                System.out.print(i + " ");
            }
        }
    }
}
```
我个人建议创建三个变量来做这道题，就不要像我这样做  

2.输入两个正整数，求最大公约数和最小公倍数   
最大公约数   
```
import java.util.Scanner;

//方法1
public class ArbitraryTest {
    public static void main(String[] args) {
        int m = 0;
        int n = 0;
        Scanner scan = new Scanner(System.in);
        m = scan.nextInt();
        n = scan.nextInt();
        int min = (m < n) ? m : n;
        scan.close();

        int result = 1;
        for (int i = 1; i <= min; i++) {
            if (m % i == 0 && n % i == 0) {
                result = i;
            }
        }
        System.out.println(result);
    }
}
```
```
import java.util.Scanner;

//方法2
public class ArbitraryTest {
    public static void main(String[] args) {
        int m = 0;
        int n = 0;
        Scanner scan = new Scanner(System.in);
        m = scan.nextInt();
        n = scan.nextInt();
        int min = (m < n) ? m : n;
        scan.close();

        for (int i = min; i > 0; i--) {
            if (m % i == 0 && n % i == 0) {
                System.out.println(i);
                break;
            }
        }
    }
}
```
```
import java.util.Scanner;

//while循环做法
public class ArbitraryTest {
    public static void main(String[] args) {
        int m = 0;
        int n = 0;
        Scanner scan = new Scanner(System.in);
        m = scan.nextInt();
        n = scan.nextInt();
        scan.close();

        if (n == 0)
        {
            System.out.println(m);
        }

        while (n != 0) {
            int invoke = n;
            n = m % n;
            m = invoke;
        }
        System.out.println(m);
    }
}
```
其实这三个例子都只是实现了功能，并没有进行一定的处理  
例如两个数都为0，或者任一为0的情况，感兴趣自己去想想怎么优化  

最小公倍数（不考虑0的情况，因为懒）  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int m = 0;
        int n = 0;
        Scanner scan = new Scanner(System.in);
        m = scan.nextInt();
        n = scan.nextInt();
        scan.close();
        int ret = m * n;

        if (n == 0) {
            System.out.println(m);
        }

        while (n != 0) {
            int invoke = n;
            n = m % n;
            m = invoke;
        }
        System.out.println("最大公约数为" + m);
        System.out.println("最小公倍数为" + ret / m);
    }
}
```
3.猜数字游戏  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int input = 0;
        int randomNum = (int) (Math.random() * 101);
        System.out.println("猜猜数字>[0,100]");
        Scanner scan = new Scanner(System.in);
        while (true) {
            System.out.print("请输入一个数字>");
            input = scan.nextInt();

            if (input == randomNum) {
                System.out.println("猜对了");
                break;
            }

            if (input > randomNum) {
                System.out.println("猜大了");
            }

            if (input < randomNum) {
                System.out.println("猜小了");
            }

        }
        scan.close();
    }
}
```
如果你想要更高的效率，你要改用if-else结构  
多if语句效率是没有if-self结构高的  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int input = 0;
        int randomNum = (int) (Math.random() * 101);
        System.out.println("猜猜数字>[0,100]");
        Scanner scan = new Scanner(System.in);
        while (true) {
            System.out.print("请输入一个数字>");
            input = scan.nextInt();

            if (input > randomNum) {
                System.out.println("猜大了");
            } else if (input < randomNum) {
                System.out.println("猜小了");
            } else {
                System.out.println("猜对了");
                break;
            }
        }
        scan.close();
    }
}
```

#### do...while循环
```
        初始部分
        do {
            代码块;
            调整部分;
        } while (循环条件);
```
do...while循环执行过程：  
初始部分->调整部分->循环条件->满足条件->调整部分->循环条件->不满足条件->不进入循环  
do...while循环就是先进行一次再循环  

使用do...while结构做一个简单的ATM  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int input = 0;
        double money = 0;
        double hasMoney = 0;
        double carryMoney = 0;
        Scanner scan = new Scanner(System.in);
        System.out.print("请设定你所有的金额>");
        hasMoney = scan.nextDouble();
        System.out.println("设定成功，你现在拥有" + hasMoney + "金额\n");
        do {
            System.out.println("1.存款");
            System.out.println("2.取款");
            System.out.println("3.显示余额");
            System.out.println("0.退出");
            System.out.print("请选择>");
            input = scan.nextInt();

            switch (input) {
                case 1:
                    System.out.print("存入多少金额>");
                    money = scan.nextDouble();
                    if (money > hasMoney) {
                        System.out.println("余额不够\n");
                    } else {
                    //else if (money <= hasMoney)
                        hasMoney -= money;
                        System.out.println("存入成功，你现在账户余额为" + money);
                        System.out.println("你现在持有" + hasMoney + "金额\n");
                    }
                    break;

                case 2:
                    System.out.println("账户余额为" + money);
                    System.out.print("取出多少金额>");
                    carryMoney = scan.nextDouble();
                    if (carryMoney > money) {
                        System.out.println("账户余额不够\n");
                    } else {
                    //else if (carryMoney <= money)
                        money -= carryMoney;
                        hasMoney = hasMoney + carryMoney;
                        System.out.println("取出成功，你现在账户余额为" + money);
                        System.out.println("你现在持有" + hasMoney + "金额\n");
                    }
                    break;

                case 3:
                    System.out.println("账户余额为" + money + "\n");
                    break;

                case 0:
                    System.out.println("已退出ATM机");
                    break;
            }

        } while (input != 0);
        scan.close();
    }
}
```
这里留了一个扩展点，我留下了else if分支，你可以利用else分支去实现一些缺少的功能，如，检测输入是否正确  

#### “无限”循环
典型的无限循环结构有`while(true)`和`for(;;)`  
“无限”循环常用于不知道循环多少次，依靠循环内部的条件来结束的场景  

#### 循环的练习
使用嵌套循环输出棱形  
```
    *
   ***
  *****
 *******
*********
 *******
  *****
   ***
    *
```
输出一个这样的棱形  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int i = 0;
        int line = 0;
        Scanner scan = new Scanner(System.in);
        line = scan.nextInt();
        scan.close();  //我认为没有必要再使用Scanner

        for (i = 0; i < line; i++) {
            int j = 0;
            for (j = 0; j < line - 1 - i; j++) {
                System.out.print(" ");
            }

            for (j = 0; j < 2 * i + 1; j++) {
                System.out.print("*");
            }

            System.out.print("\n");
        }

        for (i = 0; i < line - 1; i++) {
            int j = 0;
            for (j = 0; j <= i; j++) {
                System.out.print(" ");
            }

            for (j = 0; j < 2 * (line - 1 - i) - 1; j++) {
                System.out.print("*");
            }

            System.out.print("\n");
        }
    }
}
```

打印9*9乘法表  
```
public class ArbitraryTest {
    public static void main(String[] args) {

        for (int i = 1; i <= 9; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(i + " * " + j + " = " + i * j + "  ");
            }

            System.out.print("\n");
        }
    }
}
```

打印素数  
```
import java.util.Scanner;

public class ArbitraryTest {
    public static void main(String[] args) {
        int num = 0;
        Scanner scan = new Scanner(System.in);
        num = scan.nextInt();
        scan.close();

        for (int i = 2; i <= num; i++) {

            int j = 0;
            boolean flag = true;
            for (j = 2; j < i; j++) {
                if (i % j == 0) {
                    flag = false;
                    break;
                }
            }

            if (flag) {
                System.out.print(i + " ");
            }
        }
    }
}
```
## 时间锥的应用
如何知道代码运行的时间呢？  
可以借助时间锥[currentTimeMillis](https://docs.oracle.com/en/java/javase/23/docs/api/java.base/java/lang/System.html#currentTimeMillis())，时间锥的单位是毫秒  
```
import static java.lang.System.currentTimeMillis;

long 变量名1 = currentTimeMillis()

long 变量名2 = currentTimeMillis()
```
```
import java.util.Scanner;
import static java.lang.System.currentTimeMillis;

public class ArbitraryTest {
    public static void main(String[] args) {
        long start = currentTimeMillis();

        int num = 0;
        Scanner scan = new Scanner(System.in);
        num = scan.nextInt();
        scan.close();

        for (int i = 2; i <= num; i++) {

            int j = 0;
            boolean flag = true;
            for (j = 2; j < i; j++) {
                if (i % j == 0) {
                    flag = false;
                    break;
                }
            }

            if (flag) {
                System.out.print(i + " ");
            }
        }

        long end = currentTimeMillis();
        System.out.println(end-start);
    }
}
```
获取代码的运算时间是为了优化算法，寻求更高的运行效率，下面是改进了算法的求质数代码，你可以自行比较一下它们的运行时间  
```
import java.util.Scanner;
import static java.lang.System.currentTimeMillis;

public class ArbitraryTest {
    public static void main(String[] args) {
        long start = currentTimeMillis();

        int num = 0;
        Scanner scan = new Scanner(System.in);
        num = scan.nextInt();
        scan.close();

        for (int i = 2; i <= num; i++) {

            int j = 0;
            boolean flag = true;
            for (j = 2; j <= Math.sqrt(i); j++) {
                if (i % j == 0) {
                    flag = false;
                    break;
                }
            }

            if (flag) {
                System.out.print(i + " ");
            }
        }

        long end = currentTimeMillis();
        System.out.println(end - start);
    }
}
```
初步实战-谷粒记账软件  
GuLiAccount.java  
```
public class GuLiAccount {
    public static void main(String[] args) {
        int hasMoney = 10000;
        boolean isFlag = true;
        String info = "";
        do {
            System.out.println("\n-----------------谷粒记账软件-----------------\n");
            System.out.println("                 1 收支明细");
            System.out.println("                 2 登记收入");
            System.out.println("                 3 登记支出");
            System.out.println("                 4 退   出\n");
            System.out.print("                 请选择>");

            char selection = Utility.readMenuSelection();
            switch (selection) {
                case '1':
                    System.out.println("------------------收支明细-------------------");
                    System.out.println("收支\t\t账户金额\t\t收支金额\t\t说明");
                    System.out.println(info);
                    System.out.println("-------------------------------------------");
                    break;
                case '2':
                    System.out.print("本次收入金额>");
                    int money1 = Utility.readNumber();

                    if (money1 > 0) {
                        hasMoney += money1;
                    }

                    System.out.print("本次收入说明>");
                    String addDesc = Utility.readString();
                    info += "收入\t\t" + hasMoney + "\t\t" + money1 + "\t\t    " + addDesc + "\n";
                    System.out.println("------------------登记完成-------------------");
                    break;
                case '3':
                    System.out.print("本次支出金额>");
                    int money2 = Utility.readNumber();

                    if (money2 > 0 && hasMoney > money2) {
                        hasMoney -= money2;
                    }

                    System.out.print("本次支出说明>");
                    String minusDesc = Utility.readString();
                    info += "支出\t\t" + hasMoney + "\t\t" + money2 + "\t\t    " + minusDesc + "\n";
                    System.out.println("------------------登记完成-------------------");
                    break;
                case '4':
                    System.out.print("是否退出(Y/N)>");
                    char isExit = Utility.readConfirmSelection();
                    if (isExit == 'Y') {
                        isFlag = false;
                    }
                    break;
            }
        } while (isFlag);
    }
}
```
Utility.java  
```
import java.util.Scanner;

public class Utility {
    private static Scanner scan = new Scanner(System.in);

    public static char readMenuSelection() {
        char c;
        for (; ; ) {
            String str = readKeyBoard(1);
            c = str.charAt(0);
            if (c != '1' && c != '2' && c != '3' && c != '4') {
                System.out.print("选择错误，请重新输入>");
            } else break;
        }
        return c;
    }

    public static int readNumber() {
        int n;
        for (; ; ) {
            String str = readKeyBoard(4);
            try {
                n = Integer.parseInt(str);
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入>");
            }
        }
        return n;
    }

    public static String readString() {
        String str = readKeyBoard(8);
        return str;
    }

    public static char readConfirmSelection() {
        char c;
        for (; ; ) {
            String str = readKeyBoard(1).toUpperCase();
            c = str.charAt(0);
            if (c == 'Y' || c == 'N') {
                break;
            } else {
                System.out.print("选择错误，请重新输入>");
            }
        }
        return c;
    }
    
    private static String readKeyBoard(int limit) {
        String line = "";

        while (scan.hasNext()) {
            line = scan.nextLine();
            if (line.length() < 1 || line.length() > limit) {
                System.out.print("输入错误，请重新输入>");
                continue;
            }
            break;
        }

        return line;
    }
}
```
你可以对其进行改造，这一次我就不作示范了  
给大家自由实践的机会  

## 数组
数组是多个相同类型数据按照一定顺序排序的集合  
并用一个名字命名，并通过编号的方式对这些数据进行统一的管理  
数组的初始化有多种形式  
```
int[] a = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
int[] a = new int[]{1, 2, 3, 4, 5};

int[] a = new int[4];
int a[] = new int[4];
```
数组中有着几个概念，分别是数组名，元素，下标，长度  
拿int[] a = new int[]{1, 2, 3, 4, 5};进行举例  
a是数组名，1，2，3，4，5是元素  
a[0]代表的就是元素1，a[0]相当于数组第一位，[0]是下标  
长度就是数组的容量，多少个元素就是多长，想要打印长度可以使用`System.out.println(a.length)`  

数组自身的特性说明了数组在内存中是连续存放的，因而各个元素之间相差的地址大小总是相等的  

数组它是一组数据，常规的打印显然是不适合  
我们需要使用循环来打印所有的元素  
```
public class ArbitrayTest {
    public static void main(String[] args) {
        int[] a = {1, 2, 3, 4, 5};
        for (int i = 0; i < a.length; i++) {
            System.out.println(a[i]);
        }
    }
}
```
上述都是进行了初始化，如果不进行初始化，会得出什么结果？  
数组的默认初始化值是多少呢？  
```
public class ArbitrayTest {
    public static void main(String[] args) {
        int[] a = new int[4];
        double[] b = new double[4];
        char[] c = new char[4];
        String[] d = new String[4];
        boolean[] e = new boolean[4];
        for (int i = 0; i < a.length; i++) {
            System.out.print(a[i] + " ");
            System.out.print(b[i] + " ");
            System.out.print(c[i] + " ");
            System.out.print(d[i] + " ");
            System.out.print(e[i] + "\n");
        }
    }
}
```
说结论，整型和浮点型默认值都是0，字符型是空字符，String类是null，布尔类型是false  

### 一维数组的内存解析
tmd，指针还在追我  
Java将内存划分为五块，程序计数器，虚拟机栈，本地方法栈，堆，方法区  

目前与数组相关的内存结构是虚拟机栈和堆  
虚拟机栈：用于存放方法中声明的变量  
堆：用来存放数组中的元素（实体）  

如果有人学过C语言或C++，或者学过数据结构，那么基本听说过栈  
栈区的存放特点是先进后出，好比如说  
```
[]  （第一个取出）  
[]  
[]  
[]  
[]  
[]  
[]  
[]  
[]  
[]  
[]  
[]  （第一个存放）  
```
我们以两个例子来说明  
```
int[] arr1 = new int[4];
arr1[0] = 10;
arr1[2] = 20;

String[] arr2 = new String[2];
arr2[1] = "荧火光";
```
上面说过栈区是存放变量的，也就是数组名  
```
[]  （第一个取出）  
[]  
[]  
[]  
[]  
[]  
[]  
[]  
[]  
[]  
[arr2：0xaabb]  
[arr1：0x12ab]  （第一个存放）  
```
栈区存放的数组名，其实本质是存放地址的首元素地址  
我们所创建的变量，方法，在栈区中都是以地址的形式存在  
数组的连续性存放使得我们能够凭借首元素地址便可以直接访问所有元素  

同时，我们知道，数据在内存中的存储方式是补码，这就意味着我们需要将内容进行转换  
像String这种字符串，同样需要被转换，不同的是，它们还需要放进常量池中  
在Java中，字符串都要被存放进常量池，这些字符串被认为成常量  
当有变量指向相同的字符串时，它们本质上都指向了这个字符串的地址，没有再一次开辟新的空间  
然而，仅仅只有字符串是这样的，数据常量依旧需要开辟空间  
暂且知道这些就足够了，后续面向对象会深入了解  

#### 两个变量指向一个数组
先来看一段代码  
```
public class ArbitrayTest {
    public static void main(String[] args) {
        int[] arr = new int[4];
        arr[0] = 5;
        arr[1] = 6;
        arr[2] = 7;

        System.out.println(arr[0]);
        System.out.println(arr[1]);
        System.out.println(arr[2]);
        System.out.println();

        int[] arr1 = arr;  //将arr的地址赋给了arr1
        arr1[1] = 9;
        System.out.println(arr[0]);
        System.out.println(arr[1]);
        System.out.println(arr[2]);
    }
}
```
上述代码中，实现了类似C/C++语言中的指针操作，将数组arr的地址赋给了arr1，这两个变量指向了同一个地址，对arr1操作，相当于操作arr，这个操作不需要开辟新的内存空间  

### 一维数组练习
1. 翻译手机号码  
```
public class ArbitrayTest {
    public static void main(String[] args) {
        int[] arr = {8, 2, 1, 0, 3};
        int[] index = {2, 0, 3, 2, 4, 0, 1, 3, 2, 3, 3};  //11
        String tel = "";

        for (int i = 0; i < index.length; i++) {
            int value = index[i];
            tel += arr[value];
            //1 8 0 1 3 8 2 0 1 0 0
        }

        System.out.println("联系方式 " + tel);
    }
}
```
2. 输入1-7，打印星期X  
```
import java.util.Scanner;

public class ArbitrayTest {
    public static void main(String[] args) {
        int input = 0;
        String[] arr = {"星期一", "星期二", "星期三", "星期四", "星期五", "星期六", "星期日"};
        Scanner scan = new Scanner(System.in);

        while (true) {
            input = scan.nextInt();
            if (input >= 1 && input <= 7) {
                System.out.println(arr[input - 1]);
                break;
            } else {
                System.out.println("输入错误，请重新输入");
            }
        }
        scan.close();
    }
}
//这里做了简单的判断，要处理除整型外的是有一些复杂的，平时练习没有那个必要
```
3. 输入学生人数以及成绩，找出最高分，并进行等级划分，等级依据最高分来取（例如，最高分-10，最高分-20等）  
```
import java.util.Scanner;

public class ArbitrayTest {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.print("请输入学生人数>");
        int count = scan.nextInt();
        int[] scores = new int[count];
        System.out.println("请依次输入学生成绩>");

        int i = 0;
        int max = scores[0];
        for (i = 0; i < scores.length; i++) {
            scores[i] = scan.nextInt();

            if (max <= scores[i]) {
                max = scores[i];
            }
        }
        System.out.println("最高分>" + max);

        for (i = 0; i < scores.length; i++) {
            if (scores[i] >= max - 10) {
                System.out.println("学生" + i + " 分数为" + scores[i] + " 等级A");
            } else if (scores[i] >= max - 20) {
                System.out.println("学生" + i + " 分数为" + scores[i] + " 等级B");
            } else if (scores[i] >= max - 30) {
                System.out.println("学生" + i + " 分数为" + scores[i] + " 等级C");
            } else {
                System.out.println("学生" + i + " 分数为" + scores[i] + " 等级D");
            }
        }
        scan.close();
    }
}
```
可以去写一个输入学生名的，例如：  
```
import java.util.Scanner;

public class ArbitrayTest {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int i = 0;

        System.out.print("请输入学生人数>");
        int count = scan.nextInt();
        scan.nextLine();  //清除缓冲区

        String[] nameLine = new String[count];
        System.out.println("请依次输入学生名字>");

        for (i = 0; i < nameLine.length; i++) {
            nameLine[i] = scan.nextLine();
        }

        int[] scores = new int[count];
        System.out.println("请依次输入学生成绩>");

        int max = scores[0];
        for (i = 0; i < scores.length; i++) {
            scores[i] = scan.nextInt();

            if (max <= scores[i]) {
                max = scores[i];
            }
        }
        System.out.println("最高分>" + max);

        char grade = 0;
        for (i = 0; i < scores.length; i++) {
            if (scores[i] >= max - 10) {
                grade = 'A';
            } else if (scores[i] >= max - 20) {
                grade = 'B';
            } else if (scores[i] >= max - 30) {
                grade = 'C';
            } else {
                grade = 'D';
            }
            System.out.println("学生" + nameLine[i] + " 分数为" + scores[i] + " 等级" + grade);
        }
        scan.close();
    }
}
```
### 二维数组
二维数组其实是将一维数组作为另一个一维数组的元素，形成的有行列的结构  

#### 二维数组的创建与使用
```
int[][] a = {{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}};
int[][] a = new int[][]{{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}};

int[][] a = new int[4][4];
int a[][] = new int[4][4];

int[][] a = new int[4][];  //不允许int[][] a = new int[][4]
//奇奇怪怪，C语言允许省略行，不允许省略列，这边居然是反过来的
```
```
public class ArbitrayTest {
    public static void main(String[] args) {
        int[][] a = new int[][]{{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}};
        //上面有三个大括号，也就是3行，每个都有4个元素（不够补默认值），也就是a[3][4]
        //如何取得元素5？
        System.out.println(a[1][0]);  //第二行，第一列就是元素5
        System.out.println(a[1]);
        //打印的是地址，是这一行的地址，不是首元素地址

        //这是将二维数组分成多个一维数组来看
        int[][] arr = new int[2][];
        arr[0] = new int[4];
        arr[0][0] = 1;

        System.out.println(a.length);  //多少行
        System.out.println(a[0].length);  //某一行有多少元素
        System.out.println();

        //如何遍历二维数组？
        //两个for循环的事情
        for (int i = 0; i < a.length; i++) {
            for (int j = 0; j < a[i].length; j++) {
                System.out.print(a[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```
数组中有关类型提升以及相互赋值等问题  
```
public class ArbitrayTest {
    public static void main(String[] args) {
        int[] arr = new int[10];
        byte[] arr2 = new byte[20];
        arr = arr2;
        //是否允许这一种，答案是不允许
        //int[]和byte[]是两种不同的引用数据类型
        int[][] arr3 = new int[3][3];
        arr = arr3;
        //是否允许这一种，答案是不允许
        //int[]和int[][]是两种不同的引用数据类型
    }
}
```
#### 二维数组的默认值和内存解析
```
//二维数组的默认初始化

public class ArbitrayTest {
    public static void main(String[] args) {
        int[][] arr1 = new int[3][3];
        System.out.println(arr1[0]);  //第一行地址
        System.out.println(arr1[0][0]);  //0
        System.out.println();

        int[][] arr2 = new int[3][];
        System.out.println(arr2[0]);  //null
        System.out.println(arr2[0][0]);  //报错
        System.out.println();

        double[][] doubleArr1 = new double[3][3];
        System.out.println(doubleArr1[0]);  //第一行地址
        System.out.println(doubleArr1[0][0]);  //0.0
        System.out.println();

        double[][] doubleArr2 = new double[3][];
        System.out.println(doubleArr2[0]);  //null
        System.out.println(doubleArr2[0][0]);  //报错
        System.out.println();

        char[][] charArr1 = new char[3][3];
        System.out.println(charArr1[0]);  //第一行地址
        System.out.println(charArr1[0][0]);  //0
        System.out.println();

        char[][] charArr2 = new char[3][];
        System.out.println(charArr2[0]);  //null
        System.out.println(charArr2[0][0]);  //报错
        System.out.println();

        String[][] stringArr1 = new String[3][3];
        System.out.println(stringArr1[0]);  //第一行地址
        System.out.println(stringArr1[0][0]);  //null
        System.out.println();

        String[][] stringArr2 = new String[3][];
        System.out.println(stringArr2[0]);  //null
        System.out.println(stringArr2[0][0]);  //报错
        System.out.println();

        boolean[][] booleanArr1 = new boolean[3][3];
        System.out.println(booleanArr1[0]);  //第一行地址
        System.out.println(booleanArr1[0][0]);  //false
        System.out.println();

        boolean[][] booleanArr2 = new boolean[3][];
        System.out.println(booleanArr2[0]);  //null
        System.out.println(booleanArr2[0][0]);  //报错
        System.out.println();
    }
}
```
你可以看这个图来理解二维数组的内存解析  
[![pAdiB7t.png](https://s21.ax1x.com/2024/10/21/pAdiB7t.png)](https://imgse.com/i/pAdiB7t)  
#### 二维数组练习
1. 求以下数组所有元素总和  
`int[][] arr = new int[][]{{3, 5, 8, 0}, {12, 9, 0, 0}, {7, 0, 6, 4}};`  
```
public class ArbitrayTest {
    public static void main(String[] args) {
        int[][] arr = new int[][]{{3, 5, 8, 0}, {12, 9, 0, 0}, {7, 0, 6, 4}};
        int sum = 0;
        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr[i].length; j++) {
                sum += arr[i][j];
            }
        }
        System.out.println(sum);
    }
}
```
































































--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------
--------------------------------------

## IDEA的使用
**你可以在这里获取[IDEA](https://www.jetbrains.com/idea/)**  
本篇章将讲述IDEA的使用  


IDEA为我们提供了许多强大的功能，例如：  
### 快捷输入
快捷输入mian方法  
```
public class ArbitraryTest {
    main  //输入main后回车
}
```
快捷打印  
```
public class ArbitraryTest {
    public static void main(String[] args) {
        sout  //输入sout后回车
        "yhlight".sout  //快捷打印
    }
}
```
快捷导入包
```public class ArbitraryTest {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);  //选择报红处ALT+ENTER
    }
}
```
还提供了一些人性化的设置，你可以自行根据需求进行修改  
### 设置IDEA
暂且无法进行更新，图片的上传有限制  

使用上了更加高级的编译器，说明我们已经进入了一个新的阶段  
在这个阶段中，我们将逐步适应项目化  
### 初识JAVA项目
JAVA项目是这样划分的  
**项目->模块->包->类**  
项目，包以及类是我们现阶段经常使用的东西，在不久之后我们将经常接触模块  
一个项目包括一个模块或者多个模块，一个模块包括多个包，一个包里面包括多个类  

#### 模块的创建与包的创建使用
**在IDEA中我们可以通过左侧项目栏右击项目新建一个模块**  
**创建好模块之后，你可以在IDEA的文件栏中看到你所创建的模块文件夹**  
**在模块的目录下面有一个名叫src的文件夹**  
**JAVA文件应被存放在src文件夹内**  
**每一个模块是独立又相互联系的，所以模块既可以做到独立运行又可以做到依赖**  
**现阶段暂不要求学会使用模块**

##### 包的创建
在创建好模块之后，我们可以正式创建属于我们自己的包，这些包将集成我们所需要实现的功能  

在前边，我们学习过标识符的命名规范，明确表明了包的起名规范  
**在实际应用中，起名往往是根据公司的域名**  
例如：  
```
com.yhlight.util
```
在IDEA中左侧的文件栏里，选择模块中的src文件夹，右键新建软件包，起名为上述格式  
然后为包创建相应的类文件或将类文件移入包文件夹内  
这样便已经创建好了你的第一个包，你可以在其他类文件中引用这个包的功能  
不过这是后日谈了  

有一些人想要直接导入别人的模块，这时候需要怎么做？  
其实很简单，直接复制整个文件夹过来，然后打开文件栏，打开项目结构，点击加号，然后选择导入模块  
