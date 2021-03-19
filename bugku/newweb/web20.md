# web20

![image-20210118095303073](../../../image/image-20210118095303073.png)

题目描述:

cookies欺骗

进入环境

![image-20210118095358370](../../../image/image-20210118095358370.png)

进入环境

有一堆不明所以的字母

url栏里有一串base64的编码

![image-20210118095522091](../../../image/image-20210118095522091.png)

解码后得到

> keys.txt

emmmm

这里应该是把文件名给编码之后才能执行

![image-20210118095906068](../../../image/image-20210118095906068.png)

用没编码过的文件名去访问的话没有任何回显

这里文件包含

可以包含keys.txt应该也可以包含主页文件

把index.php给编码过后再访问

![image-20210118100152707](../../../image/image-20210118100152707.png)

![image-20210118100232535](../../../image/image-20210118100232535.png)

但是没有任何回显。。

emmmmmm

想了看了几分钟发现url栏里还GET请求了一个line

line英文有行的意思

就试着输入了一个1

![image-20210118100414530](../../../image/image-20210118100414530.png)

就回显了一串源码

在line那输入2

![image-20210118100503248](../../../image/image-20210118100503248.png)

emmmm

但是这样看着好不方便啊

写个脚本吧

```python
  1 import requests
  2 num = 1
  3 while True:
  4     num += 1
  5     url = 'http://114.67.246.176:18408/index.php?line=' + str(
  6         num) + '&filename=aW5kZXgucGhw'
  7     text = requests.get(url)
  8     print(text.text)
  9     if text.text == '':
 10         exit()
```

得到源码

![image-20210118102257455](../../../image/image-20210118102257455.png)

从源码得知

要请求一个keys.php

而且要cookie等于margin=margin才行

所以抓个bp包

![image-20210118102716698](../../../image/image-20210118102716698.png)

得到flag





