# web35

![img](../../../image/bugku/3400641220164.png)
题目描述
>点了login咋没反应

进入题目
![img](../../../image/bugku/1981642238590.png)
有个表单
但是login点不了
估计是button那有不让点击的元素
查看源码
![img](../../../image/bugku/4255743226457.png)
发现没有东西
emmmmmmmmm
![img](../../../image/bugku/2119144246623.png)
在头部信息中发现有一个css的文件
查看一下
![img](../../../image/bugku/2779845239292.png)
介四个嘛？？
>try ?32371

试试?32371
emmmmmmm
哦哦哦~！！我晓得了！
试着请求一下?32371
![img](../../../image/bugku/4966947235847.png)
得到源码
```php
<?php
error_reporting(0);
$KEY='ctf.bugku.com';
include_once("flag.php");
$cookie = $_COOKIE['BUGKU'];
if(isset($_GET['32371'])){
    show_source(__FILE__);
}
elseif (unserialize($cookie) === "$KEY")
{   
    echo "$flag";
}
else {
?>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>Login</title>
<link rel="stylesheet" href="admin.css" type="text/css">
</head>
<body>
<br>
<div class="container" align="center">
  <form method="POST" action="#">
    <p><input name="user" type="text" placeholder="Username"></p>
    <p><input name="password" type="password" placeholder="Password"></p>
    <p><input value="Login" type="button"/></p>
  </form>
</div>
</body>
</html>

<?php
}
?>
```
代码的意思是
变量$KEY的值'ctf.bugku.com'
包含flag.php文件
变量$cookie等于特殊变量\$\_COOKIE接收一个'BUGKU'的键
判断\$_GET请求的32371是否为空,不为空就高亮文件代码，或者判断反序列化后的变量$cookie是否强等于\$KEY，满足条件就打样flag
否则就执行html代码

挺简单的
先序列化变量$KEY
![img](../../../image/bugku/1326256231601.png)

```php
<?php
$KEY = 'ctf.bugku.com';
print(serialize("$KEY"));
?>
```
得到
> s:13:"ctf.bugku.com";

然后传cookie过去
![img](../../../image/bugku/5418758249481.png)
得到flag