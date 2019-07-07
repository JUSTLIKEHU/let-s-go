Linux下安装mysql的步骤

1.删除mysql的数据文件
	sudo rm /var/lib/mysql/ -R

2.删除mysql的配置文件
	sudo rm /etc/mysql/ -R

3.自动卸载mysql（包括server和client）
	sudo apt-get autoremove mysql* --purge 
	sudo apt-get remove apparmor

4.检查是否卸载干净
	dpkg -l | grep mysql # 若没有返回，说明已完成卸载

5.接下来安装就是件简单的事情啦

​	sudo apt-get install mysql-server mysql-client

6.安装完毕后若没有提示密码则按照如下参数设置

​	<https://www.cnblogs.com/cpl9412290130/p/9583868.html> 



