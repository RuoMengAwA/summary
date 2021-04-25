[TOC]

# 前言

**好家伙，怎么用着用着python就发现，之前使用过的python语法和内置函数都不怎么熟练啊，明明以前还很熟练的用过这玩意，过了一段时间再想用它居然都不会用了，完蛋，这样下去还怎么看自己以前的代码啊，快，给爷爬去整理笔记去**

*本文档主要对不咋地熟练的语法和函数进行复习和补充整理，将以前笔记中该部分内容全部整合于该文档中，后期也会将一些基础常见库的函数补充进来*

# 函数



## zip(x,y,...)

* zip(x,y,...)可以获取多个参数（可迭代对象），返回一个zip类型的内存空间，可以对其进行获取，对其中的多个参数同时进行迭代获取，以下为例子

* for a , b in zip(c,d):同时获取c,d两个列表的数值，逐个加入a ，b
* ![image-20210425104925611](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210425104925.png)



## map(function,iterable)

* 第一个参数接受一个函数名，后面的参数接受一个或多个可迭代的序列，返回的是一个集合。
* 把函数依次作用在list中的每一个元素上，得到一个新的list并返回。注意，map不改变原list，而是返回一个新list。
* 例：![image-20210425110450255](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210425110450.png)
* 总所周知，在python中input（）会获取控制台中的数值，并默认返回str类型，而经过map函数处理之后，对返回的列表['1', '5']每个参数都使用了int函数，最后全部返回int型，当然也可以使用具有数据处理的函数对列表中每个元素进行处理



## int(x,[base])

* 将一个数字或【base】类型的字符串转化为整数
* 当x为int型时，将会对x进行向下取整，且此时【base】不能被赋值，否则会报错
* 当【base】被赋值后，x将只接收字符串，此时可以对int型使用str（）函数，接收到的字符串将会以base为基数，将字符串当做一个【base】进制的数，并返回其在十进制下的对应数据，base的取值范围为2~36
* 例：![image-20210425113357620](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210425113357.png)
* 101在二进制下，被int转化为十进制数，结果为5

* int(‘0x10‘,16) == 16 ,因为0x在此处被视为16进制的特殊符号，将除开0x之外的10作为16进制基数的数据，转化为十进制的16



## 列表相关函数

### 列表增添修改![在这里插入图片描述](https://img-blog.csdnimg.cn/2020110921342339.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1JVT01FTkdBd0E=,size_16,color_FFFFFF,t_70#pic_center)
extend（）参数可以为一个list，传输一个列表到对象列表的末尾。

insert（x = 想要增添在列表上的位置，y = 增添的元素）
增添的位置的原有元素会整体全部向后移动一位。

### 列表删除

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020110921474727.png#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201109214912213.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1JVT01FTkdBd0E=,size_16,color_FFFFFF,t_70#pic_center)

* remove（x），x == 你想删除的元素，若list中有多个 x 则删除第一个 x。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201109215029380.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1JVT01FTkdBd0E=,size_16,color_FFFFFF,t_70#pic_center)

* del（x），x == 要删除的元素索引

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201109215152107.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1JVT01FTkdBd0E=,size_16,color_FFFFFF,t_70#pic_center)
pop（）函数相当于del（）的升级版，还会返回删除的元素值。

### 元素搜索

* ![image-20210425133933406](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210425133933.png)
* 搜索列表中的元素值，返回元素对应位置的索引值（只能返回该元素出现的第一个位置的索引值）



## lambda函数

**在之后的函数使用介绍中将会使用lambda函数，所以有必要先介绍这个python中非常常用的内置函数**

* 介绍（特性）

  lambda函数又被称作匿名函数，即没有具体名称的函数，它允许你快速定义一个单行函数并使用，其具有自己独有的函数空间，不能访问自己参数列表之外或者全局命名空间中的参数，能完成较简单的运算功能，以及实现一些独特的功能，方便快捷，简化代码为他的主要功能。

* 常见用法

  



## 排序函数

### sort（），reverse（）

