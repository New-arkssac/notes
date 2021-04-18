# httpd换行符解析漏洞

启动环境

> `docker-compose build`
>
> `docker-compose up -d`
>
> 进入环境**自己ip的8080端口**

![image-20210404224231018](../../image/vulhub/image-20201228080520608.png)

上传一个webshell

![image-20210405172244303](../../image/vulhub/image-20210405172244303.png)

直接上传会失败

在burpsuite的2020版之后删除了hex模块，添加了可以直接输入hex编辑器

![image-20210405172225587](C:/Users/Cite-Arkssac/AppData/Roaming/Typora/typora-user-images/image-20210405172225587.png)

把这个空格的hex值换成0a换行的hex值

![image-20210405172531341](../../image/vulhub/image-20210405172531341.png)

然后点applychanges就可以了

![image-20210405172607920](../../image/vulhub/image-20210405172607920.png)

然后send发送

![image-20210405172636581](../../image/vulhub/image-20210405172636581.png)

发送成功

然后去验证

![image-20210405172744819](../../image/vulhub/image-20210405172744819.png)

得到解析后的php网页