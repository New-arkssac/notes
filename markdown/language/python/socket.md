# socket库编程

这个模块提供了访问BSD套接字的接口，在所有的unix系统、winows、macos和其他平台可用

_____

### 1.1 常数

​	AF\_\*和SOCK\_\*常量现在都在AddressFamily和SocketKind这两个IntEnum集合内

**socket.AF_UNIX**

**socket.AF_INET**

**socket.AF_INET6**

> 这些常量表示地址(和协议)簇，用于socket()的 第一个参数。如果AD_UNIX常量未定义，即表示不支持该协议。不同的系统可能会有更多的常量可用

**socket.SOCK_STREAM**

**socket.SOCK_DGRAM**

**socket.SOCK_RAW**

**socket.SOCK_SEQPACKET**

> 这些常量表示套接字类型，用于socket()的第二个参数。不同的系统可能会有更多其他常量可以使用(一般只有SOCK_STREAM和SOCK_DGRAM可用)

**socket.SOCK_CLOEXEC**

**socket.SOCK_NONBLOCK**

> 这两个常量(如果已定义)可以与上述的套接字类型结合使用，允许你设置这些原子性相关的flags(从而避免可能的竞争条件和单独调用的需要)

**so_\***

**socket.SOMAXCONN**

**MSG_\***

**SOL_\***

**SCM_\***

**IPPROTO_\***

**IPPORT_\***

**INADDR_\***

**IP_\***

**IPV6_\***

**AI_\***

**NI_\***

**TCP_\***

​	此列表内的许多常量，记载在Unix文档中的套接字和/或IP协议部分，同时也定义在本socket模块中。他们通常用于套接字对象的setsockopt()和getsockopt()方法的参数中。在大多数情况下，尽在那些在Unix头文件中有定义的符号会在本模块中定义，部分符号提供了默认值

**socket.AD_CAN**

**socket.PF_CAN**

**SOL_CAN_\***

**CAN_\***

​	CAN协议簇内的CAN_BCM是广播管理(Bbroadcast Manager -- BCM) 协议，广播管理器常量在linux文档中所有记载，在本socket模块中也定义

- `socket.``CAN_BCM`

- `CAN_BCM_*`

  CAN 协议簇内的 CAN_BCM 是广播管理器（Bbroadcast Manager -- BCM）协议，广播管理器常量在 Linux 文档中有所记载，在本 socket 模块中也有定义。[可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： Linux >= 2.6.25。注解 `CAN_BCM_CAN_FD_FRAME` 旗标仅在 Linux >= 4.8 时可用。*3.4 新版功能.*

- `socket.``CAN_RAW_FD_FRAMES`

  在 CAN_RAW 套接字中启用 CAN FD 支持，默认是禁用的。它使应用程序可以发送 CAN 和 CAN FD 帧。但是，从套接字读取时，也必须同时接受 CAN 和 CAN FD 帧。此常量在 Linux 文档中有所记载。[可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： Linux >= 3.6。*3.5 新版功能.*

- `socket.``CAN_RAW_JOIN_FILTERS`

  加入已应用的 CAN 过滤器，这样只有与所有 CAN 过滤器匹配的 CAN 帧才能传递到用户空间。此常量在 Linux 文档中有所记载。[可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： Linux >= 4.1。*3.9 新版功能.*

- `socket.``CAN_ISOTP`

  CAN 协议簇中的 CAN_ISOTP 就是 ISO-TP (ISO 15765-2) 协议。ISO-TP 常量在 Linux 文档中有所记载。[可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： Linux >= 2.6.25。*3.7 新版功能.*

- `socket.``CAN_J1939`

  CAN 协议族中的 CAN_J1939 即 SAE J1939 协议。 J1939 常量记录在 Linux 文档中。[可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： Linux >= 5.4。*3.9 新版功能.*

- `socket.``AF_PACKET`

- `socket.``PF_PACKET`

- `PACKET_*`

  此列表内的许多常量，记载在 Linux 文档中，同时也定义在本 socket 模块中。[可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： Linux >= 2.2。

- `socket.``AF_RDS`

- `socket.``PF_RDS`

- `socket.``SOL_RDS`

- `RDS_*`

  此列表内的许多常量，记载在 Linux 文档中，同时也定义在本 socket 模块中。

- `socket.``SIO_RCVALL`

- `socket.``SIO_KEEPALIVE_VALS`

- `socket.``SIO_LOOPBACK_FAST_PATH`

- `RCVALL_*`

  Windows 的 WSAIoctl() 的常量。这些常量用于套接字对象的 [`ioctl()`](https://docs.python.org/zh-cn/3/library/socket.html?highlight=socket#socket.socket.ioctl) 方法的参数。*在 3.6 版更改:* 添加了 `SIO_LOOPBACK_FAST_PATH`。

- `TIPC_*`

  TIPC 相关常量，与 C socket API 导出的常量一致。更多信息请参阅 TIPC 文档。

- `socket.``AF_ALG`

- `socket.``SOL_ALG`

- `ALG_*`

  用于 Linux 内核加密算法的常量。[可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： Linux >= 2.6.38。*3.6 新版功能.*

- `socket.``AF_VSOCK`

- `socket.``IOCTL_VM_SOCKETS_GET_LOCAL_CID`

- `VMADDR*`

- `SO_VM*`

  用于 Linux 宿主机/虚拟机通讯的常量。[可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： Linux >= 4.8。*3.7 新版功能.*

- `socket.``AF_LINK`

  [可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： BSD、OSX。*3.4 新版功能.*

- `socket.``has_ipv6`

  本常量为一个布尔值，该值指示当前平台是否支持 IPv6。

- `socket.``BDADDR_ANY`

- `socket.``BDADDR_LOCAL`

  这些是字符串常量，包含蓝牙地址，这些地址具有特殊含义。例如，当用 `BTPROTO_RFCOMM` 指定绑定套接字时， [`BDADDR_ANY`](https://docs.python.org/zh-cn/3/library/socket.html?highlight=socket#socket.BDADDR_ANY) 表示“任何地址”。

- `socket.``HCI_FILTER`

- `socket.``HCI_TIME_STAMP`

- `socket.``HCI_DATA_DIR`

  与 `BTPROTO_HCI` 一起使用。 [`HCI_FILTER`](https://docs.python.org/zh-cn/3/library/socket.html?highlight=socket#socket.HCI_FILTER) 在 NetBSD 或 DragonFlyBSD 上不可用。 [`HCI_TIME_STAMP`](https://docs.python.org/zh-cn/3/library/socket.html?highlight=socket#socket.HCI_TIME_STAMP) 和 [`HCI_DATA_DIR`](https://docs.python.org/zh-cn/3/library/socket.html?highlight=socket#socket.HCI_DATA_DIR) 在 FreeBSD、NetBSD 或 DragonFlyBSD 上不可用。

- `socket.``AF_QIPCRTR`

  高通 IPC 路由协议的常数，用于与提供远程处理器的服务进行通信。[可用性](https://docs.python.org/zh-cn/3/library/intro.html#availability)： Linux >= 4.7。

