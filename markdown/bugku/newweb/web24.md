# web24

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658551604-image-20210120151656440.png)

进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658575592-image-20210120151722227.png)

有一些骚话

惯例查看一下源码

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658604721-image-20210120151826784.png)

发现一个a标签

点开它

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658620318-image-20210120151917470.png)

一个code.txt

文件

还有php源码

```php
<?php
if(isset($_GET['v1']) && isset($_GET['v2']) && isset($_GET['v3'])){
    $v1 = $_GET['v1'];
    $v2 = $_GET['v2'];
    $v3 = $_GET['v3'];
    if($v1 != $v2 && md5($v1) == md5($v2)){
        if(!strcmp($v3, $flag)){
            echo $flag;
        }
    }
}
?>
```

源码意思是

判断v1v2v3三个请求是否为空，不为空就把值传给变量$v1\$v2$v3

要判断变量\$v1和\$v2不相等，但是变量\$v1的md5值和$v2的md5值相等

再使用!strcmp判断变量$v3和\$flag二进制安全比较不成立就打印flag

emmm

第一个判断这里

然后md5这个函数不能对数组进行加密

所以在后台里就会报错然后数组里的值就是NULL

然后两个NULL进行弱比较就是 true了

```php
  1 <?php
  2 error_reporting(0);
  3 $a = $_GET['a'];
  4 $b = $_GET['b'];
  5 var_dump(md5($a) == md5($b));
  6 echo "<br>";
  7 var_dump(md5($a));
  8 echo "<br>";
  9 var_dump(md5($b));
```

这里代码执行结果

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658681060-image-20210120154208478.png)



第一个判断解决了绕过了到第三个判断

strcmd是二进制安全对比

然后它有一个！

所以是让这个对比不成立才行

这个也是可以用数组进行绕过的

因为数组无法与字符串进行对比

```php
  1 <?php
  2 error_reporting(0);
  3 $a = $_GET['a'];
  4 $b = $_GET['b'];
  5 var_dump(strcmp($a, $b));
  6 if (!strcmp($a, $b)) {
  7    echo "hello";
  8 }
```

运行结果

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658698749-image-20210120154730629.png)

这样就可以进行绕过了

回到题目

payload

> ?v1[]=1&v2[]=2&v3[]=3

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658712411-image-20210120154828173.png)

得到flag

