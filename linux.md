



[TOC]

# linux操作

## 连接工作站

查看ip地址：**ipconfig**

ssh ray@10.0.0.5
215家人

## 查看当前的绝对路径

pwd

## 查看当前文件夹下的文件

ls  想要查看的路径（上一个文件夹就是  ..    上上一个文件夹就是   ../..  ）

## 返回上一/两个目录

cd ..    cd ../..

## 删除

删除文件：rm -f 文件名（或绝对路径）

删除目录：rm -rf 目录名（或绝对路径）

删除路径下全部文件 *



## 重命名，移动，拷贝

重命名：mv   【参数】  原文件名   更改文件名

移动：mv 【参数】  源文件/目录   目标目录（若第二个参数为文件的话，就为重命名了）

拷贝/生成副本： cp  【参数】  源文件/源目录	副本名/目标目录	(若第二个参数为副本名的话，即为重命名拷贝)

## 创建文件及文件夹

创建文件：touch + 文件名

创建文件夹：mkdir + 文件夹名

## 压缩包处理

压缩文件：

7za	a(表示添加文件/文件夹到压缩包)	-t(你需要压缩的文件类型，如zip)	-r(表示递归)	压缩后的文件名	需要压缩的文件路径

例：7za a -t7z -r Xiaomai.7z /Xiaomai/demo/*

解压缩文件：

7za	x(表示解压缩文件)	需要解压的压缩包路径或名字	-r	-o后直接更需要解压到的路径		

## 输入命令

直接按Tab可以查看当前文件下的所有东西

按上下键查看之前使用的命令

按右键补全命令

## 查看当前目录下有多少个非文件夹的文件

ls -l | grep "^-" | wc -l 

## 使用管理员权限

su （直接获得管理员权限）

sudo+‘    ’+命令 （单个管理员权限命令）

## 清屏

ctrl+L

## 退出当前命令

ctrl+c/z

## 查找命令

find

![image-20210420115153673](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210420115153.png)

## 查看当前进程

nvidia-smi

![image-20210422113902257](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210422113909.png)

## 杀进程

方法一：使用htop查看进程

方法二：使用kill -9 以及相关PID（从上面的进程查看中获取）



# 后台操作(tmux控制台)

## 创建新后台

tmux  new -s 起名字

## 干掉指定对话

tumx kill -session -t 会话名

## 进入最近的后台

tumx a

## 退出后台（暂时离开）

tmux detach

## 查看所有后台

tmux ls

# 后台操作(tmux快捷键)

## 后台切换

快捷键：ctrl+B +左或右括号 

快捷键：先按ctrl+B, 放开后再按S

## 退出后台（暂时离开）

快捷键：ctrl+B  然后松开ctrl 按D

## 分屏

**水平分屏**

快捷键：先按 ctrl+B, 放开后再按%

**垂直分屏**

快捷键：先按 ctrl+B, 放开后再按 "

**分屏后的窗口中的光标互相切换**

快捷键：先按ctrl+B, 放开后再按下O

**关闭所有分屏后的窗口，即合并为一个窗口** 

快捷键：先按ctrl+b, 放开后再按！

## 终止一个终端窗口

快捷键：exit 或 先按ctrl+B, 放开后再按 &

##  终端内显示时间

快捷键：先按ctrl+b, 放开后再按t

退出时间界面：按q键



# 修改文件
***vim 或者nano可以进行修改文件操作***

## nano操作

### 打开文件

* nano 操作参数	+（这个‘+’一定要要）想要打开的行数，想要打开的列数	绝对路径文件名（或当前路径下文件名）

* 以下为其操作参数：

![image-20210426085329584](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210426085329.png)



### 选定，复制，剪切，粘贴，撤销

**选定：**Alt+A 进入标记模式，在该模式下移动光标标记文本，也可在进入文件的时候启用鼠标功能

**复制：**Alt+6（若未选定，则默认复制现在光标所在的行）

**剪切：**Ctrl+K （若未选定，则默认剪切现在光标所在的行）

**粘贴：**Ctrl+U

**撤销：**Alt+U

### 搜索

按**Ctrl+W**，然后输入你要搜索的关键字，回车确定。这将会定位到第一个匹配的文本，接着可以用**Alt+W**来定位到下一个匹配的文本。

### 保存

Ctrl+O （同时可以对文件名字进行编辑，若文件名修改，则会另外生成一个修改名字后的文件）

### 获取当前位置信息，以及文本详细信息

Ctrl+C

### 退出

Ctrl+X

### 获取更多详细命令

Ctrl+G



## VIM操作

* 使用vim对文件进行操作，建议使用sduo命令，vim + ‘   ’ + 文件名

### VIM编辑模式

* 使用下面6个字母进入，esc退出

i：在当前字符前插入。

I：在光标所在行的行首插入。

a：在当前字符后插入。

A：在光标所在行的行尾插入。

o：在当前行的下一行插入新的一行。

O：在当前行的上一行插入新的 一行。

### VIM命令模式

:w 保存文本。

:q 退出vim。

:w! 强制保存，在root用户下，即使文本只读也可以完成保存。

:q! 强制退出，所有改动不生效。

:wq 保存退出。

:x 类似于wq，更改了文件以后，wq和x的作用是一样的，若没有更改文件，使用wq，文件的mtime会改变，而x不会。

:set nu 显示行号。

:set nonu 不显示行号。

