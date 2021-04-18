# web12

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656460005-image-20210116105141972.png)

题目描述是本地管理员

进入题目之后在内存源码中找到base64的编码

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656480117-image-20210116105333111.png)

```
dGVzdDEyMw==
```

bp解码得到

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656506193-image-20210116105433165.png)

```
test123
```

盲猜是个密码

盲猜用户是admin

然后使用referer标明我是从本地发送的请求

```
referere: 127.0.0.1
```

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656534560-image-20210116105636141.png)

结果没有返回信息

说明referer标明的ip在某个节点被改掉了

http中还有一个是可以标明客户端的真实地址的就是XFF

```
X-Formwarded-For: 127.0.0.1
```

添加XFF发送请求

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618656564002-image-20210116105937525.png)

得到flag





