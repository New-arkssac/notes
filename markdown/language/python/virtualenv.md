# virtualenv

virtualenv是python的虚拟化环境工具包，可以建立一个单独的python环境副本，

此副本和其他的python环境相互隔离，互不干扰。举例子说：在virtualenv1的环境中安装的所有的第三方包都是和virtualenv2的环境不相干的。这方便于多人开发或开发多个项目

# 安装

`pip install virtualenv`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618642958958.png)

# 查看是否安装成功

`virtualenv --version`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618643494680.png)

# 创建新的虚拟环境

`virtualenv venv`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618643845927.png)

# 进入虚拟环境

`source bin/activate`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618643979757.png)

可以进到虚拟环境目录下的bin目录查看有哪些文件

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618644068704.png)

可以看到除了activate进入虚拟环境的脚本以外，就是python的基本环境了

# 退出虚拟环境

`deactivate`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618644271081.png)

# 安装virtual的扩展包virtualenvwrapper

`pip install virtualenvwrapper`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618644341328.png)

这个时候输入扩展的指令会发现并没有这个指令

这是因为它并没有添加到环境变量里，这个时候就需要去更改.bashrc文件了

```bash
vim ~/.bashrc
export WORK_HOME=$HOME/.virtualenvs
source /usr/local/bin/virtualenvwrapper.sh
source ~/.bashrc
```

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618644912655.png)

# 使用扩展命令创建虚拟环境

`mkvirtualenv venv2`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618644981803.png)

`mkvirtualenv [-i]`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618647890617.png)

`mkvirtualenv [-r]`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618648147560.png)

| 参数 | 语法           | 解释                                       |
| ---- | -------------- | ------------------------------------------ |
| -i   | [需要安装的包] | 指定创建虚拟环境后安装的包                 |
| -r   | [指定的文件]   | 指定创建虚拟环境后需要读取安装包的列表文件 |

# 创建指定python的版本的虚拟环境

`mkvirtualenv --python=python3.6 venvname`

或者

`mkvirtualenv -p python3.6 venvname`

# 查看已有的虚拟环境

`workon`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618646340395.png)

或者

`lsvirtualenv [-b] `

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618647071507.png)

`lsvirtualenv [-l]`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618647125740.png)

`lsvirtualenv [-h]`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618647141410.png)

| 参数 | 解释                       |
| ---- | -------------------------- |
| -d   | 简短模式，禁用详细输出。   |
| -l   | 长模式，启用详细输出。默认 |
| -h   | 打印lsvirtualenv。         |

# 进入已有的虚拟环境

`workon venv2`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618646421443.png)

# 显示单个虚拟环境的详细信息

`showvirtualenv [env]`

# 删除虚拟环境

`rmvirtualenv venv2`

![](https://bulabula-1305079562.cos.ap-guangzhou.myqcloud.com/img/1618646524880.png)

