Git 学习

1.git init  将某个文件夹设置成git仓库

2.git add  xxx   将xxx添加到仓库中(第一步)(提交到暂存区)

3.git commit -m "xxxx" (将暂存区的所有内容提交到分支中)

4.git log (--graph)查看提交日志(视图)

5.git status 查看工作区的文本状态

6.git reset HEAD xxx  取消xxx文件的暂存

7.git branch  查看分支

8.git branch xxx  新建分支xxx

9.git checkout xxx 切换到xxx分支 

10.git merge xxx 将xxx分支与当前分支合并

11.git branch -d xxx  删除分支

12.git checkout -b xxx 创建并切换到xxx分支

13.git stash 将文件暂存（挂起）

14.git stash pop 将暂存的文件恢复



上传文件到github

1.新建一个文件夹

2.在github上新建一个仓库

3.进入到当前文件夹执行 git clone 仓库的URL

4.项目拷贝到当前文件夹

5.提交项目到缓存区

git add -A(提交所有数据到缓存区)

6.将文件提交到分支中

git commit -m "xxxx"

7.将本地仓库中的文件上传到远程仓库中

git push origin master(取决于当前的分支，默认是master分支)