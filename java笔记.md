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
#### JKD的安装（自行选版本）
https://www.oracle.com/cn/java/technologies/downloads/  
进入这个链接后，你可以选择安装高版本JAVA，也可以选择安装JAVA 8  
需要下载的是Windows版本
[![pA3VG0U.png](https://s21.ax1x.com/2024/09/30/pA3VG0U.png)](https://imgse.com/i/pA3VG0U)  

如果你想要安装JAVA 8，请继续往下浏览页面
[![pA3V8mT.png](https://s21.ax1x.com/2024/09/30/pA3V8mT.png)](https://imgse.com/i/pA3V8mT)  

#### 路径相关的配置（必要）
JAVA可以安装在任意一个盘，只不过更推荐安装在系统盘，安装在系统盘可以避免很多问题，没必要为了担心一些微不足道的问题而安装在其他盘，具体自行选择  

##### JAVA目录的简单认识
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

#### 配置Path环境变量
**什么是Path环境变量?**  
Path环境变量是window操作系统执行命令时，所要搜寻的路径  

**为什么要配置Path环境变量?**  
希望在命令行使用Java工具时，在任意目录之下都能找到工具包的目录  
好比如说，如果没有设置Path环境变量，使用javac命令需要先在命令行输入cd，导航至bin文件目录  
例如  
cd C:\Program Files\Java\jdk-22\bin  
javac test.java  
java test  
需要这样才可以正常运行  
这样对开发很麻烦，肯定是不希望每次都要把java文件丢进bin目录之中再进行运行  

##### 如何配置Path环境变量?
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
#### 你的第一个程序-打印HelloWorld
Java文件是如何编写和运行的？  
首先，你需要通过记事本等文件软件来写Java代码，这里推荐使用[visula studio code](https://code.visualstudio.com/)  

你只需要右键新建一个txt，然后更改为java后缀的文件，再进行编写就可以了，注意，要打开显示扩展名，否则无法进行后缀的更改  

然后使用javac命令将java文件进行编译，生成class文件  

接着使用java命令运行生成的class文件  

##### HelloWorld的打印
将txt命名为HelloWorld.java，注意HelloWorld只是一个名字，可以任意更换，但是需要和代码之中的 **类（class）** 的名字相同，具体往下看  
~~~
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("HelloWorld");
    }
}
~~~
这就是打印HelloWorld需要的代码，class后面接的HelloWorld就是**类**的名字，你可以随意修改，但是最好是和文件名字相同  

举个例子  
文件名字 HelloWorld.java  
类的名字 HelloChina  

javac HelloWorld.java  
生成的class是HelloChina.class  

java HelloChina  
运行需要输入类的名字，而不是文件名字  
明显，这繁琐许多，同时，不仅仅是这些问题，这里进行相关的一些解析  
1. pubilc类一致性需求
你可以看到，上面的代码是class + 类名，然而，在Java中，更多使用的是pubilc class + 类名  
在Java中规定，pubild class 的**类名**要和**文件名**完全相同  

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
>chcp 65001  
3. 运行java时设置编码  
>java -Dfile.encoding=UTF-8 HelloWorld  