[js的基础](#js的基础)
# js的基础

* js的代码推荐写在js文件里或写在script标签里

* js是严格区分大小写的

* js每一个语句都是用分号(;)结尾

  * 如果不写分号，浏览器会自动添加，但是会消耗一些系统资源

  * 而且有时候，浏览器会加错分号，所以在开发中分号是必须写的

* js会忽略多个空格和换行，所以我们可以利用空格和换行对代码进行格式化

* 字面量，都是一些不可以改变的值
  * 比如: 1 2 3 4 5 6
  * 字面量都是可以直接使用的，但一般不直接使用字面量
  * 变量可以保存字面量，且变量可以任意改变的
  * 在js中使用var关键字来声明一个变量
  * js的声明和赋值是可以同时进行的

		```javascript
		var a;
		a = 123;
		console.log(a);
		var a = 123;
		console.log(a);
		```

* 标识符
	* 标识符一般都是使用驼峰命名法： 每个首字母小写，每个单词的开头字母大写，其余字母小写
  * 在js中所有的可以自主命名的都是可以称为标识符
	* 例如： 变量名、函数名、属性名都属于标识符
	* 在标识符中可以含有字母、数字、\_、$
	* 标识符不能以数字开头
	* 标识符不能以ES中的关键字或保留字
	
	```javascript
	var var = 123;
	console.log(var);
	这个是错误的写法
	```





* 打印语句
   1. alert是一个弹窗指令
			* 语法：
				* alert("Hello world");
				* 可以嵌套到html的标签里，但不建议这样写
	
	2. document是文档指令
			* 语法：
				* document.write("Hello world");
				* document.(指令)+(内容);
	
	3. console是控制台指令
			* 语法：
				* console.log("Hello world");
				* console.(指令)+(内容);
	


