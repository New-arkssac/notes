# HTTP请求信息

**HTTP协议**

- 什么是协议？

  - > 协议就是双方或多方都遵守的一个规则、规范就是协议
  
- 什么是HTTP协议？

  - > HTTP是一个超文本传输协议(Hypertext Transfer Protocol)
  >
    > 是一个简单的请求响应的协议
    >
    > HTTP 是应用层协议，通常使用在tcp传输中
    >
    > 是为了实现某一类具体应用的协议
  
- HTTP的由来

  - > [万维网](https://baike.baidu.com/item/万维网/215515)WWW（World Wide Web）发源于欧洲日内瓦量子物理实验室CERN，正是WWW技术的出现使得因特网得以超乎想象的速度迅猛发展。这项基于TCP/IP的技术在短短的十年时间内迅速成为已经发展了几十年的Internet上的规模最大的信息系统，它的成功归结于它的简单、实用。在WWW的背后有一系列的协议和标准支持它完成如此宏大的工作，这就是Web协议族，其中就包括HTTP超文本传输协议。
    >
    > 在1990年，HTTP就成为WWW的支撑协议。当时由其创始人WWW之父蒂姆·贝纳斯·李（TimBerners—Lee）提出，随后WWW联盟（WWW Consortium）成立，组织了IETF（Internet Engineering Task Force）小组进一步完善和发布HTTP
    >
    > ​																									————摘自百度百科

- HTTP不只是浏览器可以发协议，HTTP协议只是一个规范，只要符合这个规范什么工具都可以发

- 

  



**请求**：

![image-20210114104806287](../image/image-20210114104806287.png)

1. 请求行

   1. GET就是请求的方法 method
   2. / 是请求的资源，就是请求web目录下的默认文件（及主页）
   3. HTTP/1.1 就是请求所使用的1.1版本（1.0，0.9现在不常用了，常用的是1.1）

2. 请求头信息

   1. ![image-20210114105843041](..	/image/image-20210114105843041.png)

      > 请求头部信息结束后，是需要有一个空行的
      >
      > 这个空行是表示请求头部信息已经结束
      >
      > 开始主体信息
      >
      > 即使没有主体信息，也是需要此空行

3. 主体信息

   1. 主体信息可以分为两种

      1. 请求头部主体信息

         > 请求头部信息是客户端发送给服务端的主体信息

      2. 响应头部主体信息

         > 响应头部信息是服务端根据客户端发送的头部主体信息进行判断处理后返回给客户端的头部信息
         >
         > 如果请求头是空的，就会返回默认预设好的主体信息

   2. 请求的主体信息（常用）

      | Header          | 解释                                                         | 实例                                              |
      | :-------------- | ------------------------------------------------------------ | :------------------------------------------------ |
      | Host            | 请求的服务器的域名和端口号                                   | Host: www.baidu.com                               |
      | Referer         | 请求从哪里来的                                               | Referer: 127.0.0.1                                |
      | Accept          | 指定客户端能够接受的内容类型                                 | Accept: text/plain, text/html                     |
      | Accept-Charset  | 浏览器可以接受的字符编码集                                   | Accept: Charset: iso-8859-5                       |
      | Accept-Encoding | 指定浏览器可以支持的web服务器返回内容压缩编码类型            | Accept-Encoding: compress, gzip                   |
      | Accept-language | 浏览器可接受的语言                                           | Accept-language: en,zh                            |
      | Authorization   | HTTP授权的授权证书                                           | Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ== |
      | Cookie          | HTTP请求发送时，会把保存在该请求域名下的所有cookie值一起发送给web服务器 | Cookie: $Version=1; Skin=new;                     |
      | Content-Length  | 请求内容的长度                                               | Content-Length: 348                               |
      | Content-Type    | 请求的与实体对应的MIME信息                                   | Content-Type: application/x-www-form-urlencoded   |
      | Date            | 请求发送的日期和时间                                         | Date: Tue, 15 Nov 2010 08:12:31 GMT               |
      | User-Agent      | User-Agent的内容包含发出请求的用户信息（及客户端浏览器版本） | User-Agent: Mozilla/5.0 (Linux; X11)              |

   3. 响应的主体信息（常用）

      | Header           | 解释                                             | 实例                                                |
      | ---------------- | ------------------------------------------------ | --------------------------------------------------- |
      | Accept-Ranges    | 表示服务器是否支持指定范围请求那种类型的分段请求 | Accept-Ranges: bytes                                |
      | Content-Encoding | web服务器支持的返回内容压缩编码类型              | Content-Encoding: gzip                              |
      | Content-Language | 响应体的语言                                     | Content-Language: en,zh                             |
      | Content-Length   | 响应体的长度                                     | Content-Length: 348                                 |
      | Content-Location | 请求资源可替代的配用的另一个地址                 | Content-Location: /index.html                       |
      | Content-MD5      | 返回资源的MD5的校验值                            | Content-MD5: Q2hlY2sgSW50ZWdyaXR5IQ==               |
      | Content-Range    | 在整个返回体中本部分的字节位置                   | Content-Range: bytes 21010-47021/47022              |
      | Content-Type     | 返回内容的MIME类型                               | Content-Type: text/html; charset=utf-8              |
      | Date             | 原始服务器消息发出的时间                         | Date: Tue, 15 Nov 2010 08:12:31 GMT                 |
      | Last-Modified    | 请求资源的最后修改时间                           | Last-Modified: Tue, 15 Nov 2010 12:45:26 GMT        |
      | ETag             | 请求变量的实体标签的当前值                       | ETag: “737060cd8c284d8af7ad3082f209582d”            |
      | Server           | web服务器软件名称                                | Server: Apache/1.3.27 (Unix) (Red-Hat/Linux)        |
      | Set-Cookie       | 设置Http Cookie                                  | Set-Cookie: UserID=JohnDoe; Max-Age=3600; Version=1 |
      | Warning          | 警告实体可能存在问题                             | Warning: 199 Miscellaneous warning                  |
      | WWW-Authenticate | 表明客户端请求实体应该使用的授权方案             | WWW-Authenticate: Basic                             |

   4. 响应主体信息

      1. 是响应行，分三个部分：协议版本、状态码、状态文字

         > 状态码有很多，分1-5分类状态码
         >
         > 这里就列举几种常见的状态码
         >
         > 1开头的状态码：
         >
         > | 状态码 | 状态文字 |     描述     |
         > | :----: | :------: | :----------: |
         > |  100   | Continue | 继续。客户端 |
         >
         > 2开头的状态码：
         >
         > | 状态码 |           状态文字            |                             描述                             |
         > | :----: | :---------------------------: | :----------------------------------------------------------: |
         > |  200   |              OK               |                 请求成功。一般用于GET或POST                  |
         > |  202   |           Accepted            |              已接受。已接受请求，但是未处理完成              |
         > |  203   | Non-Authoritative Information | 非授权信息。请求成功。但返回的meta信息不在原始服务器，而是一个副本 |
         > |  204   |          No Content           | 无内容。服务器成功处理，但未返还内容信息。在未更新的情况下，可确保浏览器继续显示当前文档 |
         > |  206   |        Partial Content        |            部分内容。服务器成功处理了部分GET请求             |
         >
         > 3开头的状态码：
         >
         > | 状态码 |     状态文字      |                             描述                             |
         > | :----: | :---------------: | :----------------------------------------------------------: |
         > |  301   | Moved Permanently | 永久移动。请求的资源已被永久移动到行的url上了，返回信息会包括行的url，浏览器会自动重定向到行的url上。今后的任何新的请求都应使用新的url代替 |
         > |  302   |       Found       | 临时移动。与301类似。但资源只是临时被移动。客户端应继续使用原有url |
         > |  305   |     Use Proxy     |            使用代理。所请求的资源必须通过代理访问            |
         >
         > 4开头的状态码：
         >
         > | 状态码 |     状态文字     |                      描述                      |
         > | :----: | :--------------: | :--------------------------------------------: |
         > |  400   |   Bad Request    |      客户端请求的语法错误，服务器无法理解      |
         > |  401   |   Unauthorized   |             请求要求用户的身份验证             |
         > |  403   |    Forbidden     | 服务器理解请求客户端的请求，但是拒绝执行此请求 |
         > |  404   |    Not Found     |       服务器无法根据客户端的请求找到资源       |
         > |  408   | Request Time-out |    服务器等待客户端发送的请求时间过长，超时    |
         >
         > 5开头的状态码：
         >
         > | 状态码 |          状态文字          |                      描述                      |
         > | :----: | :------------------------: | :--------------------------------------------: |
         > |  500   |   Internal Server Error    |          服务器内部错误，无法完成请求          |
         > |  501   |      Not Implemented       |      服务器不支持请求的功能，无法完成请求      |
         > |  505   | HTTP Version not supported | 服务器不支持请求的HTTP协议的版本，无法完成处理 |

   5. 请求方法

      | 方法    | 描述                                                         |
      | ------- | ------------------------------------------------------------ |
      | GET     | 请求指定页面信息，并返回实体                                 |
      | HEAD    | 类似与GET请求，只不过返回的响应中没有实体信息，用于获取报头  |
      | POST    | 向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。POST请求可能会导致新的资源建立和/或已有资源的修改 |
      | PUT     | 从客户端向服务器发送的数据取代指定的文档的内容               |
      | DELETE  | 请求服务器删除指定的页面                                     |
      | CONNECT | HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器       |
      | OPTIONS | 允许客户端查看服务器的性能                                   |
      | TRACE   | 回显服务器收到的请求，主要用于测试或诊断                     |
      | PATCH   | 时对PUT的补充，用来对已知资源进行局部更新                    |

      