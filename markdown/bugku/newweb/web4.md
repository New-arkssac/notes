# web4

进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618654831803-image-20210316161052733.png)

直接获得源码

```php
$what=$_POST['what'];
echo $what;
if($what=='flag')
echo 'flag{****}';
```

代码审计

获取一个POST请求，把POST请求的值赋值给变量$what

打印变量$what

再判断$what的值是否是flag字符串，是的话就打印flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618654855709-image-20210316161429665.png)

得到flag