Linux环境下配置golang环境步骤

1.先去studygolang.com下载linux安装包

2.进入到文件的目录下执行如下操作：

​	tar -C /usr/local -zxvf  go1.10.3.linux-amd64.tar.gz（将文件解压到/usr/local下的go文件夹）

3.安装 vim

​	sudo apt-get install vim

4.配置环境变量

​	vim /etc/profile

打开文件后在最后一行添加

​	export GOROOT=/usr/local/go

​	export PATHH=`$` PATH: `$`GOROOT/bin

```
 export GOROOT=/usr/local/go
 export GOPATH=/home/tts/go
 export GOBIN=$GOPATH/bin
 export PATH=$PATH:$GOROOT/bin
 export PATH=$PATH:$GOPATH/bin
```

编辑完成后按esc 输入如下命令

:wq!（若报错则执行）:w !sudo tee %

关闭控制台

5.确认配置成功

​	source /etc/profile

执行 go version出现版本号则配置成功



注意：为了解决每次需要重新 source /etc/profile操作，执行如下操作：

vim ~/.bashrc进入后在最后一句添加 source /etc/profile即可

root账户出现如下错误时：

***命令 'ls' 可在 '/bin/ls' 处找到***
***由于/bin 不在PATH 环境变量中，故无法找到该命令。***
***ls：未找到命令***

进入/usr/bin目录下，输入

export PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin 导入环境变量

echo $PATH     查看配置环境