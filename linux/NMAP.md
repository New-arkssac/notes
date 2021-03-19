# 诸神之眼NMAP

nmap指令:

* -A  表示使用侵略性的策略进行探测
* -iL 从文件中进行主机发现
* -sL 仅列出网段上所有主机，不发送任何报文
* -Pn/-P0 无ping扫描
* -PS TCP SYN Ping扫描
* -PA TCP ACK Ping扫描
* -n 禁止反向DNS解析
* -v  表示持续输出探测结果
* -T  表示探测的速度，速度等级是1~5，例如T4   
* -sC 是表示使用nmap脚本，一般为默认脚本
* -sV 是表示探测目标机器上的服务信息
* -sP 是表示对目标主机进行ping扫描
* -sT 是tcp探测
* -sW windows扫描
* -sM maimon扫描
* -sU UDP扫描
* -sF  tcp空测试扫描
* -sX FIN和Xmas扫描
* --sanflags 自定义tcp扫描
* -sI 空闲扫描
* -sO IP协议扫描
* -sn 仅发现主机，不进行端口扫描
* -b FTP退会扫描端口规格和扫描
* -O 时表示目标机器的操作系统信息
* -oX （文件名） 将结果输出为文件
* -p 指定端口，例如-p 80；也可以同时扫描多个端口80,3306;也可以进行范围扫描1-65536
* F 快速扫描模式
* -r 连续扫描端口，不随机
* --top-ports <编号> 扫描\<number>最常用的端口
* --port-ratio 扫描笔\<ratio>更常见的端口服务或版本检测
* --traceroute 路由跟踪
* --dns-servers 指定dns服务器扫描
* --exclude 不扫描包含指定的主机
* -PB 是进行CMP请求



nmap状态:

* open 端口打开
* closed 端口关闭
* filtered 端口被防火墙IDS/IPS屏蔽，无法确认状态
* unfiltered 端口没有被屏蔽，但是否开放需要进一步确定
* open | filtered 端口开放的或者被屏蔽
* closed | filtered 端口是关闭的或者被屏蔽



nmap脚本分类:

```text
- auth: 负责处理鉴权证书绕开鉴权的脚本  
- broadcast: 在局域网内探查更多服务开启状况如dhcp/dns/sqlserver等服务  
- brute: 提供暴力破解方式针对常见的应用如http/snmp等  
- default: 使用-sC或-A选项扫描时候默认的脚本提供基本脚本扫描能力  
- discovery: 对网络进行更多的信息如SMB枚举、SNMP查询等  
- dos: 用于进行拒绝服务攻击  
- exploit: 利用已知的漏洞入侵系统  
- external: 利用第三方的数据库或资源例如进行whois解析  
- fuzzer: 模糊测试的脚本发送异常的包到目标机探测出潜在漏洞 
- intrusive: 入侵性的脚本此类脚本可能引发对方的IDS/IPS的记录或屏蔽- malware: 探测目标机是否感染了病毒、开启了后门等信息  
- safe: 此类与intrusive相反属于安全性脚本  
- version: 负责增强服务与版本扫描Version Detection功能的脚本  
- vuln: 负责检查目标机是否有常见的漏洞Vulnerability如是否有MS08_067
```