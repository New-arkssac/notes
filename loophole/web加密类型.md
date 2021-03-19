CTF中的密码类题目脑洞大开，对很多加密方式还是不够熟悉，对以前做过的密码题目做个简单的总结，小白一只，大牛勿喷。。

1、MD5加密：

此类密码容易辨别，一般为16位或32位大小写字母数字混合字符串。密码解密可以在线解密，也可使用各种解密小工具解密，出现频率高，但较为简单，容易识别，容易解密。

注：解密可能出现33位的字符串，此时应判别多余的字符，去掉后解密。

密码样式：81bdf501ef206ae7d3b92070196f7e98

2、ascll编码：

使用指定的7 位或8 位二进制数组合来表示128 或256 种可能的字符。标准ASCII 码也叫基础ASCII码，使用7 位二进制数（剩下的1位二进制为0）来表示所有的大写和小写字母，数字0 到9、标点符号， 以及在美式英语中使用的特殊控制字符。

此类密码一般为一串数字。可以在线或工具解密。

注：做题过程中出现过二进制的Ascll 码 在线解密得到字符串。

密码样式：11910110899111109101116111115104105121971109897114

![ldvv737u0r](../../image/ascii表.jpeg)

3、Base64/32/16编码：

常见的此类密码一般后边是=或== 容易判别

特征：密文字符串的长度为4的整数倍。字符串的符号取值只能在A-Z, a-z, 0-9, +, /, =共计65个字符中，且=如果出现就必须在结尾出现。

密码样式：aGVsbG8=（共八位为base64）

4、莫尔斯电码：

此类密码是.-两种字符组成的。一般结合音频的摩斯电码得到，此时会用到工具

Audacity 根据波形图得到摩斯电码 在线解密得到明文。

注：出现的密文可能不是.-两种字符，是其他的两种字符，此时需要转化为.-两种字符。

密码样式：-- --- .-. ... . ..--.- .. ... ..--.- -.-. --- --- .-.. ..--.- -... ..-

![0pjjyo13kp](../../image/2000534-f4d27b41c1297902.webp)



5、URL编码：

url编码是一种浏览器用来打包表单输入的格式。浏览器从表单中获取所有的name和其中的值 ，将它们以name/value参数编码（移去那些不能传送的字符，将数据排行等等）作为URL的一部分或者分离地发给服务器。任何特殊的字符（就是那些不是简单的七位ASCII，如汉字）将以百分符%用十六进制编码，当然也包括象 =,&；，和 % 这些特殊的字符。其实url编码就是一个字符ascii码的十六进制。不过稍微有些变动，需要在前面加上“%”。比如“\”，它的ascii码是92，92的十六进制是5c，所以“\”的url编码就是%5c。那么汉字的url编码呢？很简单，看例子：“胡”的ascii码是-17670，十六进制是BAFA，url编码是“%BA%FA”。

特征：一串%加两个字符的样式。特征明显，出现后容易解密。

密码样式：%68%65%6c%6c%6f

6、hex编码：

特征：密文开头是0xk 后边是一串数字。

密码样式：0x68656c6c6f

7、 brainfuck：

是一种极小化的计算机语言，它是由Urban Müller在1993年创建的。

简称BF密文中出现的的字符有：'+-.[]' 可在线解密。

8、Unicode编码：

例如：原文本：You had me at hello

编码后\u0059\u006f\u0075\u0020\u0068\u0061\u0064\u0020\u006d\u0065\u0020\u0061\u0074\u0020\u0068\u0065\u006c\u006c\u006f

9、AES：

密码学中的高级加密标准（Advanced Encryption Standard，AES），又称Rijndael加密法，是美国联邦政府采用的一种区块加密标准。这个标准用来替代原先的DES，已经被多方分析且广为全世界所使用。做题过程中遇到过一个aes加密，题目给了提示，是AES加密。

密码样式：U2FsdGVkX1+qtU8KEGmMJwGgKcPUK3XBTdM+KhNRLHSCQL2nSXaW8++yBUkSylRp

10、DES:

DES全称为Data Encryption Standard，即数据加密标准，是一种使用密钥加密的块算法是一种对称加密算法。是一种比较传统的加密方式，其加密运算、解密运算使用的是同样的密钥。

11、ripleDes解码与Rabbit解码：

做题过程中遇到过一次同时使用ripleDes解码与Rabbit解码 的题目，但是是根据提示得知这两种方法。出现字母大小写、数字、+、=、/ 用此方式解密。一个ripleDes解码与Rabbit解码 解密的网站：https://www.sojson.com/encrypt_rabbit.html

12、栅栏密码：

栅栏密码，就是把要加密的明文分成N个一组，然后把每组的第1个字连起来，形成一段无规律的话。 不过栅栏密码本身有一个潜规则，就是组成栅栏的字母一般不会太多。（一般不超过30个，也就是一、两句话）是一种换位密码，明文与密文的字母种类是一样的。解密方法：用工具测试。栏数一般为字符数的因数。

13、列置换：

接触到的列置换一般是利用提交flag的格式即：CTF{} 来进行列置换。

