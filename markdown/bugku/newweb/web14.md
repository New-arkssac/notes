# web14

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656796673-image-20210116161727659.png)

进入环境

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656814608-image-20210116161801828.png)

只有一个超链接

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656835649-image-20210116161848630.png)

查看源码发现连接的地址是一个show.php的文件

点击看看

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656853615-image-20210116161952285.png)

emmmm

只有回显index.php的字样

看url有点像文件包含

尝试看看根目录有没有flag.php的文件

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656871115-image-20210116162203676.png)

回显一个oh no

emmm

![image-20210116162240184](D:\ebook\markdown\image/image-20210116162240184.png)

flag.txt也显示同样的字样

那可以确定只要是越过目录就会这样

emmmmm

看看能不能执行php的伪协议来查看源码

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656900336-image-20210116162555086.png)

 ```php
php://filter/read=convert.base64-encode/resource=index.php
 ```

这一句伪协议可以以base64编码的形式回显指定的文件源码

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656922262-image-20210116162744698.png)

得到源码

进行解码

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656938688-image-20210116162925961.png)

得到flag















