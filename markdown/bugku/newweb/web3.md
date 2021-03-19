# web3

进入题目

![image-20210316160549164](../../../image/bugku/image-20210316160549164.png)

直接有源码

代码审计

```php
$what=$_GET['what'];
echo $what;
if($what=='flag')
echo 'flag{****}';
```

接收一个$_GET请求，把请求的值赋给$what并打印

再判断$what被赋予的值是否是flag，是的话就打印flag

![image-20210316160810226](../../../image/bugku/image-20210316160810226.png)

得到flag

