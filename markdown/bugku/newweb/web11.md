# web11

![image-20210115210340325](../../../image/image-20210115210340325.png)

进入环境

![image-20210115210412189](../../../image/image-20210115210412189.png)

emmm

查看源码，没啥可用的信息

![image-20210115210444782](D:/mygit/notes/image/image-20210115210444782.png)

使用bp爆破一下目录

首先抓包

![image-20210115210712925](D:/mygit/notes/image/image-20210115210712925.png)

使用爆破模块Intruder

添加变量

![image-20210115210803485](D:/mygit/notes/image/image-20210115210803485.png)

然后添加字典

![image-20210115211459951](D:/mygit/notes/image/image-20210115211459951.png)

开始跑

![image-20210115211843098](../../../image/image-20210115211843098.png)

得到两个文件时200的状态码

![image-20210115211957230](D:/mygit/notes/image/image-20210115211957230.png)

index.php

是主页

![image-20210115212035317](D:/mygit/notes/image/image-20210115212035317.png)

shell.php

一个网页

让输入密码

又继续使用爆破

抓包

![image-20210115212203744](D:/mygit/notes/image/image-20210115212203744.png)

添加变量

![image-20210115212233204](D:/mygit/notes/image/image-20210115212233204.png)

添加字典

![image-20210115212347174](D:/mygit/notes/image/image-20210115212347174.png)

开始爆破

![image-20210115212421508](D:/mygit/notes/image/image-20210115212421508.png)

得到密码hack

![image-20210115212504855](D:/mygit/notes/image/image-20210115212504855.png)

得到flag

![image-20210115212557406](D:/mygit/notes/image/image-20210115212557406.png)