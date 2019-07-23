Make: *** No targets.	Stop.

问题分析：无法定位到GOPATH,导致编译无法正常进行。

解决方案

进入/usr/local/app目录下 查看.bashrc  发现gopath路径未正常设置，将路径改成绝对路径后问题得到解决。