14、凯撒密码：

典型的替换密码，通过把字母移动一定的位数来实现加密和解密。明文中的所有字母都在字母表上向后（或向前）按照一个固定数目进行偏移后被替换成密文。

解密方法是通过解密工具得到最终结果。

![s0m6yt2c](../../image/s0m6yt2c.jpeg)

### 15.Brainfuck/Ook!编码

例：

Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook? Ook. Ook? Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook! Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook! Ook! Ook! Ook!
Ook! Ook! Ook? Ook. Ook? Ook! Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook? Ook. Ook? Ook! Ook. Ook? Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook! Ook? Ook.
Ook? Ook! Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook! Ook! Ook!
Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook!
Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook? Ook.
Ook? Ook! Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook!
Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook!
Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook? Ook. Ook? Ook! Ook. Ook? Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook? Ook. Ook? Ook! Ook. Ook? Ook. Ook. Ook! Ook.
Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook!
Ook! Ook! Ook! Ook! Ook! Ook? Ook. Ook? Ook! Ook. Ook? Ook! Ook! Ook! Ook!
Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook?
Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook?
Ook. Ook? Ook! Ook. Ook? Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook!
Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook! Ook. Ook. Ook. Ook! Ook. Ook. Ook. Ook! Ook. Ook. Ook. Ook! Ook.
Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook!
Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook? Ook. Ook? Ook! Ook. Ook? Ook. Ook.
Ook. Ook. Ook. Ook. Ook! Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook! Ook. Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook! Ook. Ook.
Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook! Ook? Ook! Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook.
Ook. Ook? Ook. Ook? Ook! Ook. Ook? Ook. Ook. Ook. Ook. Ook. Ook. Ook. Ook.
Ook. Ook. Ook. Ook. Ook! Ook. Ook? Ook.

 为Ook!编码，在线转文本后为flag{ok-ctf-1234-admin}



```
+++++ +++++ [->++ +++++ +++<] >++.+ +++++ .<+++ [->-- -<]>- -.+++ +++.<



++++[ ->+++ +<]>+ +++.< +++[- >---< ]>--- .---- .<+++ ++++[ ->--- ----<



]>--- ----- ----- .<+++ ++++[ ->+++ ++++< ]>+++ ++.<+ +++++ +[->- -----



-<]>. <++++ ++++[ ->+++ +++++ <]>++ .<+++ [->-- -<]>- ----. <++++ +++[-



>---- ---<] >---- ----. +++++ +..++ +++.+ .<+++ [->-- -<]>- --.<+ +++++



+[->+ +++++ +<]>+ ++.++ +.+++ +++++ +.--- -.+++ ++.<+ ++[-> +++<] >++++



++.<
```

这个为brainfuck，在线解码网站解码即可。

