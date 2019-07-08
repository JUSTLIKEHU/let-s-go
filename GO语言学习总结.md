### GO语言学习总结



###### go build相关知识

win系统下跨平台编译时：

set GOOS= linux	set GOARCG=amd64	set CGO_ENABLED=0



###### go test相关知识

测试文件必须以*_test.go结尾

go test *_test.go		单独执行某个测试文件

go test -v -run TestA *_test.go	指定单元测试用例(指定测试文件中的特定的测试方法)