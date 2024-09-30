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