附上链接：[Brainfuck/Ook!在线编码解码](https://www.splitbrain.org/services/ook)

#### 16.当铺密码

   当铺密码就是一种将中文和[数字](https://www.33iq.com/index/link?url=https://wapbaike.baidu.com/item/数字/6204)进行转化的[密码](https://www.33iq.com/index/link?url=https://wapbaike.baidu.com/item/密码/65553)，[算法](https://www.33iq.com/index/link?url=https://wapbaike.baidu.com/item/算法)相当简单:当前汉字有多少笔画出头，就是转化成数字几。例如：

#### 

王夫 井工 夫口 由中人 井中 夫夫 由中大：67 84 70 123 82 77 125



#### 17.培根密码

   培根密码中的ab,代表的是数学二进制中的0和1.通过下列的密码表进行加密和解密：
第一种方式：
A aaaaa B aaaab C aaaba D aaabb E aabaa F aabab G aabba H aabbb I abaaa J abaab
K ababa L ababb M abbaa N abbab O abbba P abbbb Q baaaa R baaab S baaba T baabb
U babaa V babab W babba X babbb Y bbaaa Z bbaab
第二种方式
a AAAAA g AABBA n ABBAA t BAABA
b AAAAB h AABBB o ABBAB u-v BAABB
c AAABA i-j ABAAA p ABBBA w BABAA
d AAABB k ABAAB q ABBBB x BABAB
e AABAA l ABABA r BAAAA y BABBA

f AABAB m ABABB s BAAAB z BABBB

感兴趣的可以参考大牛的文章：[培根密码](http://www.360doc.com/content/15/0222/14/21874787_450056531.shtml)

18.ROT5/13/18/47编码

  

ROT5、ROT13、ROT18、ROT47 编码是一种简单的码元位置顺序替换暗码。此类编码具有可逆性，可以自我解密，主要用于应对快速浏览，或者是机器的读取，而不让其理解其意。

ROT5 是 rotate by 5 places 的简写，意思是旋转5个位置，其它皆同。下面分别说说它们的编码方式：
**ROT5**：只对数字进行编码，用当前数字往前数的第5个数字替换当前数字，例如当前为0，编码后变成5，当前为1，编码后变成6，以此类推顺序循环。
**ROT13**：只对字母进行编码，用当前字母往前数的第13个字母替换当前字母，例如当前为A，编码后变成N，当前为B，编码后变成O，以此类推顺序循环。
**ROT18**：这是一个异类，本来没有，它是将ROT5和ROT13组合在一起，为了好称呼，将其命名为ROT18。

**ROT47**：对数字、字母、常用符号进行编码，按照它们的ASCII值进行位置替换，用当前字符ASCII值往前数的第47位对应字符替换当前字符，例如当前为小写字母z，编码后变成大写字母K，当前为数字0，编码后变成符号_。用于ROT47编码的字符其ASCII值范围是33－126

**例：Good Day经过ROT47加密后为v@@5 s2JP [ROT5/13/18/47在线加解密](http://www.qqxiuzi.cn/bianma/ROT5-13-18-47.php)**



##### 19.Rabbit加密

   就给出几个例子参考下好了。。。

明文I Love You小可爱无密匙加密后密文为U2FsdGVkX1/ouFei55jKdzY1fWNS4jxHVNf/AfKWjnBrOGY=

明文I Love You 521无密匙加密后密文为U2FsdGVkX19DvuEo5PvBA8TuLrM2t+EZBvUkzlAa

明文I Love You 521密匙为666加密后密文为U2FsdGVkX18w6vxXxux/ivRVwo3xMzTxmUyk7cHz

[Rabbit在线加解密](http://www.sojson.com/encrypt_rabbit.html)

20.JSFuck

JSFuck 可以让你只用 6 个字符 !+ 来编写 JavaScript 程序。
[][([]+[])[+[[+[]]]]+([][[]]+[])[+[[!+[]+!+[]+!+[]+!+[]+!+[]]]]+([]+[])[+[[!+[]+!+[]]]]+(![]+[])[+[[+[]]]]+(![]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+!+ []]]]][([][([]+[])[+[[+[]]]]+([][[]]+[])[+[[!+[]+!+[]+!+[]+!+[]+!+[]]]]+([]+[])[+[[!+[]+!+[]]]]+(![]+[])[+[[+[]]]]+(![]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+!+[]]]]]+[])[+[[!+[]+!+[]+!+[]]]]+([][([]+[])[+[[+[]]]]+([][[]]+[])[+[[!+[]+!+[]+!+[]+!+[]+!+[]]]]+([]+[])[+[[!+[]+!+[]]]]+(![]+[])[+[[+[]]]]+(![]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+!+[]]]]]+[])[+[[!+[]+!+[]+!+[]+!+[]+!+[]+!+[]]]]+([][[]]+[])[+[[+!+[]]]]+([]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+[]]]]+(![]+[])[+[[+!+[]]]]+([][[]]+[])[+[[+[]]]]+([][([]+[])[+[[+[]]]]+([][[]]+[])[+[[!+[]+!+[]+!+[]+!+[]+!+[]]]]+([]+[])[+[[!+[]+!+[]]]]+(![]+[])[+[[+[]]]]+(![]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+!+[]]]]]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+[]]]]+([][([]+[])[+[[+[]]]]+([][[]]+[])[+[[!+[]+!+[]+!+[]+!+[]+!+[]]]]+([]+[])[+[[!+[]+!+[]]]]+(![]+[])[+[[+[]]]]+(![]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+!+[]]]]]+[])[+[[!+[]+!+[]+!+[]+!+[]+!+[]+!+[]]]]+(![]+[])+[[+!+[]]]][+[[+!+[]]]]+([]+[])[+[[!+[]+!+[]]]]+(![]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+!+[]]]]+(![]+[])[+[[+[]]]]+([][([]+[])[+[[+[]]]]+([][[]]+[])[+[[!+[]+!+[]+!+[]+!+[]+!+[]]]]+([]+[])[+[[!+[]+!+[]]]]+(![]+[])[+[[+[]]]]+(![]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+!+[]]]]]+[])[+[[+!+[]]]+[[!+[]+!+[]+!+[]+!+[]+!+[]]]]+[+!+[]]+([][([]+[])[+[[+[]]]]+([][[]]+[])[+[[!+[]+!+[]+!+[]+!+[]+!+[]]]]+([]+[])[+[[!+[]+!+[]]]]+(![]+[])[+[[+[]]]]+(![]+[])[+[[!+[]+!+[]+!+[]]]]+(![]+[])[+[[+!+[]]]]]+[])[+[[+!+[]]]+[[!+[]+!+[]+!+[]+!+[]+!+[]+!+[]]]])()

其他的一些表达：
false => []
true => ![]
undefined => [][[]]
NaN => +[[]]
0 => +[]
1 => +!+[]
2 => !+[]+!+[]
10 => [+!+[]]+[+[]]
Array => []
Number => +[]
String => []+[]
Boolean => []
Function => []["filter"]
eval => []["filter"]["constructor"](https://blog.csdn.net/weixin_33816821/article/details/CODE)()
window => []["filter"]["constructor"](https://blog.csdn.net/weixin_33816821/article/details/"return this")()
可以使用firebug直接解密.
[JsFuck在线解密](http://www.jsfuck.com/)