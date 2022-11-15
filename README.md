# ceshi
创建版本库    git init 在某一个目录下进行
创建文件      touch 文件名
添加文件到仓库   git add 文件名
提交文件到仓库   git commit -m "修改解释内容"
检查是否有未提交的修改  未放入的待提交的修改等    git status
查看历史记录     git log   简显  git log pretty=oneline
回到某一个版本    git reset --hard HEAD^(当前版本)/某一个版本秘钥
读取文件内容     cat 文件名
丢弃工作区修改    git checkout --文件名
暂存区的修改撤销到工作区     git reset HEAD 文件名
移出文件          rm 文件名    若想撤销删除操作  git checkout --文件名   (版本库中存在该文件)  若想把版本库中的文件也删除   git rm 文件名

本地git仓库 远程同步到 GitHub仓库      在本地仓库中 git remote add origin git@github.com:hggaun(github账户名)/ceshi.git
将本地库的内容推送到远程库中(把当前分支master推送到远程)           git push -u origin master     (u参数是第一次推送时 远程库为空)  在以后的推送中直接使用git push -u origin master 将本地修改的内容推送至GitHub上
删除远程库(添加时地址错误/删库) ---- 只是解除本地与远程的绑定关系
    查看远程库信息         git remote -v
    删除远程库            git remote rm origin(远程库名)
克隆远程库
    git clone  远程库的地址  http/ssh
创建分支  
    git checkout -b 分支名      -b表示创建并切换  等同于 git branch 分支名 和 git checkout 分支名  2个命令             git swtich -c dev  
    git checkout -b 分支名 origin/dev    创建远程origin的dev分支到本地
查看分支    
    git branch   当前分支前会标一个 * 号
切换分支
    git checkout 分支名                     git switch 分支名 
合并分支
    当前分支  master
    git merge  dev (分支名)   其代码表示 将dev分支合并到master分支上   在合并之前要将分支切换到 master上
删除分支
    git branch -d dev
分支合并图
    git log --graph
fast forward模式
    禁用fast forward模式 git就就会在merge时生成一个新的commit 就可以在分支历史上看出分支信息
    git merge  --no-ff  -m "commit修饰信息" 分支名
分支合并冲突  
    多个分支都进行提交导致合并冲突   要把合并失败的文件手动编辑为我们希望的内容 再提交
存储当前工作状态
    git stash    
恢复当前工作状态并删除stash
    git stash pop     或者 git stash apply 和 git stash drop 2个命令共同实现
查看工作存放
    git stash list 
将一个提交过程转到另一个分支上进行提交
    git cherry-pick  提交信息
丢弃一个没有被合并过的分支
    git branch -D 分支名   强行删除
 
将分支推送到远程库中
    git push origin 远程库分支(master/dev等)
远程抓取分支
    git pull      若无法抓取则需要建立分支与远程分支的链接   git branch --set-upstream-to=origin/dev dev
    
多人协作
    先试图用git push origin 分支推送自己的修改  若失败则git pull提取最新的提交  在git push  若git pull时出现no tracking information 则建立本地分支与远程分支的链接  
    git branch --set-upstream-to branch-name origin/ branch-name
