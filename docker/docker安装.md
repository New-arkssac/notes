# docker安装

### 

### centos7安装docker

**确认环境**

```bash
# 根据系统内核选择docker版本
[root@localhost ~]# uname -r
3.10.0-1160.el7.x86_64
```

```bash
# 系统版本查看
[root@localhost ~]# cat /etc/os-release
NAME="CentOS Linux"
VERSION="7 (Core)"
ID="centos"
ID_LIKE="rhel fedora"
VERSION_ID="7"
PRETTY_NAME="CentOS Linux 7 (Core)"
ANSI_COLOR="0;31"
CPE_NAME="cpe:/o:centos:centos:7"
HOME_URL="https://www.centos.org/"
BUG_REPORT_URL="https://bugs.centos.org/"

CENTOS_MANTISBT_PROJECT="CentOS-7"
CENTOS_MANTISBT_PROJECT_VERSION="7"
REDHAT_SUPPORT_PRODUCT="centos"
REDHAT_SUPPORT_PRODUCT_VERSION="7"
```

**安装docker**

```bash
# 卸载原来的docker
yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```

```bash
# docker的安装环境
yum install -y yum-utils # 下载yum插件
yum-config-manager \
    --add-repo \
#    https://download.docker.com/linux/centos/docker-ce.repo # 添加docker源（国外源）
	https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo # 添加docker源(国内阿里源)
	# 两个源二选一
yum update # 更新yum源
```

```bash
# 安装docker
 yum install docker-ce docker-ce-cli containerd.io
```

```bash
# 启动docker
 systemctl start docker

# 测试hello word
[root@localhost ~]# docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
0e03bdcc26d7: Pull complete
Digest: sha256:31b9c7d48790f0d8c50ab433d9c3b7e17666d6993084c002c2ff1ca09b96391d
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
 # 成功
```



### Depian系安装docker

**安装docker**

```bash
sudo apt-get update # 更新源
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common # 安装依赖
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add - # 添加GPG验证密钥
# 添加源
# x86_x64/amd64架构cpu添加的源
 sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
# armhf架构cpu添加的源
 sudo add-apt-repository \
   "deb [arch=armhf] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
# arm64架构cpu添加的源
 sudo add-apt-repository \
   "deb [arch=arm64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
# 更新源
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io #安装docker
systemctl start docker # 启动docker
# 运行hello-world
sudo docker run hello-world
```





















