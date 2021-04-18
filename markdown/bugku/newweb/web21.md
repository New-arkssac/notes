# web21

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658169151-image-20210118103015014.png)

进入环境

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658191791-image-20210118103105844.png)

never never never give up!!!永不言弃！

查看f12

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658206614-image-20210118103236972.png)

有一个1p.html

尝试访问

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658225848-image-20210118103322803.png)

访问就自动转跳到别的页面了

这个要抓包才行了

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658246189-image-20210118103455966.png)

抓包得到1p.html的源码

有一些url编码和base64编码的东西很可疑

先解码看看

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658266452-image-20210118103748221.png)

得到base64编码的玩意儿

再解码

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658281031-image-20210118103839035.png)

又得到url编码的

再解码

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658298647-image-20210118103932475.png)

得到源码

重要的语句

```php
if(!$_GET['id'])
{
    header('Location: hello.php?id=1');
    exit()
}
```

这里的意思是变量$id不能传空的参数

```php
if(stripos($a,'.'))
{
    echo 'no no no no no';
    return ;
}
```

这一句的意思限制限制变量$a中不能有字符  **.**

```php
$data = @file_get_contents($a,'r');
if($data=="bugku is a nice plateform!" and $id==0 and strlen($b)>5 and eregi("111".substr($b,0,1),"1114") and substr($b, 0, 1)!=4)
{
    $flag = "flag{*************}"
}
else
{
    print "never never never give ip !!1";
}
```

这里的意思比较绕

变量$a的参数传给变量$data，如果变量$data弱等于字符串bugku is a nice plateform! 和 变量$id弱等于整型数0和变量$b的长度要大于5和不区分大小写的正则表达式匹配字符串1114和字符串111连接变量$b的第一个字符等于4和变量$的第一个字符弱不等于整形4就爆出flag

payload是这样

> hello.php?id=s&b=%0012345&a=php://input
>
> bugku is a nice plateform!

得到flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658318443-image-20210118120721051.png)



