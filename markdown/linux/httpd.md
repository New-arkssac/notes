| 服务参数          | 描述                                                         | 语法                                                         |
| ----------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ServerRoot        | 服务目录，存放配置文件                                       | ServerRoot   "/usr/local/apache"                             |
| ServerAdmin       | 管理员邮箱                                                   | ServerAdmin email_address                                    |
| User              | 运行服务的用户                                               | User    user_name                                            |
| Group             | 运行服务的用户组                                             | Group   group_name                                           |
| ServerName        | 网站服务器的域名                                             | ServerName    主机名:port                                    |
| DocumentRoot      | 网站数据目录，站点路径，默认：/var/www/html                  | DowumentRoot                                                  /path/to/someFIle |
| Listen            | 监听的端口号                                                 | Listen       80                                              |
| DirectoryIndex    | 默认的索引页面文件                                           | DirectoryIndex         index.html                            |
| ErrorLog          | 错误日志文件                                                 | ErrorLog             "/path/to/error_log"                    |
| CustomLog         | 访问日志文件                                                 | CustomLog            "/path/to/error_log"                    |
| Aliase            | 设置路径别名，意味着访问alias资源时，其页面文件来自于/path/to/someFile | Aliase           /alias/        "/path/to/someFile"          |
| Include           | 需要加载(包含)的其他文件                                     | Include    conf.modules.d    *.conf                          |
| Directory         | 为指定目录设置不同的权限                                     | *1                                                           |
| LoadModule        | Apache加载动态文件，如果要和php结合，就需要加载php的.so文件  | LoadModule       mpm_prefork_module     modules/mod_mpm_prefor.so |
| PidFile           | 定义其pid文件所在的位置                                      | Pidfile       "/path/ro/apache/pid"                          |
| AddDefaultCharset | 设置默认字符集                                               | AddDefaultCHarset      UTF8                                  |
| ScriptAlias       | 设置脚本路径别名                                             | ScriptAlias         /URL/        "/path/to/somewhere"        |

*1:Directory语法:

​			\<Directory  "/path/to/someFile">

​					Options:

​							Indexes						#缺少指定的默认页面时，允许将目录中的所有文件以列表的形成展开给用户

​							FollowSymLinks		 #是否将符号连接所指向的文件打开

​							None							#所有选项都不启用

​							All								 #所有选项都启用

​							ExecCGI					   #允许使用mod_cgi模块执行CGI脚本

​							Includes					  #允许使用mod_include模块实现SSL(服务端包含)

​							MultiViews				 #允许使用mod_negotiation(协商)，实现内容协商

​							SymLiknsifOwnerMatch		#在链接文件属主数组与原始文件的属主属组相同时，允许跟随符号链接所指向的原始文件

​					Require all granted				#允许所有访问

​					Require all denied				 #拒绝所有

​					Require env  env-var [env-var]	#允许，匹配环境变量中任意一个

​					Require expr expression   			#允许，表达式为true

​					Require group  group-name [group-name] 	#允许，特定用户组

​					Require user 	userid  [userid]				#允许，特定用户

​					Require valid-user   #								#允许，有效用户

​					Require   ip  172.20    192.168.2              #允许 ， 特定IP和网段

​			\</Directory>

注：MultiViews:协商可以这样理解，假如网页有中文的，英文的，阿拉伯文的，而用户需要中文的，则客户端和服务端进行协商，最后把中文的网页发送给用户，这就是协商；