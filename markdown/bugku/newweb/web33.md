# web33
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661161370-5804302170163.png)
## 题目描述
>fR4aHWwuFCYYVydFRxMqHhhCKBseH1dbFygrRxIWJ1UYFhotFjA=

这道题要下载
先看是啥玩意儿
得到源码
![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618661175644-1397926115847.png)

```php
    1 <?php
    2 function encrypt($data,$key)
    3 {
    4     $key = md5('ISCC');
    5     $x = 0;
    6     $len = strlen($data);
    7     $klen = strlen($key);
    8     for ($i=0; $i < $len; $i++) {▫
    9         if ($x == $klen)
   10         {
   11             $x = 0;
   12         }
 13         $char .= $key[$x];
   14         $x+=1;
   15     }
   16     for ($i=0; $i < $len; $i++) {
 17         $str .= chr((ord($data[$i]) + ord($char[$i])) % 128);
   18     }
   19     return base64_encode($str);
   20 }
   21 ?>
```
是一个加密的代码
算法是这样的
在这之前先说一下前言
变量$data是明文，变量\$key是加密的密钥
变量$key是'ISCC'的md5值
变量$x是0，变量\$len是明文的长度
$klen是\$key的长度
>循环循环$len的长度次数(明文长度有多长就循环多少次)
判断$x是否弱等于\$klen，是就让$x归0，不是就给\$char赋值通过\$x遍历的\$key得到的字符串，然后$x + 1
再次循环$len
遍历明文的accii码值并转换成字符串加上遍历$char的accii码值余128得到的数赋值拼接给\$str
循环结束后返回对$str进行base64的编码的结果

通过已经给出的[密文](#题目描述)去进行逆向计算就可以了
一个一个的用手算会很浪费时间，所以使用脚本进行跑
直接附上一个python写的解码
```python
  1 import hashlib
  2 import base64
  3
  4
  5 def md5_m(data):
  6     md5 = hashlib.md5()
  7     md5.update(data.encode("utf-8"))
  8     return md5.hexdigest()
  9
 10
 11 def flag(data, content):
 12     m = data
 13     m_len = len(m)
 14     m_str = content
 15     m_str = base64.b64decode(m_str).decode()
 16     m_str_len = len(m_str)
 17     x = 0
 18     char = ""
 19     m_str_data = []
 20     f = ""
 21     for i in range(m_str_len):
 22         if x == m_len:
 23             x = 0
 24         chr1 = m[x]
 25         char += chr1
 26         x += 1
 27     for a in range(m_str_len):
 28         s = ord(m_str[a])
 29         m_str_data.append(chr(s))
 30     for s in range(m_str_len):
 31         a = (ord(m_str[s]) - ord(char[s])) % 128
 32         if a < 0:
 33             f += chr(a + 128)
 34         else:
 35             f += chr(a)
 36     print(m)
 37     print(char)
 38     print(f)
 39
 40
 41 v = "ISCC"
 42 z = "fR4aHWwuFCYYVydFRxMqHhhCKBseH1dbFygrRxIWJ1UYFhotFjA="
 43 flag(md5_m(v), z)
```