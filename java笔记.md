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
你可以看到，上面的代码是class + 类名，然而，在Java中，更多使用的是public class + 类名  
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

****

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

***

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
变量的声明：数据类型 变量名 = 变量值  
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
        int j;
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
    public static void main(String[] arg) {
        System.out.println(0.1 + 0.2);
    }
}
```

***

```
public class Test {
    public static void main(String[] arg) {
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
    public static void main(String[] arg) {
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
    public static void main(String[] arg) {
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
    public static void main(String[] arg) {
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

##### 类型提升
当容量小的变量与容量大的变量做运算时，结果自动转换为容量大的数据类型  
这个容量指的是范围大小，而不是占用的内存大小  
```
public class VariableTest {
    public static void main(String[] arg) {
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

### String类
String不属于基本数据类型，属于引用数据类型  

`String s1 = "字符串";`

字符串：由一个或多个字符组成并被双引号括起来的字符或字符串  
Java允许字符串为0个字符  
```
public class StringTest {
    public static void main(String[] arg) {
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
    public static void main(String[] arg) {
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
    public static void main(String[] arg) {
        int num = 10;
        String s1 = "";
        String s2 = s1 + num;
        System.out.println(s2);
        //最终输出"10"，字符10
        int num2 = Integer.parseInt(s2);
    }
}
```