* list.sort()对原列表进行排序，修改原列表数据，默认正序排序（从小到大），因为是对列表直接进行处理，所以要先进行list.sort()才可使用排序过后的list
* list.reverse()对原列表排列进行倒置，如list = 【1,2,3】--》list = 【3,2,1】

### sorted（iterable,key,reverse）

* iterable





[TOC]

# 语法

## python中对自建包的引用

这是文件结构，我先创建了一个文件夹mai，其中包括一个自带的_init_.py文件，而我自己创建了一个jiafa.py的文件，其中放入了我写的函数，如图：

![image-20210310153643167](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210310153650.png)

![image-20210310154243988](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210310154244.png)

![image-20210310154358937](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210310154358.png)

如图，我从mai这个文件当中引用了jiafa这个py文件并在现在这个运行文件当中使用jia这个名字来使用其，而在调用的时候，直接使用jia.jiafa/jianfa来调用即可。



## python引用包h5py对.h5文件操作

*.h5类型的文件在神经网络机器学习方向的数据处理具有极其重要的作用*

![image-20210210190022307](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210210190029.png)

例：

![image-20210210190135057](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210210190135.png)的操作就是，从file：train_catvnoncat.h5当中的文件train_set_x提取数据形成到列表train_set_x_orig当中



## python的广播化处理

* 规则

![image-20210214161634217](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210214161634.png)

* 例子

![image-20210214162159470](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210214162159.png)

![image-20210214162213757](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210214162213.png)

![image-20210214162258871](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210214162258.png)

![image-20210214162309312](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210214162309.png)

![image-20210214162434773](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210214162434.png)

![image-20210214162452577](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210214162452.png)

在上图中定义了两个numpy数组a和b，将他们相加，首先因为b数组的维度较a来说不足，由广播处理准则中第一条，b数组的维度会变成（1,5）即[ [1,2,3,4,5] ]

而此时，a，b的维度为（6,1）（1,5）根据规则二，最后的输出数组c应该会被扩展为（6,5）

而根据规则3（规则三应该为：输入数组的某个轴长度若为1或者与输入数组的对应轴长度相同时，若该数组无法计算，则需要进行自修改至可运算）

所以，由规则三和规则四共同修改得：

a的第一轴1被更改为了5，从之前第一轴的第一个数值（如0）在第一轴上开始扩展为5个0![image-20210214172637461](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210214172637.png)

b的第零轴1被更改为了6，从之前第零轴的第一个数值【0,1,2,3,4】在第零轴上扩展至6个该数值![image-20210214172704712](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210214172704.png)

最后将其相加，结果维度恰好为（6,5）

补充，规则五：适用于广播运算的数据应该是要至少有一个维度是“满的（非0,1）”，另外对应的一个维度为1，或者两个维度都是“满的”（且维度数值要相同）



## 推导式（循环用）

*使用推导式可以在循环当中大大降低时间复杂度*

* 列表推导式

  * a = (i for i in range(1,11))

  * 结果为输出列表 list a [1,2,3,4,5,6,7,8,9,10]

  * 其中，第一个 i 是可以加上其他条件的譬如说改为 i**2

* 字典推导式

  * 相较于列表推导式，字典推导式的建立要考虑到键值对的搭配
* ![image-20210203231429231](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210203231429.png)

## 切片

* 切片有第三个参数--步长，步长的作用为按步长跳跃性的提取字符串或列表当中的对应数据，步长为正数则为正序，步长为负则为倒序，默认为1
* 前两个参数就是正常的取值，在某范围内取
* ![](https://i.loli.net/2021/01/24/RDqbVxmGKCNOEsa.png)
* ![image-20210203231508402](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210203231508.png)
* 若步长为负，则前面两个参数需要变化，因为在负步长的情况下，整个列表会先索引再倒置，之后正向切片，而使用的索引还是倒置之前的索引，所以如图，索引5就为6，而索引1就为2，最后正向切取
* ![image-20210329161753876](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210329161753.png)

## 类的定义

* ![image-20210203231543399](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210203231543.png)

* ![image-20210203231629524](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210203231629.png)

* ![image-20210203231725660](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210203231725.png)

## 类的继承

* ![image-20210203231809172](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210203231809.png)

