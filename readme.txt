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
git push origin 分支名     //将分支推送到远程。
git clone https://github.com/llllrx/gitskills.git       //将远程仓库克隆到本地

git branch dev      //创建dev分支
git git checkout dev    //切换到dev分支
git checkout -b dev     //创建并切换到分支
git merge dev           //合并dev分支到当前分支
git branch -d dev       //删除分支dev，当使用-D的时候，能强制删除
git merge --no-ff -m "merge with no-ff" dev     //合并分支，禁用Fast Forward
git stash           //将工作现场在不用提交保存的情况下，保存起来
git stash list          //查看保存的工作现场列表
git stash apply         //恢复之前的工作内容
git stash drop          //删除列表里面的保存的现场
git stash pop           //恢复工作现场，并且删除保存的内容
git tag -d v0.1         //删除标签

git tag <name>就可以打一个新标签，后面可加版本号，指定某一次提交的标签
git tag 可以查看所有标签

因此，多人协作的工作模式通常是这样：

首先，可以试图用git push origin <branch-name>推送自己的修改；

如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；

如果合并有冲突，则解决冲突，并在本地提交；

没有冲突或者解决掉冲突后，再用git push origin <branch-name>推送就能成功！

如果git pull提示no tracking information，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream-to <branch-name> origin/<branch-name>。

这就是多人协作的工作模式，一旦熟悉了，就非常简单。


Creating a new branch is quick and simple.