## 关于Golang中包管理工具vendor的学习与总结

##### **1.**go项目结构

首先理解govendor是依赖于gopath的。

Gopath的目录结构如下：

```
|---gopath
	|---src			存放源代码	*.go
	|---pkg			编译后生成的文件	*.a
	|---bin			编译后生成的可直营文件
```

我们的项目文件是存放在src目录下的。并且将gopath/bin添加到环境变量中去。

##### **2.**govendor

1).*介绍*

Golang 官方并没有推荐最佳的包管理方案。到了1.5版本时代，官方引入包管理的设计，加了 vendor 目录来支持本地包管理依赖。官方 wiki 推荐了多种支持这种特性的包管理工具，如：Godep、gv、gvt、glide、govendor等。即使使用vendor，也必须在**GOPATH**中。

govendor只是用来管理项目的依赖包，如果**GOPATH**中本身没有项目的依赖包，则需要通过go get先下载到**GOPATH**中，再通过govendor add+external拷贝到vendor目录中。

2).*查找依赖包路径的顺序*

- 当前包下的vendor目录。
- 向上级目录查找，直到找到src下的vendor目录。
- 在**GOPATH**下面查找依赖包。
- 在**GOROOT**目录下查找

3).*安装govendor*

控制台执行	go get -u github.com/kardianos/govendor 

等待执行完毕后进入 %**GOPATH**%/src/github.com/kardianos/govendor,执行

go build

go install

执行完毕后在%**GOPATH**%/bin文件夹下会有 govendor.exe可执行文件。

4).*govendor命令*

| init    | 创建vendor文件夹和 vendor.json 文件                          |
| ------- | ------------------------------------------------------------ |
| list    | 列出已经存在的依赖包                                         |
| add     | 从$GOPATH中添加依赖包，会加到 vendor.json                    |
| update  | 从$GOPATH升级依赖包                                          |
| remove  | 从vendor文件夹删除依赖                                       |
| status  | 列出本地丢失的、过期的和修改的package                        |
| fetch   | 从远程拉取包到vendor下并记录进vendor.json，gopath目录下不会有拉下来的包 |
| sync    | 根据已有的vendor.json里面的依赖包信息。从远程拉取包到vendor目录下 |
| migrate | Move packages from a legacy tool to the vendor folder with metadata. |
| get     | 类似go get目录，拉取依赖包到vendor目录                       |

![img](https://img-blog.csdnimg.cn/20190510181943303.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlbGNvbWU2Ng==,size_16,color_FFFFFF,t_70) 