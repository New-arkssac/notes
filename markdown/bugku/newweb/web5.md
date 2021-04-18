# web5

进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618654967945-image-20210316161545171.png)

直接得到源码

代码审计

```php
$num=$_GET['num'];
if(!is_numeric($num))
{
echo $num;
if($num==1)
echo 'flag{**********}';
}
```

变量$num被赋值$_GET请求得到的值

再取反判断is_numertic来判断变量$num是否是数字或者数字字符串

不是就打印变量$num

然后判断$num的值是否是整数`1`

是就打印flag

这里就要说一下php这个弱语言的弱比较了

在php中`==`这个比较是不严格的比较

只比较值，不会去比较类型的

在别的语言里`1='1'`是返回false

python

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618654998027-image-20210316164239403.png)

php

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618655014333-image-20210316164417973.png)

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618655041248-image-20210316170248550.png)

php在弱比较的时候会把以数字开头的字符串转换成数字进行比较，必须是开头是数字，如果开头不是数字就会返回false(此方法在php8失效)

然后呢题里的

!is_numeric取反，传入的值不能是字符的1或者是整形的1

这时候可以传入1a(1和任意字符)

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618655074808-image-20210316170354192.png)

得到flag

