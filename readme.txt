Git is a distributed version control system.
Git is free software distributed under the GPL.

git init        //初始化一个库
git add readme.txt  //添加要提交的文件（放进了暂存区）
git commit -m "更新说明"   //可以添加多个文件然后再上传
git status  //查看目前已近改变的文件
git diff readme.txt  //查看修改部分
git log //查看提交日志
git log --pretty=oneline    //查看提交日志在一行
git reset --hard HEAD^      //HEAD指针只会指向当前版本，回退到上一个版本，前一百个版本可以表示为HEAD~100
git reset --hard 版本号     //回退到指定版本
git reflog          //查看之前的命令以及对应的版本
cat readme.txt      //输出文件内容
git diff HEAD -- readme.txt    //查看工作区和缓存区版本区别
git checkout -- readme.txt     //去除文件在工作区的修改，截止至上一次提交到缓存区的版本
                                （其实就是用版本库里面的文件替代工作区的文件）
git reset HEAD readme.txt      //去除已经加入到缓存区域的文件修改
                                再用上一条命令去除工作区修改
git rm test.txt     //从库里面删除文件（需要提交确认后才会真正删除）
git remote add origin git@server-name:path/repo-name.git；   //关联远程仓库
git push origin master     //命令，实际上是把当前分支master推送到远程。
git clone https://github.com/llllrx/gitskills.git       //将远程仓库克隆到本地

git branch dev      //创建dev分支
git git checkout dev    //切换到dev分支
git checkout -b dev     //创建并切换到分支