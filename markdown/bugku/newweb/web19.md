# web19

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618657834026-image-20210117091916100.png)

题目描述：

> 速度要快！

进入环境

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618657854555-image-20210117092009156.png)

进入环境

让快一些

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618657869032-image-20210117092123499.png)

按F12查看源码

发现有注释信息

一串英文

> OK, now you have to post the margin what you find

> 好吧，现在你提交一个你找到的POST请求参数

大致是这个意思

emmm

在页面找不到啥意思

估计是在报文里

抓个包试一下

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618657883626-image-20210117105543373.png)

解码之后还要再解码一次

但是这个码每次发送都会变化所以要写个脚本去弄才行

直接附上脚本

```python
  1 import requests
  2 import base64
  3
  4 url = 'http://114.67.246.176:19392'
  5 push = requests.session()  
  6 headers = push.get(url).headers
  7
  8 str1 = base64.b64decode(headers['flag'])
  9 str2 = base64.b64decode(repr(str1).split(':')[1])
 10
 11 data = {'margin': str2}
 12 flag = push.post(url=url, data=data)
 13 print(flag.text)
```



