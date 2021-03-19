
* [目录结构](#目录结构)

* [linux文件权限](#linux文件权限)

   * [linux文件的属性](#linux文件的属性)
   
* [linux的命令](#linux的命令)

   * [基础命令](#基础命令)
   
   * [进阶命令](#进阶命令)
   
   * [高级命令](#高级命令)
	
# 目录结构：

/bin:      全称 binary, 含义是二进制。该目录中储存的都是一些二进制文件，文件都是可以被执行的。

/boot:    这个目录主要是放置开机会用到的文件，比如开机用的系统引导文件

/dev:     该目录中主要存储的是外接设备，例如盘、其他的光盘等。在其中的外接设备是不能直接被使用的，需要挂载类（类似windows下的分配盘符）。

/etc:       该目录主要存储一些配置文件。

/lib:       系统的很系统的函式库非常的多,而/lib 放置的则是在开机时会用到的函式库, 以及在/bin 或/sbin 底下的指令
会呼叫的函式库而已。 什么是函式库呢?妳可以将他想成是『外挂』
 ,某些指令必须要有这些『外挂』
才能够顺利完成程序的执行之意

/media:  media 是『媒体』的英文,顾名思义,这个/media 底下放置的就是可移除的装置啦! 包括软盘、光盘、
DVD 等等装置都暂时挂载于此。

/opt:    这个是给第三方协力软件放置的目录。

/run:    早期的 FHS 规定系统开机后所产生的各项信息应该要放置到 /var/run 目录下,新版的 FHS 则规范到
/run 底下。 由于 /run 可以使用内存来仿真,因此效能上会好很多!


/home:	表示“家”，表示除了root用户以外其他用户的家目录，类似于windows下的user/

用户目录。

/proc: 		process,表示进程，该目录中存储的是linux运行时候的进程。

/root: 		该目录是root用户自己的家目录

/sbin: 		全程super binary, 该目录也是存储一些可以被执行的二进制文件，但是必须得有super binary权限的用户才能执行。

/sys:  这个目录其实跟/proc 非常类似,也是一个虚拟的文件系统,主要也是记录核心与系统硬件信息较相
关的信息。 包括目前已加载的核心模块与核心侦测到的硬件装置信息等等。这个目录同样不占硬盘


/tmp: 		全称temporary 表示临时的，当系统运行的时候产生的临时文件会在这个目录存放着。

/usr: 			存放的是用户自己安装的软件。类似于windows下的progtam files.

/var:			存放的程序/系统的日志文件的目录。

/mnt:			当外接设备需要挂在的时候，就需要挂在到mnt目录下的。


# 绝对路径和相对路径
	 . : 代表着是当前目录
	.. : 代表着上一层目录

# linux文件权限

linux最强大的地方就在于它是多用户管理的
每个用户管理不同的文件
每个人管理的权限都不同
然后也可以多个用户管理文件
分别拥有不同的权限
然后有一个万能的用户
>管理员用户root
这个用户可以拥有系统的所有权限
想干嘛干嘛

## linux文件的属性 

在文件夹下使用 ls<空格>-al 指令
就可以查看文件夹的属性
<img src="../../image/20201112_1.png">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAroAAAAwCAIAAABxK07ZAAAACXBIWXMAAAvXAAAL1wElddLwAAAgAElEQVR4nO29d3wTV7o+/o4lS3K3Jfci916wAYMh9A4h1ARICElIIWU3yabt7r13N7m7uXu/u5u2NxtS2AQIkACGEHoxxrh34y4XWbIlWy6yJduyJVt1fn8MTMYzI1k2tsH70/Phw2c8OnPmPc+ced/nvOfMDKJWq2Gy+PHc9az80g2rFj++eQ1tgVGt7vX//BuKogDwp/deCfDzziup/P70JQAI8PP+03uvTOh0as3Im3/4CAC++vt/2jOZkzbbeozbwJlHVn5Zg7AV2xa1tauG1PwAXx7XHQDYLNaLe7dZX1X6xZsZ2UWeXPfU5HgnR4dWqayqvpnDZqk1I4tT5zz/5FasmDW0ZxeWnzh7NTU5/uVnduI7M3NLTp2/EeDr9Ye3X7JnMvOK7xw7cwUAEmMj/H29fL089QZDjaC5tqElPCTwt79+jmFnZzAYP/jo655eBc/DPS4q1NuL6+bi3NOnzC4o14yMvrb/iZSEGADoHxz6418Pjmp185PjwoODlAODNQKhon+AwWBotbq//fENnoc7ZkNGdnH6xQwASIqLDAny1+n1QrFU1Nbh7cn9829fZTIZk+DK2clRLOmYNFc5RRXHz1yxzFV+SeX36ZeJXBmMxur6Joyr372+H+Pq/b9/hXPl483DuLqdX6YZGf3V87uS46Ot5wpBkIzs4tMXbuBc6Q2GZpFkolwZDMaDR07XNrQAQFx0GMPOzmgy4b/6eXs+uX0DALS0tv/ti6POTg7zkmJ5Hu6dPb1lVfWoCd2zfcOKxfOwwp09fQcPn5b3KXke7hGhQYH+3qohdWll3aBqODYq9M0Xn2QwGACgGlK/89+fAsDnf/mtA4eNn+vYmct5xZUJMeFvvvQUiqIIggAA5ovMQa0ZwWgHAM3IaLNIYs9kxseEY3uWLkxOjI3Etk9fyLiVV+rv65U6J06r0xeWV6vVI88/tW3+nFiMTIPB+Jd/fCfrlu/dsXH54nnYeREEwTdwY7Lyy05fyFj5SOqebeuIZSaEzp6+L4+k9yr6Ma4C/LxUQ+qyqnqMqzde2GNnZ4c1ELsHaRu4ZMEcvIHjQjMyaoErvKr/+9dJQbM4NjI0IjRIp9cLmlvbZd1BAb5vHXjKydGBVOf124U/X72Nbf/+9edC+QGWbXj/71/19Co/eOeAv6/XhKyaQvzp4286e/pC+f4uzk59iv6evn6j0ejJ89i/+7GI0CBSYaFY+vFXxwGAyWR8/MFbxO4KAD9duZWRXQwAj65ZsmX9cgD44vDdW2n/ni1p8xJHtbp3//szvcHwtz+84e7mAoSOVFBadezMlbDggN+/vh8APv/2ZF2jaOfm1etXLMLr/+s/j4glsu2bVm5YuRhBkGaR5Mipi4r+QTbLnh/gF+jvoxkZrWtsUWtGFs1P2r9nCwBodfqzlzJziioAwJPnMQVBF7OYFhw2y9/XS9Yld+CwsSsaHR6M/RQWPE5XeHhgoYEzj/bO7sraRuIeqaxbKusGAEfK7WcZOx9dpdPr84ruXMsqAAAfL97urWsjQvl//uTQRK2ipWjNsoWCZnGNQPjjuevP7tq8NG1uZFjw1cz8RlFbjUCIlWGz7NcsW7hl3TKGnR0AMJmMP//2lcLympzCiuKKWr3BgBULDvTbtnFlYmwE9qeHm8sbLz75ffrl8ipBeZWAw2bFRoW9/sKec1du3RlLzroVaaF8/zOXbtY2tGAndXJ0WLNs4baNK63XClPLFS1IXC1ZmBIRyjfHlR2CoCjKYNh9+LtXC8qqqVxt37QqISYcCzwebi5vvvTU0dOXLHOFouja5QtD+f7pFzPuh6shtQZzcAAgaBKTfh0d1WEbEaFB+/dsuXwzL7uwAgAQBAnw9X5m1+aw4AAstKMo6u/j+f7bL124kVNYVl1yp7bkDmAmbVm/fN3yNEwrWMDWDSvKKuvrGkW1DS0J9wKGZej0hqq6JuIeveGXPbjvAoDdW9e5uThn5BRfuJEDAJ5c9+ee34KfBUXRH85dk3XLQ/n+S9NSsJ1YoxAEMZlMVfXNDDsEwM7ODpF2dAOAs5MDfqw1ppLg7+P5x7devJiRW1ReU3KnFtvp5Ojw2Lpl65anYVoBAPQGo5UNHBdWcvXsrs3pl27WNbRggxwOm7Vm6YLtm1bR9qjU5PhbeWWqoeFQfkCQv6/1xkzUqilHq7QTADzcXGIjQ4ID/davWMRms6jFIkKDXF2cVUPDMREhJK0AAL5ePGwj6p6dkaF87G7y4nkAQI1AqDcYggP9MK0AhN6SFBeJIEirtFPRP9jZ3VvXKPLkuq9akkqsf9eWtX/959GrtwrS5iZ6uLtGhQd/8O7LP1/NKqmsF7ZKha1SAHBzcX5y+/pli+5KdjbLfu/OjSmJMeeu3JLKupH7yS7Y8G+AkVGtvE/JdXdzcXacsZNqNCPdvUpXFycPd1fGPV9GAoqi8j7lqFbnyXWnDkSwAr2Kfp1eH+DrPa6k0xsMXd29jo4Onlz3SZv9YLniergRucLDKvZnT69iVKvz4nk4OnDwyEQs3Kvo1+p0gX4+QBiU4CWJtRmMxq7uXgcHjhfPY3LRy3qoNSN9ygEfLx6HzSK1iGT8sFrj5urMdXebqHwnVosfO1Xt6pYr2GyWxz33jdUsFEs/+fqEi7PTe6/t8/HiUW342xdHRW0d+CEcNuvd154J8ve5f3tQFO1TDmBcebi5PiRDHRRF5X39AODt6WHZJK1O39OrCPT3sXs4LJ9doN74OEj9nwijydSn6FdrRnhcdzcXZ3OVDw1rbHLBBhtmGYgxlRr/zGWzia6EKhFIZaZbJZAwrvGTrpbkH2esXfmlVXx/H36gH4xtHbbRLJbUNrQw7Bj29gw3F+f46HAPd1cS89N9FWjrt9AfiHKHtpMQu+K4DaHOy5B65hS29P9XIA0SqP3/fhSkTS7YYMPDC6r7xjZofbE10sGc77ZQ5zT5btqgYs0Kg0mchfaMMwZSLCTtp0ZNC2F4qkyyRitYWQlVRpBMtbJa2l5nkw4WQO1URG1H3EPdnhzo88A22GDDwwDLvhJ3DRhQFB035U7VFthOYklz4WpqgVWLWY7voTXv/s+CNfCBZOaJ56WGUmJQxLaJDODkkC6Q9SA2mXTFJ1GbZZDsp54Lv+IWDidRZNMKFkDsFbSDCpjq/m+TCzbYMDuABxVzAy9cNOB/AiHqkJy1BUdMLDzpQGUliP6OGG+mNcEwVTVbAyqHJPVAcu5E/US83LTlJ2qG5TLmChANpmoOkkIF86HLmitr4QI9ELX38IPYK4hXmbhBunCThk0u2GDDrAEp0uBACQBKTpt2FELyINRANTN5YJKzIyqVKQ8PeCiascCDh1JalUYNjeYSDEQhSKrTcltIoYJ0FOlYUkkw399IO2lFKskA6gWl9kC8KptiGBckHUa9VWm71n3CJhdssGF2gBRpiKM6ajygzYETC5NqAIpDoYa6aQUpHE5TVoM0Xp9ukKiGsU6cKtfAzGCd9nKPG1ZJlSCUKQ/iJSbWSVWKpItCFRb4TpJVxEZR5RqRFqpUIjVqxq7arAApeQBjew41kTMld/FMvOzIBhtsmCagdMvliD+R9gDBrdB6dhjrZWbYRxNtm6o6aWMnEBiY7jYiYzM94wZ7Iqhhm3Q4qQBCmfswVxLolrgCQTEAJd6gY6d1SPVTzaNKE6oaQMauuaF20XEpeoBYWl76oE2YJPJTF07iKFt2wQYbZg0sjL2ocYKUIsZjAGn8QXTxxPEfNcpON8zlOaYQRIqoI7DpA0nSAYXYSQwEzaVJzF044jUlXXFzxpASBpaTJUDpWsSjqPqAVIxKAjp2IgOhTHlMiC4b7h82uWCDDbMJFuINMRhQx3a04YrkqYlHzczIGz8X0TxqAJtaPFgxRAQp/tGO6UlskGI5aZt0HUmXmySVaK0iBWZSngClTHLh28SLSBQWeA0k2kn/0150ohnm9NZDnoH4d4JNLthgw+wA7oLNCQWiT6cdrZJGdUAIBrSBasZG3tRh65SfmhhsSCQ8KJAEGdEYEhW014Vanhjpib2FdtROOik1T0Alh6RIqAcSMwfmhCntSc1pINqz00ocsGH6YVu7YIMNswOkgSP1Jwy0CQOqsyZGHXNjUKqGmD6YCydTdXZS+CSJpOnTRodPXmgWS8cttmhe4tYNK0iGgfmLbq4b4IqB+D/QXWWgcE79k1ZtUI0nnRcoeQhS5VS9S62KtnILDbfMjA1TAmvlglarq6hpsLND0uYlTatBNsxGdMsVYkkHj+s+fR9x+bfBfXJFcpq0AY80/iPuBMIQ0NyYnnb8Oq0g2o8PRkmj6qk6C2mb2NLpkEfDao2yf9DNxdnent7Zjoxq1ZoRzYgW30MNeOYG9FRhR+WQtkIY23OopyZpBXOBHywyaQ6Wm0NUKuauF7X/kyp/IGCg6DalYsDe/par24OyYVphrVwYHBo+fPICh82yyYWHB0aTydz3mWYYjS2t2AesbXJhXDSJ2rAPWN8/V9R4YEE0kEQAcSxobkA2YwM1qv20zaENQkaTSdYlB4Agfx9iAbVmRNE/SNxPm2ixkOKeQrz63BPmvsF7K6/09IUMbJtqDG0whrErDGiT9jC2AxD/J9VDHdDTHkILc4kHUpoE+x/3VxZSFLStMNdYy3po5vG+uGWroBYAfr901XX3yX/K7qGFbTJi9kHa0XUtq7C+WTwyMsrjusdGhmzbuNLCl8Rs+PeAOedIjanUZL656EubRTCXbJgchGIpFg4P7Nvh7cm1poEkS2obWm7llYjaOtgsVnhI4I5HV/t4/VKPWj3y4af/AoDP//Jb/KPAo1rdR18ek3XJN6xczA/wJZ4CCCGHFOHwbdWQuqyqvqyqnsNm/+bAU7TWGk0mUWt7XklVt7xv0+pHUhJjLDTNGgJJwZVqIb6HmHchRWWjySQSS3GrkhOiSfUbTabMnJLC8mp5r9Lenunn47lu+aK5STHWZFaoOgZBkEHVcFlVfXm1gMgVsSHSjq7rt4sEwlbMX8VEBG/dsILor2gnF6j2YC0l0Z6cEE3sNmcu3RSK283Zv2zR3CULki008D7BMhqxDY7JOH1neYCwyYVZhuzC8tPnMwxGY5C/j09UWHtnd15x5Z2axg/efZnr7vqgrJrWkdm/GSYdekkH0oYW4iwDaT8xrpCyvqSS+Onuf0ZgUDX89bGzg6phANDrDdY0kCR3bheU/XjuOofNiokIHdVqaxqETSLJr5/fHREaZKGeQ8fPybrkSXGROx5dZflEpKy7VNb9xXenB1RDWElzKvzIqYtlVfUGw92ooBqegg/1mctzEEf/1ItOLE+1ilRV/4Dqm+M/iSUyBw47MS5Sp9MLxdJvjv+0bkXa45vXwHg3MqmzSTq6Dh5Ot8xVTlFF+oWbBqMx0M/bJzK0o6snv6Sqsrbpj2+/hPsrcyelUnH09CULDUQQZFCl7ulVkOsB0Gp1ADDdH8X+MCKqyc1dxWSe5/Km9UQPCja5MJswqtXlFt3herj96vld/j5eAICiaPrFmzdzik/9fP21/bsetIE2TDtopxtIUZ+UsibtpKoEoFv0jiuPScsFo9H49bGzqiE1m83C/DUV1CE1UdP0KQdO/XzD3dX5vV8968XzAABBc+s/vzt59PSlD3/3qrkwc+bSzdoGYYCf94Gnd9CWsZDzd+CwsTzB0LC6vFpgrmnBgX4cNhsAahuEfcqBcak4cuoim82i/Wl4rNSg1Qq026RiAMAP8KW1ChccTSJJq7Rz05olW9cvx6rqUw785R/f3cwpWZCSQEzDWINxucL91avPPY77qzOXMjNzS06fv/Hqc09QDzGaTIOqYUxJUK+duQbivfTFvduI5bEaisprjpy6mJwQvTh1zoQaOFFo7OyO+kyMw9kFs3JhVKvLzC0WS2QoikaG8ufNiaWWqahpaGltX7NsAc/DXdLRlV9S2d7ZY4fYhYcEbtu08ucrWUaTacv65XiGkAhF/0BmbqmPJ3f54nlXMvPVmpHU5Hji9F51fXNjS1uQvw9+jbVa3fnr2T5e3BWL52u1usLy6rpG0aBqmOvhtmbZAoPBWNvQEsoPWJAST9uinKKKbrli9ZJU1bC6rErg6MDZvHYp3iO1Ov2lGzlGk2njqkdcXZymqoG+Xrxli+Za2cBxwWGz3nl1HwA4OTpgexAE2bBy8c2c4iaRxMpKSBC1dVTUNLTLurU6fYCfd2pyXFxUGLEARruvN2/5onlara6ooqa2oQWnPSosGMyMmJUDqsycYhRg7fI0fCQxoBrKLqiQyrqHhtV+3p6BAT5pcxNcx45LUBStqmuqrG3qVfbbM5n8QN/o8JDE2AhS/aNaXVF5TbNIougfcHZyCgnyW79iEa1Trm1oqW8StXf2sOyZIUH+85PjA3y9po8rc10U44oW1nAVFOibNjfBxdkJZwlBEJPJVFnbSOQqJiIU44qYQhjV6oorapta2jCuQvn+65ancThs6jqGukZRXWMLxlUoP2DenLhAP+/JKYb0izeFYumGlYsbhK2Sji7aMiSZQhQoCIJk5pYYTab1KxdjWgEA4qJCUxJiyqrqq+ubiZl2HPmlVTdzSlycHX/9/G5zEZqqt/CfvHgeT+3YgKKoVNZtQS6sWpKKbfQpByzLBZMJBYChYbVmZJS2gN4wTtIFB1HlUBNIALB66QJaq/DCafMSw4IDiFNCnlz3uUkxecWVQrF0onLB25P75Pb1ACDp6KLlisNmvf3K0zDWX61fsSgzt4T2aZHBoeGPDh6T9ykTYyN//fwuqlxYvXQB1ny8gaQrSJ1d6lP0//jzdU+u+3O7Nk+odVbiHWmbr0ZD2nkwLKKN9Uvf+3/NjcP29llePk9JxH5DQ6cioy9xeR8Im2IVvS0evD9HxQwRlqCtGxxY090VPDjAMhpkLm6Z/gHUXIWzyfRauyShr9dZr5O5uI4yfonjX4eFi1h345G/Qf+8VBox2O+qHW13dcvx8TvH87yfxtLLBWlH15ffn+1T9CMI4uDAqW1ouZVP87bLphZJVn5pQkzE7YLyG7eL8JuwT9m/c/NqzEckxkTERYcBwOEfL9Q0CFcsnr9t4woAaGhuvZlTvGbZQgRB/Hw8vzp65k5NwwfvHHB0dACAPkX/oRPnEID33zmAn85gNN7MKQ4PCYwM5R88ki7vU2L729o7k2IjXF2csF8xuSDr7v3o4PcIAv/7n69j4fxqZr5yQLV57VJ3N9cffrom6ejisFlrl6dhlfx0OTMrv2zF4vm4ViA2MLuw4npW4YQa2Chsm2gDrQF+4/0CBAAAnfhyLVmX/PSFDEGzGAA4bBaCIGJJR17xna0bVjy2bhleDKc9IiSISru5ENinHPj4q+MK5cDeHRvx+NfU0vbZoR8MBqMnz4Ntzyyrqi8sr75w7fbOzatXLbnr6Ywm08HD6TWCZg6b5cn16NP0C5rF17MKQ4L833hxDy4srt7Kv3G7SK0ZAQA3F+dWaWeNoLmgtOr3r+/3IEzK9A+ojpy6iLWRzWYhALUNLVdvFWzfuHLDqsX3z9WW9cu3rF9O5Yq2i2JcUa8RztXTOzfhXDWLJJ9+c4LE1fmrWY8/tgbjCkVRg9FomSusx169lX89q5DEVX5J5X+88by7mwtuhrJ/kMrVlcz8HZtWrV+5yHquMJTcqbuVVxrKD9i2cWWNQGihJLHfkmZMquqaAGB+chyxfGpyXFlVfbVASJULzSLJibNXmUzGq8894ck1u9aMGHene4mcwWAAgHde3WcuGBOXOlJBTYSQEgzmpjBwkH6iLh+xQ+wAwDQ9PEzIXxWV12C3TG2DUNLRFRLkT62QVifRzuBg/3/743mtVvfWgb2Ojg7Tca0Xd8rCe3tIO0/zg4lyYZVIyEBN60XNzqOjdij6tmpgtV9AWpsYAEL7eu1Q9J3YeABIUw+/VV8b3dMFAFqmPYogoX29S1pbkuMS/zs8Eq/N36A/XJjnOzjQ7eauYnMWSVqZxl+WSvwUxMfkwp6+3l9XljuPjqjZbDWbs6RVtFwkXBEW+UZ84qQbSyMX9AbDoRPn+hT9i1Pn7Nm6ztHRobO79/v0S9gEJBXpFzNkXfIFKQkbVi329/HSjIz2KfsBIDwkUNLR1dbeiUXTuibRsFojaBZh0bStowsAsNH2vKTYFYvnZxeWHz979eVndqIoevjkRa1W9/yTW6mdW96n/PTrEwDw3J4tSbERDg4cWZfck+uO9QRpRze2/rZZ1Das1gBAS2t7YmyEamhY0T/o48XDuu+BfTs+/PRfP125FR0ezA/0q28S3y4o9/XmPbFl7UQb2CqV0Tawtb1zcg2cKARNYgCICAma6AICDofV1tG1bnnaIwuS/X29EARpamn7/NuTF2/kzE2KJY2/cdqf3f3YnLhInHbsV9Kp5X3KT746rhxQPbNr89KFKfj+H366ZjAYX3p6x8K5CQCAoqigufXKzbzoiFC8zJ2ahhpBMz/A93ev72ez7AFgWK25cbtoZFRLTEIoB1Q8D7dndm2OiQhxcnTQanVHTl8srxKcuXTzwL6dWBmj0fjV92fEEllcdNiebev9fbxQFG0WSY6dueLkyJkEV2uXLVyyMIXI1aWM3Hlz4ibEFclnmePqxNmrBoPxwL6dmPxFUbRB2HY5IzcqPASPE5W1jdZwpegf5Hm4Pbv7sejwYGcnx9FRLcZV+sWMl595HKvcZDLhXD25fQPO1ffplyfKFQDIuuTH0i+5ODu+9twTTCbDhJosFKb2W9zXD6iG7JlMd1cXg8GYXVju5uo8f06cJ88DAJQDg6SjehX9Xx49YzQaI0P5kaF8K00lSQcLN9HktIVObwAAR4cJc0g1Esw8cUD8ycKx5tAgbAWAqDBrGZvEKcacrrkVAMKDA6lH+XrfHUbbM5keE1mJRZ1Kw1DbIBJLZImxEaF8/2nShW/MW8Am1Hzq1nUWXbqIaTR2uHm8tWL+h/W1C6Stqe2S11euDRoZ+V1x/sIOKcTGA8AQg8HvV2RExZwL5Jc5OhkRZEu/8g/F+Vsa6m74+BU5372jPxDU+Q4OXImJ/6/IaABYNDz8eW6Wms1+9ZHlWjs7mb09AKSq1W+XFaGAfLzwkRPePgDA1+s/qixfJhYe4PIO+dHoMGtAIxeyC8q75Qp+gO/+PVsw6v19vV54att//u8XtFXIuuSb1y7DYiQAuLo4YQP0UH4AQFmrtBMAuuUK1dAwAEg6uvUGgz2T2SqRAUBYcCB21O5t64St0rKq+sTYiJFRbbNYkpocT5ulHxrWeLi5/O71/bj/xUWotydX3qeUdcn5Ab4trXfXx4ra2hNjI9raOwEgPOTu6Xy8eE/t2Hj45IVvfzj/7mv7jqVfYjDsDjy9A/O5E2pgW3vXRBuoGRm10MAJQavVXb6ZBwBr7uUhrQfPw/2jP75JTNhGR4QsmJuYV3yntkFICoEWaIexIbCnV/Hxl8cGVMOk+Af3XLwX7xeRER8dFh89Jp/fP6ACABdnJ/xaODs57ty8mmT87q3rmAwG7hrYbNbuLevKqwQ1AiHuNzNyisUSWYCf95svPslgMLAzRkeE/Om9V5hMxv1zlZqSkF9SOVGuiMC5enb3Y6Q12xhXnty7D3AjCBIXFRoXFUosg3PFYbOwS4BzRXSgu7eus2fevdNRFCVxhRXGufrNS0/Z3XvabXJcaTQjB4+k6/SGN1580nqnT/T12P8DqmGDwcj1cENRNLuw/NT5GwDg/TbXxckRABRKslw4ePi0WjPCYDCErdLahhbq7BUJVH1gQTGQ8h9WNgoARrVaAHB2crT+EAswt+Bx0mmSvJJKeZ8yMow/0ZkIIqw/tVaru5KZD2b8VXJ89P49W1pa2xfNT5roo16kpTkYOdey8gHg0TVLpi+NhIXnX8wAs8rp2+jYHiZT7Oa2ACAnNCLf2SWExQYA59ERF5NpyM6unuPw6JqNSsYvt9tFD+66oJAlrS3L+3oxuWAHkNjdCQBfhtx1m0XOzg2+fkmy9rDRkSvud+fs3q2vYRkM/5qbimkFAJDa23+YlHziZtd2YeNUygVhazsALE6dY6VmjAzjb92wnLofi81iSQcACMUSAOAH+Epl3eK2jrCQwI4uuauLM+5P7ZnMA/t2fvjpoR/PXUNRlOfhtu/xTebOuP/JrbSZxrDgQHmfslUq4wf4Clvb+QG+7Z09QrEUADDVEn4veGMNFDS3FlfU/PfH36iG1Lu2ruMH+j0kDbQep87f6OlVLFmYEjc26FoJLP6pNSP1TWJZt7xP0S+SyAAAz6ITYY52ImRd8k+/PjE4NLx900qSVgCAlUtSr90q+PTrE6kp8TERoTGRIVSnMG9O7PXbRfVNor/847t5SbERoUHhITQDETz+iSUysaSjW65Q9A8AwKhWpxpSu7k6A0CjsA0AVi9dwGCMCXgTjX8YiFx1dPUolAMYV9SV2DBxrqjPdxG5io0Mi44IdqOs8Jg3J/ZaVmF9k+h/PvsW4yoiNAihPM7AsrfHfCjGVVdPH5ErTPtiY741yxZiWgE/fKJcoSj67Y8X5H3KXVvWRkeEWH8gKdmOJTzgbur67ugcQRAOm4VZaDSRMxbKAVVyQvSc+KjvT186eykzLjrM+reS0Ka4iX/SrhgYF3qDoadXCQBfHklH7OiPxTTf/WOitgFAt1yRfvEmk8nY9/ijkzh8Eqc+fSGjp1fxyILk2LHCF8ei+UmL5k/y1T4kM1qlMlFbBz/ANyw4kDjDRTpkumejcKiYTAAw2NkBgJbJBICRe/3T/p4NmFYI0OvXKfvCVSofjTpMqQAAf/UvqX1MkaAUytn4Y5woGt4nRwEGWKxtyjHeScNi+6hUzpR7x0rQyIXObjkA8LjWvpcK81DU/d6eXGcnx8GhYeWACpMgi1LnSGXdLW3t9vb2RqORGLwBIMDXa1navKz8UgB4+ZmNjtRJr3uINJM3Cwv2L821f/cAAB5ISURBVK6oaZN2JsSEK/sHE2LCdXq9WCIzGo1YdiF07JtSdm1ZW1ZZpxpShwT5r11m9oOe1jcwbX7SlDTQSly4np1XUhkWHLBn2/rJ1SCWyC7fzK1vEptMJi+ehyfXHRvT448qEWGOdhyd3fKPvzo2rB4BgJKKujVLF5LWmu3YtMqL63ElMz+vuDKvuBJBkCB/n2WL5i5Nm4t7dp6H++9ff+78tdsV1Q2tUhkAODo6JMVGbl67FM9VAoDRZLqamV9QWtWnHOCwWX4+Xh7urtjNbzDeTQZiy+v8vO9rdQ8Oc1wZjTT33pRw5c3jXr6ZNwmuHlu3DOMKc4UGo9EcV3qDHuvbVK4m50mvZObXCJp5Hm7OTo6FZdXYzpFRLQBU1jVKOrriosPcXV1ojyX5dA83FwRBVENqAEibl+js5Ojm6uztyW3v7AEAHiVvEejn88JT29gs+9v5ZVJZd3ZB+erxUm60KwMstHqihHTLFdghjS1tEzpwBtCn6P/HoR90Ov0LT20j3lnTh4s3cvJLq0L5/ru3rpvyyqkuur5JDAAxESFUrYDQPUP7MGCVavB5YVNsd6cdiiqcXHqdnTFhwbwX4E0A9T5+C6StL0vaPgiPBID5GnVMT9eoPSvf7e74ZK5aja1meK+4gPYsnlavriWBRi5gT6qM+5A0DgtchwUH1AiErVJZS2s71911bmLM6fM3WlrbHTgcAAgLGRO8u+WKwrIqBoNhNBqzCysSYyMnKnixzL9Y0oFlFEL5ASYT2i2vlHR0t0o72Sz7AD9vYvnz124bTSYGg9Eu6xa1dVh4ktvKBs5Lik2/kDF9DSTiwvXsSxm5Pl68N158kmNmBbhl1Da0HDxyms1iPb1z05z4SGy2+0pm3s9d8smZJOvuZdjZvfT09rpGUWFZ9Q/nrj3/5FZiAQRBli2au2zRXFmXvL5J1NgiETSLTpy9WlHd8JuX9+JR0NuTe2DfztFdOkGzuFkkqREIiytqyirr3njpKWzmwmgy/d+hHwXN4tTk+Jee3hEWHIAx+fK7/2Mk9EZXZ6dhtWaYsm55EsC52rtjY3JCFMbV5Zu5sunkamlaytK0FFmXXNAsbhC24Vy99crTdgiCuTmMK+1uvaBZ3NTShnP15oG92MyFCUWJXOHzcUSuUBQlcYUQHk+AiYTJ4ooaAFD0Dx4+eYH00/lr2QDw1st7zckF6qw8191V0T+oGRl1dODgkwvYIiquB3k888qzO7Eb4fHNaz795sSljNy0eYk0S+3ozmt5D+2cxbjVAkBTSxsArF66gPb1Dxiy8st+unzLmtqmEIr+gU++/kE5oNq9dZ25R8mmFheuZ1/JzPfx4r3+wp7J+auJAkuYRYQFUa/dw6YSMOzq6/1taaGOyTw6Z94lbx9sseQfxS07B/qJxf4SF3+6S7ZVUDu/S6Zic8L75ADwj/kL5fcSru1sNgAY7ez+OT/NRBdi2u1p5tytAY1c8PX2bGvvbJf1LEhJsKYKCzEvlB9QIxAKxVJ5n3Lh3ASeh5sn172ltR2b0SRO6OoNhkPHfxrV6n71/K7M3NIagfDG7aIJrV0HgCB/HyaT0d2rFLV1AEBUGJ9hZ5dfUllZ2zis1kSFBROTk2VV9bnFd0L5Ads3rfzsmx8OnTj3/tsvTXSKMSw4cNINvJ5VuHH1IxM6HQYURX+6cut6VqGvN++dV/ZNelr0elaBwWD81f7t487yWgkGg/Hyvh1zk2KT4qJEbR2FZdUxESG06zMC/LwD/LzXrVik6B/88yeHGoStotb2qLEvReawWXMTY+Ymxuzeuu7c1axrtwqu3srH5EKLWCpoFocFB7z8zE4L9gQH+XX29Da1SFISLL1xzxo8cK7WLk8jcoVnLzCvx2bZz02MSUmIxrm6kpkXFxWKIIiwpY3KFXUwjXHVKGxLjh/zmryJutT9e7ZqdeRXLBw9dVE5oHp212M8rlswZcqvvknUJJIsTEkI8PPGT4059Kjw4KLymsraxkcWJOPW3qltAIDYSHI2G1/dGRsVmhATXtcoupSRO4nEG+1MBGlgSluSBBRFc4ruAEBSXCQ+d0YFkzGZqbH7QWdP7+f/OqkcUO3cvHrcBMz9A0XRc1ezbtwu8vXmvXVgr2V/JWgWN4ulqXPiSEO7icJoNIqlMgAIDQrAzQBKBuuhEg2Pi4RMo/GvCx85a/Fxx2fbpWy97nxcoqtO56YdvRYV+2Mgv4n9y8P87fb2/U7OHurhDo5DpttUfr2CZm5vXlIMAOSVVPYP3n1dl9Fkun67cBK1Y9n4/JJKAMDWKkeFB4+MaiuqGxAECeP/Mvj+6fItqax7ceqclISYF/dud3J0+OnKraYJZvAYDEZwoJ/RaCwqr3F1cfbx4mERKLf4DgCEBv8SvPsU/cfSL9szmS88tS0uKmzDqsXK/sF/nTg30a6DNQFrIPaYnPUNPHc1a6INBACj0Xjk5MXrWYXBgX6/+/X+Ca0fJkExoIKxTzp1dPWUVtZPoirsDpwTHzU3KRYAOGzWgX07mEzGD+eudfb0YmVGRrVHT1+SdfcSD+S6u2IG4J43r7gyM7eEOBuCIIifjycA4GoP+xYA0XKjyXQpI5c0n73ykVSGnd3t/DIsLYmjvEqAXTLrQctVWZXZ5/It4P65wkHiCptc9/f1gntcoShK5Ao7tQlFca5wp0nkiphXqKhuKCitsr514SGBcVFhpH8slj0AhAUHxEWFkZrQ1NL22Tc/XM3M/9vB77FHPfElAiiKbli5GEGQmznFo1odtqenV1leJXB3dUlNjifyScLjm9cgCJJdUI5Taj2oTgBPeJCii2V30Shs6+lVeHLdYyayhmO6IZbIPjp4rH9waN8Tj65fMeHnYycKo9F49NSlG7eL+AG+7732rGV/1SyS/OPQj1cz8z/66jjWGSaNAdWw0WhEEMTF+Rd1Qu0q1AW2JNxPAnii4GnUAKAkDP0fGR5aJCO/03p9S7OGzf5rWMTbsfEvJM/7IDySqBUwXI6IAoDf1FZ6j513WDmk4tyHPKLRvCmJMXFRYYJm8YefHpo/J57JtKtrFNGufcNgaTIiJBBBEOxWx8ZDUeHBhWXVas1IgJ83PllbWduYmVvi7cndu2MjAHi4uby4d/vn3548dPzcB+++THwRwrgIDwkUtXWManVx0eEA4Ml157q7KgdUQFjnaDQaD504NzKqfXrnJmzSbtvGlaLWjvom8ZXM/M1rl1p/OmIDsbmMaW2gwWA8eOR0bUMLADg5ORw+eZ4YIP19vCY0lpqbGJORXXTo+E+pyfFOjg6tUllVffPk8oRYHyAmb4ID/XY+uvr0hYxvvj/7h7dfsmcyy6vqC0qrCkqrEmMj/Hw8fb08DUZjjaBZ3qcMDwkMCwnEGnj9dmFPr+JmTklcVKi3F9fNxVmu6L+dX4YgyMol87HKY6PCOGxWbUPL18fOhvED+wdVNQKhon+A9PbAsOCAnZvXpF/M+OybE0lxkcGBfnqDQSiWito6vD25afOSrF/Hl5IQfTOn+NDxn+bPiXN2cpxyrh7fvObU+Rs4VxXVApwrf18vH0+e0WSqrm+i5SojuzguKtTHm+fm4tzTp8S4WrX07nuE4qLDca7Cg4OUA4NErvDAHB4S+Phja09fuIFxFRLkrzcYmkUSnCsGY1o+ZiaSdGAbGs1IT68ijLDcB5M+q5ak3sor/es/j6TOiRvV6grLq3U6/b4nNuPXjtb/BPh5L1mYnFdceebizTdfov/oAxVqzcjR05fu2jMyiv1/8Eg6tmfpwuSkuCgEQbLyy7CHDwFA0tEJALlFdzBJymaxXnhqKwAYDMYzl24CwPoVi2Ym5NwuKB/XKkGz+ODhdL3BwHV3raprLq8SEBfy79i0ipr7MQe1ZuT79MvYNs7Vl0fPYHuWLkxOjI00GIxfHk2vaxQBgJOTw5FTF0j+irSIgdgZ5H3KUP6YyVxrGohjUDUEAE6ODnb3bjRcE5Cet7QwN0EsPANJiAr/wHXNDf9VUbo2IGiQxYrqV87p7BilTBzI3Nyj5N2Hy0tEHlwjggCAzo6hZLPzudw6zl0t/gk/JFHRl9wh/TnrRhE/pMvRyVWvj1IqYrs7j82Z9ynf7PviLIM+RfbGi0+mX8zILb6TlV+KIEgoP+APb734+b9O0r6YzMLNwGGz/H29ZF1yBw4bG/TgT/fi7zfsH1AdPX2JYWf34t7teHxNjI14dO3Syxm53xz/6d1X91l/v+E9DM/WRkeEFJXXAEDoPU/087XbYolsTnzUikfuhh+Gnd3Lz+z80yffXLieHcYPsP4pgxlu4JBag2kFuPe6BSJGR+nfs2sOOx9dpdPr84ruXMsqAAAfL96ebevCQ4L+/MmhCdUDZvrA2uVpDcLWGoHwx3PXn921eWna3Miw4KuZ+Y2iNvy9PWyW/ZplC7esW4aFTyaT8effvlJQVp1bdKe4ohZ/4V1woN+2jSvxiQAPN5c3Xnzy+/TL5VWC8ioBh82KjQp7/YU9567culPbSLRh3Yq0UL7/mUs3axtasJM6OTqsXrpg+6ZVE1rz//jm1Tq9Pr+4Ekuz+Xjxdm9dGxHKnyqu1ixbKGgW41wtWZgSEcq3wBWCIAyG3Ye/e7WgrDqnsILE1fZNqxJjIzAn6OHm8uZLTx09fYmWK6ITxLhKv5hB5GrNsoXbNq7EtMJ0OM0FKQmZuaWqoeGw4EB+gB9x7QK2vWfbendXlxvZReevZwOAJ9d9/wtbE2LCx61564YVZZX1dY2iukaRNeUBQKc3YC+GwqE3/LIHTxK0d3aTirV39mALMLH1yyiK/nDuWkeXPJTvv2zRXNJZUBStqm/GLiKCINKObgAgDoInh3GtAoDyagHWT5QDKiXliQz1igkM6C1zhX1tdUitwbQC3FtJQATVX6Umx9/KK1MNDYfyA4L8yQ92WtNAHNgCFxfKxIeFVQsWxMHMiIb3o2JYRuMyccvGJgEA9Lq4/pCUUuHu8X/ZmcRi30fH/kXeHdfdGdfdSdz/MsD16Lj/iLo78fp8yvwDPn67G+vXCO+SpmGzb0TFXvCd/BOziFpt9uMoBoOxs6eX5+FmzXIhG2YpRka18j4l193t/h2W9dBoRrp7la4uTh7uruaedkNRVN6nHNXqPLnutD0QRdFeRb9Orw/w9R5Xb+kNhq7uXkdHh3Gfb7SAh4crqufq6VVodXrskQSiT8Sn3nsV/XqDAeOKNPtOXMqHoqjBaOzskmNcTXSp4yQwqtX19CoC/X3w1hEtxw3o6VWyWPZcd9cZnmwmLfkkEmXukGaR5JOvT7g4O/32V8/Qvoftb18cxdZXYeCwWe/96tkgf58pNn0WYlSrk/cpA/y8rX8IdnIw94INkp4g3WikP5eW07zs+D7hYzDEjWjEHI7EniZ5mTKi+SLvdper++9T5nNQk7PRiKDARk3xKtULlWV2KLpj/WYxa8yBAXp99IhGwuHgL4cGgPxUs08CWoAluWCDDTY8nLAw0CE9HmZhaR7VDxJjIamGmVwUZmVUnklQowvtiBP/M7+0KjjAN8jMu4+wF0kx7BhMpp2bi3N8dPj9LEKyYXIgilFr+j/+E17DdMgFy/iLsOnRxvr/t2jpac8xr4ZjoGh+xhWOXr9t/aO0OoOEyckF2xcpbbBh9oEUokg7qTHMwlHUn0jigLikfGaCN9GJU0/6QFazkzikjStAoJH63i0iJvSaahumCdRHYLANkjSk9v+ZXP9IwgCLDQArO2XXubzBewmYYL3ubWGTg05Xxg+xRitMGja5YIMNsxikoQ+YcXYW1oRThYK5eDzD2QXiPAhx+8HmG3AmScw/EBFjw5SAVjeQHrkk/UQ9ambwXWDQ/J6uNIk4s0Pa4+qqYzCddVrPoSEAtCA0/J34Sb4Q00rY5IINNsxKWI6gpCwrVQcQ4xyxBss59hkANScMFA30kIB2YYdNN8xq4P2fKhqI63AflHlKBuPJBYu2KhVLerp5IxqOwSDkeebwQ877+ddzpn2JoU0u2GDDrAQ1guKBivp8ATWhSp25sBDnZlI6mJMvM3DqicKyCHuoTLXBSlATdRbWNDwQC00AP3N5P3Nn4r3dJNiWOtpgwywGdRW3NYFq3GVcxKpmOLUAZmaRqZY8DCHZXC4EHsQS0YcQD+ElmwRoF7qaW+sw0cMt73yoML0Pq9hggw3TCtLKA3wbz6YCZd6B6rKJKoF2fEzcP5Mg5oFp98ODG+QRLSFtE1MOD38MmHJQl84A4ZLNRjbMLWKgbuOwsKzY3CEPPzM2uWCDDbMS5pwLMY2Pxy3qtAXtei48MFMj8czEZqouIU2sUG14qCIQVbFRRRsRD4/lljGuncRJfXP5A5KcwsmxsvIHjgmZ8ZDYPC6MJpO566WnfLjSJhdssGFWgjSpj++n6gCEsl6BVNjcUIlafmYyyVRrSdGI+OjEjFllDYgWmuOciIfHcsugze4Qt82lUnBZgF81opwdN301W4Lu7EV+SeWbf/joVh75BRKK/sE3/uujz775gbjTttTRBhtmMSxMi9IuEiSN0UnrwDGQZitmPjYTxQHVTqoSQh6yGXEimYdPXmgWS8c9ZPH8pC3rl0+nUVbBApOkSI/vt7zchLYq6spQYh8jXt+H9hL/2yC7sGJUqwvw8ybRm5VXajQasW8q4fzb5IINU4BuuUIs6eBx3aPHfoR6VmCGs9lTyxU1/JMSwrQZBdqhHl6Amv9/UAl/a9TMQx5OhtUaZf+gm4uzvT29sx0Z1ao1I2oN+XM8M9wiZOxSFXw/kVtSGdI2Qpn2IvVJaiqL9BNJapDyFjBWO1LNmHkYDMayqjGf8OV5uEWNd18PqoabxZKk2Ej2pL5RN4UQiqWyLjkAfPr1CeL+/Xu2FJTXAMDtgvLbBeX4fptcsGEK0CRqO37mSmpy/KyTC6ShqoX95kpOFI0trSfOXp0qrqhhnmgebSilJvlpYwApQjwQp2yOZ6JVJhTFXF6gnzdR5ag1I9hXlPD9DxCvPvdEeEggcQ9+XbLyy06dvwHm19NR00LjyiMLsRz/n5SwoY7jaSUatR6g9B9zgsBoMpG+BGGuPLETUnMVWFV25rvujEEzMnrk1EXinuSEaMtyQaMZef/vX42MamOjQt86sHeaDbQEo8l09vItAFg0P6lZJFH0Dy5IiXd1ccb6pEYzEhUeHOTvk11QDgiyYvE8BEFscmFWwmgytYileSVV3fK+TasfmZsU+2DteTgHdpZhbrwCZib+cTzw2EOEhcQvyZtTx4jUdtG6aRg7+Jvaaz2oGi6trCuvFnDY7LdeHuM9cWtJvT0lMYaYuFarR7Dvgv7zf3+Hf1Jcq9N/9OUxWZd8w8rFQZtXT8Kqsqr68moBm8UiWYXDaDKJWttziyt7ehUbVy2e6D1oYaiN/wmUzmah72GXBrOKyBXpWhtNplu5pYXl1T1yhb0908/Hc93yRfPm/GI8NVlFqwbw/zGuyqrqOWz2bw6QvxWOIIi0o+taVqFA2DoyMsrjusdEBG/buNLNxZnaIqpSIZphuSr8wNLKups5JSiKIgDEnpqcEP3omiXm2JscHB04eJOr6pqzC8stlwcAFMBkMgGAXk9eSDjDuHg9p1Uqmz8nbv+eLUXlNUdOXfT25G5Zvzy/pOpWXqmPF++NF/aw2Sy1ZqS4ojY6PDglMcYmF2YfDp+8UFpZZzAYsT+H1JoHa89sBDXykRwx0W09VPoAB2mmgOrfaRPIMFYMEWsjlbEwWzElkHR0/fPbUwOqIexPPH6QGvjdj+fLqurx3q4aVpPK4NtEUw8dPyfrks+Jj9rx6KqJWvXFd6ctWIXh8MkLRKum6h6kTgdQaTeX7EFR9Mipi1SuiDG+f0D19bGzYonMgcNOjIvU6fRCsfSb4z+t71j0+OY1+Knx3APJGNI2lSvqnZJTVHH6fIbBaAzy9/GODO3o6skvqaqsbXr/nQNcuq9qWZiq+KUqP29qVXi/7elVtrV3MpkMJmPMF+pVQ8PU090nmExGXFQYtt3Tq7TmECdHhz+89WJjS1tKQsyU22M9FMqBjOwiF2fHJ7dvAIAFKfHpF29mF1ZsXP1IWXW9PZN5YN8OFsseRdENKxc3tbTVN4n5gb42uTD7EBzox2GzAaBG0NynHHjQ5sxi0A5iYKyzpnrA+5yMmCoQw4aFESEp+Wy5NiCID2K+mpqjvn/14MBhpyTGAMCwWkOaAMaBIAje22sbhFhvHzehkn4xo0bQHODn/dLe7RO9UrhVQ8Pq8mqBuWJUqyzj8MkLHA6b9qehe2HMXE6e2EtplR/eIc1xhR/Y2NLWKu18dO3SLeuWYVe5TznwP599m5FdvCAlIcjfh9r/qQbjpxuXq1GtLrfoDtfD7bX9T/j7eGHHpl+8mZlbcurn66/t30U9xGgyDaqGMSVBJIRYlZ+3J7YTr+rV557Ay6s1IwDw5LYNS9NSqLw9DPDx4vl4PYB3MhLB47q/96tnNSOjLs6OAMBkMvfu3MjzcNeMjO7YtKq+UdTS2l5UXiPvU3bLFQOq4ZyiCqms+77kQkVNQ0tr+5plC3ge7pKOrvySyvbOHjvELjwkcNumlecu3zKh6Jb1yx3o7hNF/0BmbqmPJ3fFI/OtPJ1Wqzt/PdvHi7ti8XytVldYXl3XKBpUDXM93NYsWxAVNvWz5pYbON1fZDeH1UsXYBt9yoE+5cB93gmito6KmoZ2WbdWpw/w805NjsP1MgaMdl9v3vJF87RaXVFFTW1DizW0KwdUmTnFKMDa5Wn4SGJANXQ7v7y9s2doWO3n7RkU6LswJd517BgORdGquqbK2qZeZb89k8kP9I0OD0mMjSDVP6rVFZXXNIskiv4BZyenkCC/9SsW0a4eqm1oqWts6eiSs+yZIUH+85PjA3y9qMXMhRbcP4raOsqrBR2dPVqd3t/Xa0FKPJWrn6/d9vXmTbSLmuMqu6BCKuvGuAoM8Embm0Dlqrq++U5NI85VTERoQkw43iIs6o9qdcUVtU0tbRhXoXz/dcvT2GwWNd9Q1yiqa2xp7+xh2TND+QHzk+P9fTzB/KB20vD25O7duREAJB1d5uQCAKxZthA77z+/G8RCIFHVUe3JL626mVPi4uz46+d3czhs0ih5XPu9PblP7diAWWVBLuD34OffDliWCyYTCgBDw2rNCHkxIwbi0+3UOSCqjANC7odUbPXSBdh+klW47Fg0Pyk8JNCL54Ef68l1n5sUk1dcKRRL+ZTPbdPeEfjOcbnisFlvv/I0ADg5OuDHbli5ODO3hPZpkcGh4b9/8b28T5kYG/n6C7uJZ6dWBQB4VUQqMLmARUFzQnmGBUS3XJFbfIe0M8jfZ9H8MV+Eyiup7Orp27xmCQqQXVjRIGwFFA0LDtywcpHjvVbXNggbhG3hwYHE+aPBoeEbt4vYLNbWDcsBAEXRq7cK1JqR1OT4UL4/XqxGIGxsacPPGxYcIJV1f/fjBdXQsGpoeHBIrdaMkGjhsFk+XrzFqXOCA335AX73JReaWiRZ+aUJMRHZhRXXswrxM/Up+3duXt3Y0ibp6EqMiYiLDgOAwz9eqGkQrlg8f9vGFQDQKGy7mVOM+QIrYTAab+YUh4cERobyDx5Jl/fdTf60tXcmxUZMh1yw3MApP90MQ9YlP30hQ9AsBgAOm4UgiFjSkVd8Z+uGFY+tW4YXw2mPCAkyRzvVrfQpBz7+6rhCOfD0zk14/Gtqafvs0A8Gg9GT58G2Z5ZV1ReWV5+/mrVz8+pVS+76X6PJdPBweo2gmcNmeXI9+jT9gmbx9azCkCD/N17cgwfLq7fyb9wuwlyDm4tzq7SzRtBcUFr1+9f3exCSnP0DqiOnLmJtZLNZCEBtQ8vVWwXbN67csGoxVoYYLIljNSAMzmi5yi+p3LJ+OfH5N4PRmJlbMtEuinO1d8dGy1xduHb78cfWrHwkFbPKYDRa5grrsdeyCq5nFZK4yi+p/I83nidypewfpHJ1JTN/x6ZVG1Ytph3vzozPpV1IQd0GgGaR5MTZq0wm49XnnvDkugPdig0rMVUJJIPBAADvvvYMNRhjuJVXii11hLGJBHyDKBQsFAMzi1GI0gpBEG9PLskAO8QOAEzTcymJ0f2eWQAAKF2WDhvOAkBtg7CtvTOUH2BlVSaTye7e4A3r564uzqRLT6RohpMN/YOqzNwS0s7U5HiSXKiqa65tEAYH+l64ntOnHLBnMvUGQ7NYWl4t+OCdA9hASNjanplbYlhsIMoF1ZA6M7fE2ckRkwsIgvj5eH79/dnK2sb3337JwYEDAArlwL9++BkB+OPbL2FHIQjiwGHXNba4ODs6OTp4eXKdnRztmYzbBeUebi6vPPu4F4+LqS6cvf8PXbmd0ZzPNiMAAAAASUVORK5CYII=">
这里的drwxrwxrwx 就是用户的权限

>d代表的是这个文档是一个文件夹

>r是可读，w是可写，x是可执行
>>那么第一个rwx代表着文档所有者的权限
第二个rwx就是就是文档所属群组的权限
第三个就是其他人的权限，什么是其他人呢，就是不属于这个文件拥有者和所属群组中的用户就是其他人

>>如果没有权限则用-来表示,但是在第一开头除外，如果开头的d是-的话，就代表着这个文档是一个文件，而不是目录

	它们可以这样区分
	[d][rwx][rwx][rwx]
	 1  234  567  890
		1 代表这个文档是否是目录或文件，本例中为(d);
	234 代表拥有者的权限，本例为(rwx);
	567 代表同群组权限，本例为(rwx);
	890 代表其他用户权限, 本例为(rwx);
	如果没有权限，就会变成(-);
那么如何改变权限呢

* chgrp : 改变文件所属群组
```shell
	chgrp [-R] name filename
```
* chown : 改变文件拥有者
```shell
	chown [-R] name:name filename
```
* chmod : 改变文件的权限
这就用到了上面的知识rwx
用户组、群组、其他人各自的三个权限是相加的

	r:4

	w:2

	x:1

	用户组 = rwx = 4+2+1 = 7
	群组   = rwx = 4+2+1 = 7
	其他人 = rwx = 4+2+1 = 7

```shell
	chmod 777 filename
```

就是给这个文件全部的权限

arkssac:arkssac 就代表着是这个文档所属的用户和用户群组

时间则表示，修改文档的最后修改时间

最后就是文档的名称





# linux的命令：

## 基础命令

​                                                                                                                                                                                                                                                                                   

ls + 想要列出绝对路径或相对路径:
列出指定路径下的所有文件/文件夹的名称（相对路径：在相对路径中通常会用到两个符号“./”,"../"；"./"是表示当前目录;"../"是上一级目录,绝对路径：绝对路径不需要参照物，直接从根目录下寻找）

* ls -l + （想要列出绝对路径或相对路径)

* ls -la (想要列出绝对路径或相对路径)

* ls -lh (想要列出绝对路径或相对路径)

* -l :		表示list,表示以详细列表的心事进行展示

* -a:		表示显示所有的文件/文件夹（包含了隐藏文件/文件夹）

* -h :		列出指定路径下的所有文件/文件夹的名称，以列表的形式并且在显示大小的时候可以以可读性较高的形式显示



pwd:  (print working directory,打印当前工作目录)

cd： change directory切换当前工作的目录

* mkdir:  	(make directory,创建目录,路径，可以是文件夹名称也可以是包含名称的一个完整路径) 

 * mkdir -p:  一次性创建多层不存在的目录的时候，添加-p参数，否则会报错

touch 文件路径:    创建文件，路径可以是直接的文件名也可以是路径 

cp 文件名 文件路径位置+文件名（可根据需求修改文件名    ）:(copy,复制文件/文件夹到指定的位置)

mv   (move,移动,剪切)移动文档到新的位置，需要移动的文档路径 需要保存的位置；mv也是重命名命令，语法和移动的语法一样

* rm （remove,移动、删除）

 * -f: force,强制删除，不提示是否删除

 * -r: 表示递归，删除目录使用的



\*称之为通配符，意思表示任意的字符，如：linux* *，则表示只要文件以linux开头的文件，后续的不管

* vim:

 * 语法：vim 文件的路径

 * 打开一个文件

 * 1 >: 覆盖输出，会覆盖吊原先的文件内容

* 1 >>:  追加输出，不会覆盖原始文件内容，会在原始内容末尾继续添加

cat  文件路径: 	直接打开一个文文件；cat还能对文件进行合并：cat 待合并的文件路径1 待合并的文件路径2 ...文件路径n> 合并之后的文件路径

## 进阶命令：

1. df -h

	* 查看磁盘的空间

	* Filesystem:分区

	* Size:大小

	* Used:已使用的空间

	* Avail:可用的空间

	* Use%：使用的百分比 

2. free

 	* 查看内存使用情况
 	
 	* -m: mb为单位
 	
 	* -g:	gb为单位
 	
 	* -/+ buffers/cache	已经被分配但是没有被使用的
 	
 	* buffers:  输入
 	
 	* cachd：输出
 	
 	* Swqp:用于临时内存，当系统真实内存不够用的时候可以临时使用磁盘空间来充当内存

3. head

 	* 查看一个文件的前n行，如果n不指定数字的话，则默认显示前10行。
 	
 	*  head 文件路径

4. tail

 	* 查看一个文件的末n行，如果n不指定数字的话就默认末10行
 	
 	* tail 文件路径
 	
 	* -f ： 查看一个文件的动态的变化改，该命令一般用于查看系统日志

5. less

 	* 查看文件，以较少的内容进行输出，按下辅助功能键（数字+回车、空格+上下方向键）查看更多
 	
 	* less 需要查看的文件的路径

6. wc

	* 统计文件内容信息（包括行数、单词数、字节数）

	* wc -lwc 需要统计的文件路径

 	* -l: 表示lines，行数
 	
 	* -w: 表示words，单词数 依照空格来判断单词数量
 	
 	* -c: 表示bytes，字节数

7. date

 	* 表示操作时间日期（读取、设置）
 	
 	* date   ：输出形式2018年3月24日 星期六 15:54:28
 	
 	* date +%F	(等价于date "+Y%-%m-%d")	 输出形式2018-01-24
 	
 	* date ''+%F %T “	等价操作"+Y-%m-%d %H:%M:%S"引号表示让年月日于时分秒成为一个不可分割的整体，输出形式：2018-01-24 16:01:0
 	
 	* date   -d "-1 day"  "+Y-%m-%d %H:%M:%S"  符号的可选值+（之后）、-（之前）
 	
 	* 单位可选值（day、month、year）
 	
 	* %F：表示完整 的年月日
 	
 	* %T: 表示完整的时分秒
 	
 	* %Y: 表示四位年份
 	
 	* %m:表示两位月份（带前导0）
 	
 	* %d:表示日期（带前导0）
 	
 	* %H：表示小时（带前导0）
 	
 	* %M：表示分钟（带前导0）
 	
 	* %S：表示秒数（带前导0）

8. cal命令

	* 用来操作日历的

	* cal -1	直接输出当月的日历

	* cal -3	直接输出上一个月+本月+下一个月的日历

	* cal -y  显示一年的日历

9. clear/ctrl+L命令

	* 清除终端中已经存在的命令和结果（信息）。

	* clear			或者快捷键：ctrl+l

	* 需要注意的是，该命令并不是真的清楚了之前的信息，而是把之前的信息隐藏到了最上面，可以通过滚动条继续查看以前的信息。

10. 管道（重要）

	* 管道符：|

	* 管道符一般可以用于”过滤“，”特殊“，”扩展处理“。

	* 管道符不能单独使用，必须需要配合其他命令来一起使用，其作用主要是辅助作用

	* 过滤案例：ls / | grep y 意思是通过管道查询出根目录下包含”y“字母的文档名称。

	* 一贯道作为分界线，前面的命令有个输出，后面需要先输入，然后再过滤，最后在输出，

	* 通俗的讲就是管道前面的指令的输出让给后面指令的输出；

	* grep指令：主要用于过滤

	* 特殊用法案例：通过管道的操作方法来实现less的等价效果（了解）

	* 之前通过less查看一个文件，可以讲less 路径

	* 现在通过管道还可以这么弄：cat 路径 | less

	* 扩展处理案例：ls / | wc -l 可以通过这个指令来显示根目录下的文档总个数

## 高级命令

1. hostname命令

	* 操作服务器的主机名（读取、设置）

	* hostname				表示输出完整的主机名

	* hostname -f			表示输出当前主机名中给FQDN（全限定域名）

2. id命令

	* 查看一个用户的一些基本信息（包含了用户id，用户组的id，附加组id），该指令如果不指定用户则默认当前用户

	* id  	默认显示当前执行该命的用户基本

	* id 用户名		显示指定用户的基本信息

3. whoami命令

	* 作用是"我是谁?"显示当前登录的用户名，一般用于shell脚本，用于获取当前操作的用户名方便记录日志。

4. ps -ef命令

	* 作用于查看服务器的进程信息

	* -e: 			等价于”-A“，表示列出全部的进程

	* -f:			  显示全部的列（显示全字段）

	* UID: 	该进程执行的用户id；

	* PID:	 进程id；

	* PPID: 	 该进程的父级进程id，如果一个程序的父级进程找不到，该程序的进程称之为僵尸进程；

	* C:  		cpu的占用率，其形式是百分数；

	* STIME :		进行的启动时间;

	* TTY:			终端设备，发起该进程的设备势必符号，如果显示”？“则表示该进程并不是由终端设备发起的；

	* TIME：		进程的执行时间；

	* CMD： 		该进程的名称或者对应的路径：

5. top命令

	* 查看服务器的进程占的资源

	* top:			动态显示；退出按q

	* PID:			进程id；

	* USER:			该进程对应的用户；

	* PR： 			优先级；

	* VIRT：			虚拟内存；

	* RES：		     常驻内存；

	* SHR：			共享内存，计算一个进程实际使用的内存=常驻内存RES-共享内存SHR；

	* S:					表示进行的状态（sleeping，其中S表示睡眠,R表示运行）；

	* %CPU： 		表示CPU的占用百分比；

	* %MEN：		表示内存的占用百分比;

	* TIME+： 		执行的时间；

	* COMMAND：		进程的名称或者路径；

	* P: 					表示讲结果按照CPU使用率从高到低进行降序排列；

	* 1： 			当前服务器拥有多个cpu的时候可以使用”1“快捷键来切换是否展示显示各个CPU的详细信息；



6. du -sh命令

	* 查看目录的真实大小

	* du -sh 

	* -s:  			summaries, 知识显示汇总的大小

	* -h:			  表示以高可读性的形式进行先显示



7. find命令

	* 用于查找文件（其参数有55个之多）

	* find  路径范围 选项 选项的值

	* -name:  		按照文档名称进行搜索（支持模糊搜索）

	* -type:  		   按照文档的类型进行搜索

​								文档类型：‘-’表示文件（在使用find的时候需要用f来替换），”d“表示文件夹

8. service命令

	* 用于空置一些软件的服务器启动/停止/重启

	* service  服务名 	 start/stop/restart

9. kill命令

	* 杀死进程

	* kill    PID  进程名称

	* killall  进程名称

10. ipconfig

	* 获取网卡信息

11. reboot命令

	* 重启计算机

	* reboot  -w  模拟重启，但不重启（只写关机与开机的日志信息）

12. shutdown命令

	* 关机

	* shutdown -h now  或者 shutdown -h 15:25

13. uptime命令

	* 输出计算机的持续在线时间（计算机从开机到现在的时间）

14. uname命令

	* 获取计算机操作系统相关的操作信息

	* uname				操作系统

	* uname   -a		all,获取全部的系统信息（类型、全部主机名、内核版本、发布时间、开源计划）

15.  netstat  -tnlp命令

        * 查看网络连接状态

        * netstat   -tnlp

        * -t  表示只列出TCP协议的连接

        * -n 表示将地址从字母组合转换成ip地址，将协议转化成端口号来显示

        * -l  表示过滤出”state（状态）“列中其值为LISTEN（监听）的连接；

        * -p 表示显示发起的连接进程pid和进程名称

16. man命令

	* manual 包含了linux中全部的命令手册，英文

	* man + 指令
	
17. poweroff命令
	* poweroff就是关机命令
	* 与shutdown不同的是它是直接关机，shutdown是可以延时关机
