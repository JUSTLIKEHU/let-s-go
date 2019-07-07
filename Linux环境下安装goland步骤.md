Linux系统下安装Goland软件

1.JetBrains官网下载Linux下的安装包

2.进入到下载目录下，使用Tar命令将Go安装解压到/opt路径下

tar -C /opt -zxzf golang-2019.1.2.tar.gz      注意C记得大写

3,若报出没有权限则执行以下操作

ubuntu安装好后，root初始密码（默认密码）不知道，需要设置。
1、先用安装ubuntu的时候创建的用户登录到系统
2、然后输入命令：sudo passwd  摁回车
3、接下来会提示您：输入新密码，重复输入密码，最后提示您passwd：password updated sucessfully
此时已完成root密码的设置
4、接着就可以输入命令：su root

即以root的身份登录到系统里面去了，此时你再拷贝文件，就ok啦
--------------------- 





启动Goland

```
cd /opt/Goland-2018.1.1/
//sudo chmod a=+rx bin/idea.sh
//启动GoLand
sudo bin/idea.sh
```