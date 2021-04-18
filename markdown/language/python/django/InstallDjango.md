# 安装Django

安装Django遇到的坑

如果python是3.6的话，内置的sqlite版本会太低而启动无法运行runserver

`django.core.exceptions.ImproperlyConfigured: SQLite 3.9.0 or later is required (found 3.7.17).`

这个时候要么切换django<=2.1的版本

要么更新sqlite

我这个人喜欢新的

所以呢

就更新sqlite

```bash
wget https://www.sqlite.org/2019/sqlite-autoconf-3280000.tar.gz
tar -zxvf sqlite-autoconf-3280000.tar.gz
cd sqlite-autoconf-3280000
./configure --prefix=/usr/local
# 到这一步可能会编译失败，是我没有安装gcc的缘故安装gcc就好了
yum install gcc -y
make && make install
mv /usr/bin/sqlite3  /usr/bin/sqlite3_old # 备份原来的sqlite
ln -s /usr/local/bin/sqlite3  /usr/bin/sqlite3 # 软连接编译好的sqlite
vim ~/.bashrc
export LD_LIBRARY_PATH="/usr/local/lib" # 添加环境变量
source ~/.bashrc # 重新加载.bashrc
```

然后要用到数据库

这个时候就安装mariadb

`yum install mariadb-client mariadb-server`

安装后启动

`systemctl start mariadb`

再初始化数据库

`mysql_secure_installation`

一路回车就好

然后再测试创建app

`./manage.py startapp test`

然后报错

`ModuleNotFoundError: No module named 'MySQLdb'`

这是缺少数据库依赖

安装mysql-devel

`yum install mysql-devel`

之后再创建又报错说没安装mysqlclient

去安装mysqlclient和pymysql

```bash
pip install mysqlclient
pip install pymysql
```

然后在安装pymysql的时候报错

`  error: command 'gcc' failed with exit status 1`

去百度说是缺少python依赖

安装

`yum install python3-devel`

之后创建app成功

启动自带服务

`./manage.py runserver`

报错语法错误

因为centos7默认的是python2

django3.2又是python3写的

所以会报语法错误

这个时候用python3去启动就好了

但是呢，我这个人比较懒，每次都要打个python3

我觉得很麻烦，所以我打算把python3变成默认python

```bash
rm -f /usr/bin/python
ln -s /usr/bin/python3 /usr/bin/python # 这样就行了
```

这样改之后，蛋疼的事就来了

你会发现yum用不了了

也是报语法错误的报错

这是因为yum使用python2写的，然后我们因为把python3的软连接给换成了python

所以才报错的

不要慌~

这个时候要去更改urlgrabber-ext-down和yum的启动脚本文件的启动方式就好了

`vim /usr/libexec/urlgrabber-ext-down`

编辑把`#!/usr/bin/python`改为`#!/usr/bin/python2`就好了

yum的启动脚本同理

这样之后就可以愉快的使用`./manage.py runserver`了

:)









