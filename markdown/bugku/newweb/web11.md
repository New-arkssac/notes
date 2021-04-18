# web11

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618655999248-image-20210115210340325.png)

进入环境

![image-20210115210412189](D:\ebook\markdown\image\image-20210115210412189.png)

emmm

查看源码，没啥可用的信息

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656048006-image-20210115210444782.png)

使用bp爆破一下目录

首先抓包

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656066298-image-20210115210712925.png)

使用爆破模块Intruder

添加变量

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656090318-image-20210115210803485.png)

然后添加字典

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656110734-image-20210115211459951.png)

开始跑

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656134649-image-20210115211843098.png)

得到两个文件时200的状态码

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656202288-image-20210115211957230.png)

index.php

是主页

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656228255-image-20210115212035317.png)

shell.php

一个网页

让输入密码

又继续使用爆破

抓包

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656255153-image-20210115212203744.png)

添加变量

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656272493-image-20210115212233204.png)

添加字典

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656290759-image-20210115212347174.png)

开始爆破

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656311574-image-20210115212421508.png)

得到密码hack

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656329531-image-20210115212504855.png)

得到flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656358081-image-20210115212557406.png)