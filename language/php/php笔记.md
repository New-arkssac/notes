# 函数

str_replace — 子字符串替换

strstr — 查找字符串的首次出现

scandir() 函数 返回指定目录中的文件和目录的数组。
base_convert() 函数 在任意进制之间转换数字，返回一个字符串
dechex() 函数：把十进制转换为十六进制。
hex2bin() 函数：把十六进制值的字符串转换为 ASCII 字符。
readfile() 函数:输出一个文件。该函数读入一个文件并写入到输出缓冲。若成功，则返回从文件中读入的字节数。若失败，则返回 false。您可以通过 @readfile() 形式调用该函数，来隐藏错误信息。

file_get_content函数:将整个文件读入一个字符串

file_get_contents(chr(47).chr(102).chr(49).chr(97).chr(103).chr(103))=file_get_contents(/f1agg)

preg_match — 执行匹配正则表达式

unserialize — 从已存储的表示中创建 PHP 的值,反序列化，将字符串转化为类。

serialize()：序列化，将类转化为字符串

file_get_contents — 将整个文件读入一个字符串

*require_once* 语句和 [require](https://www.php.net/manual/zh/function.require.php) 语句完全相同，唯一区别是 PHP 会检查该文件是否已经被包含过，如果是则不会再次包含

变量：
local #局部变量
global #全局变量
static #静态变量
parameter #参数

 1.PHP 定界符 EOF 的作用就是按照原样，包括换行格式什么的，输出在其内部的东西；
 2.在 PHP 定界符 EOF 中的任何特殊字符都不需要转义；
 3.PHP 定界符 EOF

数据类型：
echo - 可以输出一个或多个字符串
print - 只允许输出一个字符串，返回值总为 1

 var_dump() 函数返回变量的数据类型和值：

对象数据类型也可以用于存储数据。

在 PHP 中，对象必须声明。

首先，你必须使用class关键字声明类对象。类是可以包含属性和方法的结构。

然后我们在类中定义数据类型，然后在实例化的类中使用数据类型：

echo，print，print_r，var_dump 的区别

1.echo

输出一个或者多个字符串。

2.print

和 echo 最主要的区别： print 仅支持一个参数，并总是返回 1。

3.print_r

打印关于变量的易于理解的信息,如果给出的是 string、integer 或 float，将打印变量值本身。如果给出的是 array，将会按照一定格式显示键和元素。object 与数组类似。 记住，print_r() 将把数组的指针移到最后边。使用 reset() 可让指针回到开始处。

4.var_dump

此函数显示关于一个或多个表达式的结构信息，包括表达式的类型与值。数组将递归展开值，通过缩进显示其结构。

5.var_dump 和 print_r 的区别

var_dump 返回表达式的类型与值而 print_r 仅返回结果，相比调试代码使用 var_dump 更便于阅读。

6.超级全局变量
$GLOBALS  是一个包含了全部变量的全局组合数组。变量的名字就是数组的键。
$_SERVER 是一个包含了诸如头信息(header)、路径(path)、以及脚本位置(script locations)等等信息的数组。这个数组中的项目由 Web 服务器创建。不能保证每个服务器都提供全部项目；服务器可能会忽略一些，或者提供一些没有在这里列举出来的项目_

![image-20200727114506096](C:\Users\爽爽\AppData\Roaming\Typora\typora-user-images\image-20200727114506096.png)

![image-20200727114538816](C:\Users\爽爽\AppData\Roaming\Typora\typora-user-images\image-20200727114538816.png)$REQUEST  用于收集HTML表单提交的数据。
$_POST      被广泛应用于收集表单数据，在HTML form标签的指定该属性："method="post"
$_GET 		同样被广泛应用于收集表单数据，在HTML form标签的指定该属性："method="get"。
$_FILES
$_ENV        通过环境方式传递给当前脚本的变量的数组
$COOKIE  通过 HTTP Cookies 方式传递给当前脚本的变量的数组
$SESSION  当前脚本可用 SESSION 变量的数组。更多关于如何使用的信息

![image-20200727114954645](C:\Users\爽爽\AppData\Roaming\Typora\typora-user-images\image-20200727114954645.png)



## 7.while 循环



while 循环将重复执行代码块，直到指定的条件不成立。

### 语法

```php
while (条件)
{
    要执行的代码;
}
```



## do...while 语句

do...while 语句会至少执行一次代码，然后检查条件，只要条件成立，就会重复进行循环。

### 语法

```php
do
{
    要执行的代码;
}
while (条件);
```







## 8.For循环

## for 循环

for 循环用于您预先知道脚本需要运行的次数的情况。

### 语法

```php
for (初始值; 条件; 增量)
{
    要执行的代码;
}
```

参数：

- **初始值**：主要是初始化一个变量值，用于设置一个计数器（但可以是任何在循环的开始被执行一次的代码）。
- **条件**：循环执行的限制条件。如果为 TRUE，则循环继续。如果为 FALSE，则循环结束。
- **增量**：主要用于递增计数器（但可以是任何在循环的结束被执行的代码）。

**注释：**上面的**初始值**和**增量**参数可为空，或者有多个表达式（用逗号分隔）。



## foreach 循环

foreach 循环用于遍历数组。

### 语法

```php
foreach ($array as $value)
{
    要执行代码;
}
```

每进行一次循环，当前数组元素的值就会被赋值给 $value 变量（数组指针会逐一地移动），在进行下一次循环时，您将看到数组中的下一个值。



## PHP函数

函数是通过调用函数来执行的。

## 语法

```php
<?php
function functionName()
{
    // 要执行的代码
}
?>
```

PHP 函数准则：

- 函数的名称应该提示出它的功能
- 函数名称以字母或下划线开头（不能以数字开头）

## PHP 函数 - 添加参数

为了给函数添加更多的功能，我们可以添加参数，参数类似变量。

参数就在函数名称后面的一个括号内指定。

### 实例 1

下面的实例将输出不同的名字，但姓是相同的：

## 实例

```php
<?php
function writeName($fname)
{
    echo $fname . " Refsnes.<br>";
}
 
echo "My name is ";
writeName("Kai Jim");
echo "My sister's name is ";
writeName("Hege");
echo "My brother's name is ";
writeName("Stale");
?>
```

输出：

```
My name is Kai Jim Refsnes.
My sister's name is Hege Refsnes.
My brother's name is Stale Refsnes.
```

### 实例 2

下面的函数有两个参数：

## 实例

```php
<?php
function writeName($fname,$punctuation)
{
    echo $fname . " Refsnes" . $punctuation . "<br>";
}
 
echo "My name is ";
writeName("Kai Jim",".");
echo "My sister's name is ";
writeName("Hege","!");
echo "My brother's name is ";
writeName("Ståle","?");
?>
```

输出：

```
My name is Kai Jim Refsnes.
My sister's name is Hege Refsnes!
My brother's name is Ståle R
```



## PHP 函数 - 返回值

如需让函数返回一个值，请使用 return 语句

## 实例

```php
<?php
function add($x,$y)
{
    $total=$x+$y;
    return $total;
}
 
echo "1 + 16 = " . add(1,16);
?>
```

输出：

```
1 + 16 = 17
```

# 魔法常量

__ LINE __                //文件夹中的当前行号

__ FILE __     			//文件的完整路径和文件名。如果用在被包含的文件中，则返回被包含的文件名。

__ DIR __				  //文件所在的目录。如果用在被包括文件中，则返回被包括的文件所在的目录

__ FUNCTION __  	// 返回该函数被定义时的名字（区分大小写）

__ CLASS __			 //类的名称，该类被定义时的名字

__ TRAIT __			 //代码复用

__ METHOD __  	//返回该方法被定义时的名字（区分大小写）

__ NAMESPACE __  //当前命名空间的名称（区分大小写）





# 正反序列化

__construct()            //对象创建的时候调用此方法

__destruct()             //对象销毁的时候调用此方法：unset函数释放   网页执行完毕自动销毁

__sleep()                 //序列化对象时 调用此方法

__wakeup()             //反序列化字符串的时候调用此方法

__toString()            //把类当作字符串使用时触发

__get()                   //用于从不可访问的属性读取数据时触发

__set()         		  //用于将数据写入不可访问的属性

__isset()                //在不可访问的属性上调用isset()或empty()触发

__invoke()         	//当脚本尝试将对象调用为函数时触发

Serialize                 //可以将变量转换韦字符串并且在转换中可以保存当前的值

unserialize             // 可以将serialize生成的字符串变换回变量



```
O:4:"test":2:{s:10:"testflag";s:9:"flag{233}";s:1:"a";s:3:"aaa";}
```



