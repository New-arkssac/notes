```php
<!DOCTYPE html>>
<html>

<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
	<title>获取POST参数</title>
</head>

<body>
	<form action="" method="post">
		用户名：<input type="text" name="username" /><br />
		密码：<input type="password" name="password" /><br />
		留言：<br />
		<textarea name="msg"></textarea><br />
		<input type="submit" value="提交" /><br />
	</form>

</html>

<?php
if ($_POST) {
	$username = isset($_POST['username']) ? $_POST['username'] : '';   // 获取用户输入的用户名 
	$password = isset($_POST['password']) ? $_POST['password'] : '';   // 获取用户输入的密码
	$msg = isset($_POST['msg']) ? $_POST['msg'] : '';                  // 获取用户输入的留言内容 

	echo '您输入的用户名为：' . $username . '<br/>';     // 把获取的用户名输出到页面
	echo '您输入的密码为：' . $password . '<br/>';       // 把获取的用户密码输出到页面
	echo '您输入的留言内容为：' . $msg . '<br/>';        // 把获取的用户留言内容输出到页面
}
```
