# web2

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649110790-Screenshot_20200930_195042.png)

## 进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649134588-Screenshot_20200930_200140.png)



看到一堆js特效

按照惯例，先看查看源码

按下F12

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649278098-image1.png)

得到flag

# web3

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649369552-image19.png)

## 进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649406968-image20.png)

## 解题过程

看到alert弹窗

按Ctrl+u查看源码

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649496192-image21.png)

在最底下找到一串HTML的编码

用bp解码

## 得到flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649561272-image22.png)

# web基础$_GET

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649640765-image7.png)

## 进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649676664-image8.png)

得到题目

## 过程

代码审计

这一段代码的意思是接收一个GET请求

要求GET请求的what等于flag

构造

what=flag

## 得到flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649779615-image9.png)



# web基础$_POST

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649841961-image10.png)

## 进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649870049-image11.png)

## 过程

这段代码的意思是

接收一个POST请求

要求what等于flag

bp抓个包

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618649921051-image12.png)

修改请求头

把GET改为POST

添加POST请求头

Content-Type: application/x-www-form-urlencoded

在添加内容

what=flag

## 得到flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650013876-image13.png)

# 变量1

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650075447-image33.png)

## 题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650097629-image34.png)

题目就是代码审计要一个GET请求

代码审计，这里需要知道一个知识点可变变量 可变变量是一种独特的变量

它允许动态改变一个变量名称。其原理是 变量的名称由另外一个变量的值来确定

即一个可变变量获取了一个普 通变量的值作为这个可变变量的变量名

实现过程是在变量前面多加美 元符号 “$” 我们的目标是得到flag

由于代码含有正则匹配，文件上传、本地包含 等漏洞不能用，而PHP中$GLOBALS[index] 的数组中存储了所有全局变 量 所以我们构造

`payload http://123.206.87.240:8004/index1.php?args=GLOBALS`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650377686.png)

# 计算器

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650472105-image2.png)

## 进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650505671-image3.png)

## 过程

要计算红框的值

但是只能输入一个字符

修改一下js代码就好了

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650559296-image4.png)

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650591776-image5.png)



## 得到flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650623446-image6.png)

# 矛盾

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650733805-image14.png)

## 进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650769930-image17.png)

## 过程

得到源码
源码的意思是
GET请求一个num的变量
然后用is_numeric()函数检测$num是否为数字或者是数字字符串
然后is_numeric()函数前面有一个!这个就使$num不能是数字或者是数字字符串了
再接下来就是如果$num等于1的话就打印flag
知道意思之后就可以构造参数了
?num=1a

## 得到flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650872729-image18.png)

# 你必须让他停下来

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650915035-image26.png)

## 进入题目

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618650985648-image27.png)

## 解题过程

看到网页一直在转跳

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618651028779-image28.png)

看到图片标签里有注释flag is hert

这是在说flag在图片的标签里

后我在打开了一次源码发现每次转跳的时候

图片就会不一样

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618651083798-image29.png)

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618651102170-image30.png)

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618651131929-image31.png)

估计flag就在某个图片的标签里

这样重复看源码效率太慢了用bp抓包

一直重发到10.jpg的时候flag出现了（我不会说其实是我刚好抓到有flag的包的:D）

## 得到flag

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618651207917-image32.png)

# 域名解析

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618651247772-image23.png)

## 解题过程

这道题很简单

直接编辑一下自己本地的hosts文件就行了

给hosts文件里添加

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618651315228-image24.png)

## 得到flag

访问网址就行了

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618651347153-image25.png)





