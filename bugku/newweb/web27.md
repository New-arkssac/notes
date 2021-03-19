# web27

![image-20210119203412792](../../../image/image-20210119203412792.png)

题目描述

md5 collision

md5碰撞题

进入环境

![image-20210119203510084](../../../image/image-20210119203510084.png)

please input a

请传参一个a

php是一个弱类型语言

php中的==为弱类型对比

松散比较的==只对比值不对比类型

严格的比较是===三个等号，比较值也比较类型

md5值在php中因为==是松散的比较的原因

所以只要是0e开头的md5值都会被php解析器当作科学计数法去对比

所以bool值就会是true

```php
  1 <?php
  2 $a = "QNKCDZO";
  3 $b = "s878926199a";
  4 echo md5($a) . "<br>";
  5 echo md5($b) . "<br>";
  6 var_dump(md5($a) == md5($b));
```

执行的结果

![image-20210119210046355](../../../image/image-20210119210046355.png)



​	oe开头的md5值有很多请[百度](https://www.baidu.com)

![image-20210119211221516](../../../image/image-20210119211221516.png)

得到flag