# git 安装与配置

## windows 安装

    安装命令行环境 msysGit
    安装图形客户端 TortoiseGit
    TortoiseGit 依赖于 msysGit，两个软件同要求同时安装，否则 TortoiseGit 不能正常运行

## 配置

    连接 github

# 创建密钥，将密钥复制到 github 网站

    ssh-keygen -t rsa -C "chwin@msn.com"

# 测试连接是否成功

    ssh -T git@github.com

    设置 username 和 email
    因为 github 每次 commit 都会记录他们。因为 Git 是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和 Email 地址。如果有人故意冒充别人也是有办法可查的。
    git config 命令的 --global 参数表示你这台机器上所有的 Git 仓库都会使用这个配置，也可以对某个仓库指定不同的用户名和 Email 地址。
    git config --global user.name "chwin" 设置全局库名称
    git config --global user.email "chwin@msn.com" 设置全局 email
    git push -u origin master                    推送 master 到 origin  -u 只输入一次就自动记录，下次直接推送即可

    配置 github 远程地址
    git remote add origin git@github.com:chwin/chwin.git

## 远程配置

    git remote add origin                        配置远程地址
    git remote rm origin                         删除远程地址
    git config --global user.name                配置用户名
    git config --global user.email               配置 email 地址

### 查看状态

    git status                                   检查状态
    git log                                      查看历史记录（详细信息）
    git log --graph                              查看分支合并图。
    git reflog                                   查看命令历史，以便确定要回到未来的哪个版本。
    git config -l                                查看全局配置
    git remote -v                                显示了可以抓取和推送的 origin 的地址。如果没有推送权限，就看不到 push 的地址。

### 工作区操作

    git init     初始化当前目录为 Git 仓库，创建。git 隐含目录保存进度
    git add aaa.txt                              添加一个新文件到暂存区来跟踪文件变化
    git add '#.txt'                              添加所有。txt 文件到暂存区，加单引号包括子目录内的文件。否则只加当前目录下的文件
    git add .                                    添加当前目录所有文件
    git add *                                    添加所有文件
    git rm --cached aaa.txt                      从暂存区移除一个文件
    git rm aaa.txt                               从仓库移除一个文件

### 版本操作

    git reset --hard HEAD^                       恢复到上一个版本
    git reset --hard HEAD^^                      恢复到上上个版本
    git reset --hard HEAD20                      恢复到上 20 个版本
    git reset --hard commit_id                   恢复到指定 id 的版本
    git reset HEAD readme.txt                    可以把暂存区的修改撤销掉（unstage），重新放回工作区
    git diff file.txt                            比对修改后的文件
    git diff HEAD -- readme.txt                  查看工作区和版本库里面最新版本的区别
    git diff origin/master
    git checkout -- readme.txt                   回到最近一次 git commit 或 git add 时的状态。其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。

### 提交操作

    git commit -m "history"                      提交代码并添加注释
    git commit -a                                将所有被修改或者已删除的且已经被 git 管理的文档提交倒仓库中。如果只是修改或者删除了已被 Git 管理的文档，是没必要使用 git add 命令的。
    git remote add origin                        此命令需要一个“远程名称"和"版本库 URL"，try-git 账号  try_git.git 一个仓库
    git remote rm origin
    git push -u origin master                    推送 master 到 origin  -u 只输入一次就自动记录，下次直接推送即可
    git push -f 解决冲突，如远程服务器与本地不一致，以本地为准
    git push -u origin master
    git pull origin master                       拉回 origin 到 master
    git clone git@github.com:chwin/chwin.git     克隆一个版本库

### 分支操作

    git branch                                   查看分支
    git branch <name>                            创建分支
    git checkout <name>                          切换分支
    git checkout -b <name>                       创建 + 切换分支
    git merge <name>                             合并某分支到当前分支
    git merge --no-ff -m "merge with no-ff" dev  禁止 fast forward 方式合并
    git branch -d <name>                         删除分支
    git branch -D <name>                         强行删除，丢弃一个没有被合并过的分支
    git stash                                    把当前工作现场“储藏”起来，等以后恢复现场后继续工作
    git stash list                               查看储存列表
    git stash apply                              恢复后，stash 内容并不删除
    git stash drop                               删除
    git stash pop                                恢复的同时把 stash 内容也删了
The end
