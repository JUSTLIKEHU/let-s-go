LINUX下配置Bee相关设置以及遇到问题

1.配置好GOPATH和GOROOT

2.bee可执行文件默认在GOPATH/bin里面，所以需要吧GOPATH/bin添加到环境变量中去。

echo 'export PATH=`$`GOPATH/bin:$Path'  >> ~/.bashrc

source .bashrc

3.安装好之后，运行bee new 项目名来创建一个项目，注意：通过bee创建的项目代码都是$GOPATH/src目录下面。





注意：利用vim ~/.bashrc 插入下面数据

```
export GOROOT=/usr/local/go
export GOPATH=/home/tts/go
export PATH=$PATH:$GOPATH/bin
export PATH=$PATH:$GOROOT/bin
```

利用goland编写代码时可能会遇到控制台是root的情况导致用户配置的环境变量不可用。需要切换到root然后操作第2步骤

root和普通用户切换规则

root>>>>>user    exit

user>>>>>root     su





#### **注意：Goland中的Gopath一定不能和系统配置的冲突，否则会发生异常，全局gopath不要配置，只配置当前的就好。**