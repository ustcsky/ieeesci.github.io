# 通用cookie管理器

## 什么是cookie?

Cookies是一种能够让网站服务器把少量数据储存到客户端的硬盘或内存，或是从客户端的硬盘读取数据的一种技术。Cookies是当你浏览某网站时，由Web服务器置于你硬盘上的一个非常小的文本文件，它可以记录你的用户ID、密码、浏览过的网页、停留的时间等信息。当你再次来到该网站时，网站通过读取Cookies，得知你的相关信息，就可以做出相应的动作，如在页面显示欢迎你的标语，或者让你不用输入ID、密码就直接登录等等。

从本质上讲，它可以看作是你的身份证。但Cookies不能作为代码执行，也不会传送病毒，且为你所专有，并只能由提供它的服务器来读取。保存的信息片断以“名/值”对(name-value pairs)的形式储存，一个“名/值”对仅仅是一条命名的数据。一个网站只能取得它放在你的电脑中的信息，它无法从其它的Cookies文件中取得信息，也无法得到你的电脑上的其它任何东西。

Cookies中的内容大多数经过了加密处理，因此一般用户看来只是一些毫无意义的字母数字组合，只有服务器的CGI处理程序才知道它们真正的含义。

由于Cookies是我们浏览的网站传输到用户计算机硬盘中的文本文件或内存中的数据，因此它在硬盘中存放的位置与使用的[操作系统](https://www.baidu.com/s?wd=操作系统&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)和浏览器密切相关。在Windows 9X系统计算机中，Cookies文件的存放位置为C:WindowsCookies，在Windows NT/2000/XP的计算机中，Cookies文件的存放位置为C:Documents and Settings用户名Cookies。

硬盘中的Cookies文件可以被[Web浏览器](https://www.baidu.com/s?wd=Web浏览器&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)读取，它的命令格式为：用户名@网站地址[数字].txt。如笔者计算机中的一个Cookies文件名为：ch@163[1].txt。要注意的是：硬盘中的Cookies属于文本文件，不是程序。

特别想说明的是，还有一个和cookie相似的文件，那就是session，它和cookie的作用几乎是相同的，最大的区别是session是放在[服务器端](https://www.baidu.com/s?wd=服务器端&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)的，而cookie是在客户端的。

## 微博cookie池A版本——基于selenium

https://www.jianshu.com/p/6784c261126e

这段时间因为要爬微博的数据，而微博很多数据都是要在登陆状态之下才能访问，所以就写了两个版本的微博cookie池，第一个是学习崔大神课程时候改写的，也是比较简单暴力的，只要网页不改就能一直有效，因为用的是selenium，第二个呢是抓包分析登陆时候的请求以及账号密码的登陆方式，用requests实现的，效率高速度快，但是只要微博改了加密算法，那就完了，今天我这里先分享第一个用selenium版本的cookie池，该脚本主要启动两个进程，一个是根据数据库的账户密码获取cookie，另一个是定时检验数据库cookie的有效性，运行之前我们是需要按照一定格式将账号录入数据库的,[githubhttps://github.com/xiaobeibei26/weibo_cookies](https://link.jianshu.com/?t=githubhttps://github.com/xiaobeibei26/weibo_cookies)
先看登陆界面网址[http://my.sina.com.cn/profile/unlogin](https://link.jianshu.com/?t=http://my.sina.com.cn/profile/unlogin)

## dockerfile定制镜像

定制镜像的基本思路：

1. 选择合适的基础镜像（`FROM`）；

2. 准备程序运行的环境（`ENTRYPOINT`, `RUN`,`ADD`, `COPY`, `ENV`, `WORKDIR`）

3. 将自己的程序打包好，拷贝到镜像文件系统（`ADD`, `COPY`）；

4. 设置开放的端口(`EXPOSE`)；

5. 设置数据卷(`VOLUME`)

6. 配置容器启动命令（`CMD`）；


```shell
git clone http://10.60.1.90/fengbin/cookiemanager.git

docker build -f DockfileMysql -t cmsql .
docker images|grep cmsql
docker build -f DockfileFlask -t cmflask .
docker images|grep cmflask

docker build -f DockfileFlask -t cmflask .
docker images|grep cm
docker save -o cmflask cmflask:latest
docker load --input cmflask

docker login hub.ict.ac.cn/student -u fengbin -p 'Mr7QC$LWb5'
docker tag cmflask:latest hub.ict.ac.cn/student/cmflask:latest
docker push hub.ict.ac.cn/student/cmflask:latest
```

