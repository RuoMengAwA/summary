***引子：在日常书写笔记的时候，个人比较喜好使用typora在本地编辑，因为其比较简洁方便速度快，但使用typora在本地编辑也有一个坏处，譬如说，当你从其他地方复制粘贴一张图片作为到typora上作为自己笔记的一部分的时候，该图片的地址为你本地粘贴板的地址，而当你想要将该笔记上传到云端的时候，就会出现因为图片不在图床上导致的上传图片无法正常被转存，而要多一步重新截图复制粘贴的步骤，当你笔记图片较多的时候（譬如说我），就会觉得特别麻烦，所以就有了以下教程，傻瓜级别，带你避坑***

![image-20210207130206694](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207130206.png)

[TOC]



# 效果

当使用该方法建立云笔记之后，可以在typora上直接复制粘贴图片，也可以直接将本地图片复制粘贴过来，而在typora上会自动上传图片到gitee的图床上，而现在的图片就可以正常在外界博客上或者别人被读取了，且因为gitee在国内，速度相较于github的图床速度更快，且gitee也不限制图片上传的总大小，可以说是非常的方便了。

# 实际操作

## Gitee

1.首先现在gitee上创建一个账号，创建账号的操作就不要我教了叭，之后点击新建仓库。

![image-20210207153309125](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207153309.png)

2.在新建仓库界面，随便写点仓库名称，随便写下仓库介绍，选择公开，语言随便选一个就行，添加开源许可证就点快速选择选一个你觉得最好的就行了，然后再选择“使用Readme文件初始化这个仓库”，最后点创建。

![image-20210207154819839](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207154820.png)

3.创建好仓库之后，再点击自己右上角的头像，再点设置，之后在左侧，点击私人令牌

![image-20210207163859998](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207163900.png)

![image-20210207164046333](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207164046.png)

4.随便填一点描述，点提交，记住，这个生成的令牌口令务必要保存，只会生成一次，我一般保存在一个记事本上，这个token之后会在picgo的设置当中使用到

![image-20210207164528793](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207164528.png)

5.之后就完成了gitee的操作过程了，之后，我们便开始PicGo的配置过程

## PicGo

*这是一个图床软件*

1.先在github上下载一个PicGo（地址：https://github.com/Molunerfinn/PicGo/releases ）

![image-20210207131626629](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207131626.png)

2.打开PicGo（一般要在自己的后台打开）

![image-20210207131728568](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207131728.png)

![image-20210207131800643](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207131800.png)

3.这时候我们看到，在图床选择当中并没有gitee的选项，这时候我们就需要安装插件啦，首先进入插件设置，搜索gitee，选择安装第二个，无论如何一定要安装第二个，第一个没办法上传成功的，安装它的时候经常会一直显示着正在安装，然后一直没安装上，耐心的多试几次 

![image-20210207131847109](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207131847.png)

4.在安装gitee插件的时候我们可以先去做一下gitee的设置，来排除之后可能回出现导致上传失败的各种设置问题，进入Picgo的设置选项，再点击设置Server，之后按照该图片的配置进行修改（虽然大部分默认状况就是这个，但是picGo有可能会更改默认设置的，还是要看看，不然之后会遇到很奇怪的上传失败问题）

![image-20210207151918234](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207151918.png)

5.接下来还是在设置当中，打开时间戳重命名，不然会在某些特殊情况遇到一些上传失败问题

![image-20210207152406919](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207152407.png)

6.接下来，在下载好gitee的插件之后，重新启动PicGo，之后可以在图床设置当中就看见gitee的选项了，点击并且开始设置

![image-20210207170728837](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207170728.png)

7.repo这个是你的gitee用户名和仓库名，但是这个地方有一个巨大的坑，在下图可以看到，我的用户名加仓库名是这样的，而在gitee设置当中为什么变成了ruomengawa/pic-go呢，这个问题曾经让我在配置过程当中差点气的摔电脑，后来，经过多方查找，终于发现，这个地方填入的用户名和仓库名需要在这个地方获取：

![image-20210207170903460](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207170903.png)

![image-20210207181922642](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207181922.png)

将其复制粘贴之后放在repo当中即可

8.branch默认填master即可

9.token填刚刚在gitee中拿到的令牌码

10.path默认填个img，然后就会在你刚刚创建的gitee库当中建立一个名字为img的文件夹来储存你的云图片

11.custompath选年月，保存的命名方式

12.customurl不用填

13.一定要点确定和设为默认图床

14.搞定一切之后重启PicGo

15.之后结束了PicGo设置部分，进入typora偏好设置部分

## typora

1.打开偏好设置

![image-20210207130856395](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207130856.png)

2.在图像当中，按照下图中这样改，然后PicGo路径为PicGo软件放的位置

![image-20210207183111946](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207183112.png)

3.为提高笔记舒适感，在平时敲笔记的时候输入英文时，英文下方会出现红色波浪线，影响笔记阅读观感，所以可以在偏好设置——编辑器当中进行如下修改

![image-20210207183523938](https://gitee.com/ruomengawa/pic-go/raw/master/img/20210207183524.png)

4.之后就可以正常复制粘贴图片到笔记当中不需要担心博客中无法转存笔记图片外链了，这时的typora我觉得就是我用的最舒服的笔记编辑器了，哈哈哈哈。



5.以下是一个他人写的typora的markdown语法和一些书写设置操作，如有需要可自行查看

[链接](https://blog.csdn.net/qq_34599132/article/details/90172835?ops_request_misc=%25257B%252522request%25255Fid%252522%25253A%252522161269419816780264016691%252522%25252C%252522scm%252522%25253A%25252220140713.130102334.pc%25255Fall.%252522%25257D&request_id=161269419816780264016691&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_v2~rank_v29-6-90172835.pc_search_result_hbase_insert&utm_term=typora%25E5%25BC%2595%25E5%258F%25B7%25E8%2587%25AA%25E5%258A%25A8%25E8%25A1%25A5%25E5%2585%25A8)



