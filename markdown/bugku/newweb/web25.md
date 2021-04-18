# web25

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658756536-image-20210119154444935.png)

进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658774380-image-20210119154547502.png)

根据提示估计是sql注入

尝试注入

失败

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658800511-image-20210119154810335.png)

emmm

看一下注册页面

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658816786-image-20210119154852758.png)

使用语句的时候就直接注册成功了。。

那只好先注册看看里面有什么吧

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658832508-image-20210119155054251.png)

使用admin去注册的时候说admin已经存在

哦豁

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658846994-image-20210119155152074.png)

注册成功之后去登陆

回显个这个玩意儿

emmm那估计admin就是管理员了

根据题目的提示说是基于sql的约束注入

属于知识盲区

去网上查了查资料知道了注入的方法

先说一下原理

在SQL语句执行处理字符串的时候，在字符串最末尾的空格符会被清空

例如：

> "hello                                            " 就会等于 "hello"

先创建一个数据库

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658986544-image-20210119161639054.png)

选择数据库

再创建表

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659023196-image-20210119161854067.png)

再插入数据

> username插入"admin"
>
> password插入"password"

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659039463-image-20210119162247398.png)

然后使用where条件去查询

```sql
select * from user where username = 'admin';
```

执行结果

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659052907-image-20210119162617505.png)

再使用"admin                                  " 去查询

```sql
select * from user where username = 'admin                         ';
```

执行结果

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659073411-image-20210119162747738.png)

这两个语句的执行结果是一样的

> 1.对尾部空格符的这种修剪操作，主要是在字符串比较的期间进行的，sql在进行数据字符串对比的时候才会删除尾部的空格符
>
> 2.在所有的insert查询中，sql都会根据创建表的时候设定的字段最大长度，如果插入的字符长度大于设定的最大长度就会截断到符合最大长度的那一部分，例如插入字符“helloworld”，字段最大的长度是6，insert就会插入"hellow",而不是"helloworld"

然后先插入数据

> username插入"admin"
>
> password插入"password1"

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659093124-image-20210119164421804.png)

插入相同的话就会报错

再插入

> username插入"admin                                                          1"
>
> password插入"password1"

>shit!!!!!!!!!!!!!!!!!!!!!!!!!!!!
>
>他mua的这个约束注入我还以为是特性，没想到是一个bug，在版本高的mysql跟mariadb中都已经被修复了，没有截断了只有在版本低的mysql还有mariadb中才有！！！！：(
>
>所有接下来的复现都只接着上文的继续进行

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659111678-image-20210119164421804.png)



这就插入成功了

返回两个独立的用户

但是第二个用户的username后面还是有20个空格

所以它是两个独立的用户

但是因为select的bug会把第二条数据的password的字段当成第一条数据的username的字段

这样就可以使用原始的用户什么登录成功了

根据以上原理

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659126929-image-20210119173319561.png)

在注册中注册一个admin的用户使用过长的payload使它截断

```sql
admin                                 1
```

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659153434-image-20210119173437485.png)

注册成功

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659464965-image-20210119173455111.png)

转跳后登录

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659483005-image-20210119173520645.png)

得到flag

：D