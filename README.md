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
