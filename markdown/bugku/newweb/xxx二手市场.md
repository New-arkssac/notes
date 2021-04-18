# xxx二手市场

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662264657-image-20210119094447787.png)

进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662281603-image-20210119094540321.png)

emmm类实战题

尝试一下有没有sql注入

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662298297-image-20210119094618779.png)

进入注册页面

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662314502-image-20210119094658604.png)

不能使用特殊字符

emmmm

注册页面有防护，没有注入点

去登录界面看一下

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662334529-image-20210119095218247.png)

也是一个样

emm

那没办法了

只好注册一个用户找找看了

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662352247-image-20210119095335827.png)

登录之后发现可以上传头像

看看是否有文件上传漏洞

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662366517-image-20210119095426844.png)

bp抓包

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662383997-image-20210119095529171.png)

这个是将图片进行base64编码把图片的信息传上服务器

可以按照图片base64编码的格式进行伪装绕过

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662407655-image-20210119095832068.png)

```php
data:image/php;base64,PD9waHAgQGV2YWwoJF9QT1NUW3NoZWxsXSk7Pz4=
```

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662424676-image-20210119100038380.png)

得到绝对路径

使用蚁剑返回shell

选择base64解码

![image-20210119100253404](D:\ebook\markdown\image/image-20210119100253404.png)

然后测试连接

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662480511-image-20210119100308294.png)

测试成功

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662501522-image-20210119100336654.png)

在html目录下找到flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662516323-image-20210119100403766.png)