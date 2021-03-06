## 上传至github之前，需要先创建本地仓库
git init
## 将需要上传的文件先添加到仓库的索引中
git add .  所有文件梭哈上传
 git add <filename> 选择文件上传
## 通过diff指令查看未提交（仅添加至索引中）和最后一次提交的区别
git diff
## 提交信息至仓库
git commit "description"
git commit -m "description" 
git commit -a -m "description" （-a提交被修改文件，但新创文件不会被提交）
## 查看仓库现有状态（那些文件被修改或者新建或者被删除）
git status
## 查看分支过往提交史
git log
## 更正最后提交的描述信息
git commit --amend -m "new description"
## 本地删除一个文件后使用git add .无法删除版本控制下的该文件，有以下两种方式删：
1. git add -A . 2. git commit -m "description" or
1. git add . 2.  git commit -a -m "description"
## 关联本地仓库与远程仓库
git remote add origin <repository URL> 其中origin是远程仓库在本地的小名
git remote 可以显示已有的远程仓库
git push origin 上传本地仓库至origin
## 直接拉取一个远程仓库到本地
git clone <repository URL>
## 拉取更改
git pull <repository URL> 拉取仓库的更改内容
## 还原更改
git reset HEAD <filename>从最新版本的commit中复制文件到本地
git revert commit_name 根据版本号还原
## 标记操作
git tag 可以列出所有标记
git tag version1.6 -m 'version 1.6' 创建了一个标记
git checkout commit_name 可以恢复一个标记
## 分支
git branch 列出本地所有分支，带*表示当前使用分支
git branch -a 列出远程仓库分支
git branch <branch_name> 创建一个分支
git checkout <branch_name> 切换到该分支
git branch -d <branch_name> 删除分支
以上分支切换均为本地操作，若clone一个仓库，那么本地分支与远程分支一一对应
## 合并
git merge <branch_name> 合并两个分支，通过最新合并完成，分别来自两个分支的commit和两个分支的公共commit
## 本地分支与远程分支关联
git push origin <branch_name> 默认远程仓库若没有该分支，则需要先上推一次，因为每次push只会推送匹配的分支进入仓库
git pull origin <remote_branch> 拉取一个远程分支到当前分支
git pull origin <remote_branch>:<local_branch> 拉取一个远程分支到本地分支
git pull 直接拉取与当前分支关联的远程分支
注：git pull 自带fetch和merge效果
git checkout -b <local_branch> orgin/<remote_branch> 切换分支时关联远程分支
git push -u orgin <remote_branch> 提交时关联远程分支
git branch -vv 查看分支关联关系
## 其他操作
git config --list 查看已设配置
git config --global usr.email <your_email> 设置邮箱（要与github邮箱匹配，否则push时显示的账号有误）
git config --dlobal usr.name <your_account_name> 同上
 
基本操作：
远程已有仓库，则克隆，修改文件内容后，关联自己的远程仓库，上传

通过git log可以查看提交版本ID，用git checkout commit_name可把版本内容复制到索引和工作副本中

在本地创建的分支（一般不用在本地创建，直接拉取的远程分支）若需要与远程分支关联，则需要先建立关联关系。关联后可以实现pull与push操作
