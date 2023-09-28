* TODO 待办事项 [2/4]
"SPC f f"      文件查找
"SPC p f"      项目内文件查找
"SPC b b"      缓冲区（buffer）列表
"SPC p p"      项目列表
    - [ ] 自动对齐注释
    - [ ] 快捷键映射命令
    - [ ] 学习配置文件
    - [ ] toc功能
    - [ ] git 功能
    - [ ] 打开行号功能
    - [X] Emacs 自动换行功能打开
    [2/4] 会显示成 [2/4] 的形式。
    [50%] 会显示成 [50%] 的形式。
    C-c C-c # 标记待办事项
    C-c C-t # 标记 TODO 状态
    windows 文件夹管理

* linux
** 文本编辑
*** emacs
**** emacs安装与配置
***** 安装

    1. [[https://www.gnu.org/software/emacs/emacs.html][点击安装 emacs]]
    2. 配置系统home变量

***** 配置
****** 最开始的配置

    (setq confirm-kill-emacs #'yes-or-no-p)      ; 在关闭 Emacs 前询问是否确认关闭，防止误触
    (electric-pair-mode t)                       ; 自动补全括号
    (add-hook 'prog-mode-hook #'show-paren-mode) ; 编程模式下，光标在括号上时高亮另一个括号
    (column-number-mode t)                       ; 在 Mode line 上显示列号
    (global-auto-revert-mode t)                  ; 当另一程序修改了文件时，让 Emacs 及时刷新 Buffer
    (delete-selection-mode t)                    ; 选中文本后输入文本会替换文本（更符合我们习惯了的其它编辑器的逻辑）
    (setq inhibit-startup-message t)             ; 关闭启动 Emacs 时的欢迎界面
    (setq make-backup-files nil)                 ; 关闭文件自动备份
    (add-hook 'prog-mode-hook #'hs-minor-mode)   ; 编程模式下，可以折叠代码块
    (global-display-line-numbers-mode 1)         ; 在 Window 显示行号
    (tool-bar-mode -1)                           ; （熟练后可选）关闭 Tool bar
    (when (display-graphic-p) (toggle-scroll-bar -1)) ; 图形界面时关闭滚动条

    (savehist-mode 1)                            ; （可选）打开 Buffer 历史记录保存
    (setq display-line-numbers-type 'relative)   ; （可选）显示相对行号
    (add-to-list 'default-frame-alist '(width . 90))  ; （可选）设定启动图形界面时的初始 Frame 宽度（字符数）
    (add-to-list 'default-frame-alist '(height . 55)) ; （可选）设定启动图形界面时的初始 Frame 高度（字符数）

****** 配置生效

    M-x eval-region # 运行选中的这部分代码
    M-x eval-buffer # 执行当前 Buffer 的所有代码

****** 配置快捷键
**** Spacemacs
***** pacemacs 安装

    brew install emacs     # MAC
    // or
    sudo apt install emacs # Linux
    rm -rf ~/.emacs.d .emacs
    git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d emacs

***** 基础操件

    M-m     # 打开命令窗口，空格键不能用时用这个命令
    g       # 跳转
    SPC SPC # 输入命令行
    SPC b h # 打开主页面 buffer
    SPC b b # 打开 buffer 例表
    SPC b n # 打开下一个 buffer
    SPC j j # 跳转到指定字符串
    SPC q q # 退出 Emacs 提示保存
    SPC q Q # 退出 Emacs 不保存
    SPC c t # 注释
-----
五条短线或以上显示为分割线

***** 表格操作

    C-c 竖线	创建或转换成表格
    C-c C-c	调整表格，不移动光标
    TAB	移动到下一区域，必要时新建一行
    S-TAB	移动到上一区域
    RET	移动到下一行，必要时新建一行
    M-RET	(Alt + 回车) 插入同级列表项
    M-S-RET	(Alt + Shift + 回车) 插入有 checkbox 的同级列表项
    M-left/right	(left: <- ; right: ->) 改变列表顶层级关系
    M-up/down	上下移动列表项
    C-c C-c	改变 checkbox 状态
    C-c -	添加水平分割线
    C-c RET	添加水平分割线并跳到下一行
    C-c ^	根据当前列排序，可以选择排序方式

***** 窗口操作

    SPC w / # 垂直分割窗口
    SPC w - # 水平分割窗口
    SPC n   # 快速功换窗口（n代表任意数字）
    SPC w j # 移动光标到下边的窗口
    SPC w k # 移动光标到上边的窗口
    SPC w h # 移动光标到左边的窗口
    SPC w l # 移动光标到右边的窗口
    SPC w d # 关闭当前窗口
    M-0 # 跳转到项目管理窗口
    M-1 # 跳转到第一个窗口

***** Buffer 管理

    SPC TAB # 切换两个 buffer
    SPC b b # 查看当前打开的 buffer
    SPC b d # 关毕当前 buffer
    SPC b n # 下一个 buffer
    SPC b p # 上一个 buffer

***** Magit

    Git 是一个当前非常流行的版本管理程序，Spacemacs 当然也不会少了 Git 的集成。在配置文件中加入 git 的 layer 即可。Spacemacs 内部集成的是一个叫 的扩展，所有跟 Git 相关的操作，都可以在 Spacemacs 中通过 Magit 一次性搞定。下面是一些常用的 Git 命令:
    SPC g i   # 等价于命令 git init
    SPC g s   # 等价于 git status
    SPC g s   # 弹出层选中文件然后按 s, 等价于命令 git add 某个文件
    SPC g S   # 等价于 git add .
    SPC g c c # 等价于 git commit
    SPC g C   # 等价于 git checkout XXX
    SPC g l l # 等价于 git log
    在 commit 时，我们输入完 commit message 之后，需要按 C-c C-c 来完成 commit 操作，也可以按 C-c C-k 来取消 commit。

***** 项目管理

    SPC p t # 打开项目管理页面
    SPC p f # 模糊匹配和查找项目中的文件

**** 目录操作
**** emacs 常用命令

    C-x-c   # 关闭 Emacs
    C-z     # 保留 Emacs
    M-x     # 输入命令
    C-g     # 取消正在编辑的命令
    C-s     # 查找字符串
    C-r     # 光标上、中、下跳转
    M-<     # 移动到文件头
    M->     # 移动到文件尾
    C-x C-j # 可以打开当前文件所在的目录
复制： M-w 复制选中的区域。
移除： C-w 移除选中的区域。
再按 M-y ，就可以得到倒数第二次移除的内容，再按一次 M-y 即可得到倒数第三次移除的内容，以此类推。后面笔者会介绍插件 counsel 辅助这个过程。
**** 移动

    C/M-v  # 下 / 上一页
    C-l    # 当前行居中
    C-b/f  # 前 / 后一个字母
    M-b/f  # 前 / 后一个单词
    C-p/n  # 上 / 下一行
    C-a/e  # 行首 / 尾
    M-a/e  # 句首 / 尾
    M-</>  # 文件首 / 尾

**** 编辑

    C-d            # 删除下一个字符  也可以 C-f 退格，多一个键
    M-退格 /d      # 剪切上 / 下一个词
    C-k            # 剪切这一行  按一次去掉内容，第二次才会去掉换行符
    C-h            # 退格
    C-j            # 换行
    C-u 2 C-k      # 则会完全删掉两行
    M-k            # 剪切这一句
    C-空格 /@      # 高亮选中 受输入法影响，会有 bug，也可以按住 C-shift
    C/M-w          # 剪切 / 复制选中部分
    C-y            # 粘贴 多次 C-k 会被一并粘贴，且可粘贴多次
    M-y            # 将粘贴内容变为上次剪切的给负数可以逆向滚动
    C-//_ 或 C-x u # 撤销 重复按可以撤销多次  按 C-g 会将操作写入历史，可以 redo

**** org-mode
***** todo

    C-c C-t 变换 TODO 的状态
    C-c / t 以树的形式展示所有的 TODO
    C-c C-c 改变 checkbox 状态
    C-c, 设置优先级（方括号里的 ABC）
    M-S-RET 插入同级 TODO 标签
***** 大纲

折叠



快捷键

功能


S-TAB 循环切换整个文档的大纲状态（三种状态：折叠，打开下一级，打开全部） 
TAB 循环切换光标所在大纲的状态 

大纲间移动



快捷键

功能


C-c C-n/p 下/上一标题 
C-c C-f/b 下/上一标题（仅限同级标题） 
C-c C-u 跳到上一级标题 
C-c C-j 切换到大纲浏览状态 

基于大纲的编辑



快捷键

功能


M-RET 插入一个同级标题 
M-S-RET 插入一个同级TODO 标题 
M-LEFT/RIGHT 将当前标题升/降级 
M-S-LEFT/RIGHT 将子树升/降级 
M-S-UP/DOWN 将子树上/下移 
C-c * 将本行设为标题/正文 
C-c C-w 将子树或区域移动到另一标题处（跨缓冲区） 
C-x n s/w 只显示当前子树/返回 
C-c C-x b 在新缓冲区显示当前分支（类似C-x n s) 
C-c / 只列出包含搜索结果的大纲，并高亮，支持多种搜索方式 
C-c C-c 取消高亮 

***** Tags

    C-c C-q 为标题添加标签
    C-c / m 生成带标签的树

***** 标题

    C-b C-f   # 下一个同级标题
    C-b C-b   # 上一个同级标题
    M - Enter # 新建一个目录
    M - Enter # 新建一个目录
    C-c C-^   # 跳转到上级目录
    C-c C-_   # 跳转到下级目录
    C-c C-p   # 移动到上一个标题
    C-c C-n   # 移动到下一个标题
    C-c C-u   # 移动到
***** 列表

    TAB	折叠列表项
    M-RET	插入项
    M-S-RET	插入带复选框的项
    M-S-UP/DOWN	移动列表项
    M-LEFT/RIGHT	升 / 降级列表项，不包括子项
    M-S-LEFT/RIGTH	升 / 降级列表项，包括子项
    C-c C-c	改变复选框状态
    C-c -	更换列表标记（循环切换）

***** org-roam
***** 链接操作

    C-c l          # 保存至 buffer 中，以便后续使用。但是在我的版本中提示没有这个快捷键
    C-c C-l        # 光标处无连接时表示插入链接，要求输入链接内容，光标处有链接时表示修改链接
    C-c C-o        # 光标在链接位置时，表示打开链接
    C-c %	buffer   # 中记忆一个位置
    C-c &	从 C-c % # 的记录中，逐一回溯

***** elisp语言

** 终端
*** oh-my-zsh
*** Tmux
** git
*** windows 安装
**** 安装 TortoiseGit

    安装命令行环境 msysGit
    安装图形客户端 TortoiseGit
    TortoiseGit 依赖于 msysGit，两个软件同要求同时安装，否则 TortoiseGit 不能正常运行

**** 安装 SourceTree
*** 配置

    连接 github

*** 创建密钥，将密钥复制到 github 网站

    ssh-keygen -t rsa -C "chwin@msn.com"

*** 测试连接是否成功

    ssh -T git@github.com

    设置 username 和 email
    因为 github 每次 commit 都会记录他们。因为 Git 是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和 Email 地址。如果有人故意冒充别人也是有办法可查的。
    git config 命令的 --global 参数表示你这台机器上所有的 Git 仓库都会使用这个配置，也可以对某个仓库指定不同的用户名和 Email 地址。
    git config --global user.name "chwin" 设置全局库名称
    git config --global user.email "chwin@msn.com" 设置全局 email
    git push -u origin master                    推送 master 到 origin  -u 只输入一次就自动记录，下次直接推送即可

    配置 github 远程地址
    git remote add origin git@github.com:chwin/chwin.git

*** 远程配置

    git remote add origin                        配置远程地址
    git remote rm origin                         删除远程地址
    git config --global user.name                配置用户名
    git config --global user.email               配置 email 地址

**** 查看状态

    git status                                   检查状态
    git log                                      查看历史记录（详细信息）
    git log --graph                              查看分支合并图。
    git reflog                                   查看命令历史，以便确定要回到未来的哪个版本。
    git config -l                                查看全局配置
    git remote -v                                显示了可以抓取和推送的 origin 的地址。如果没有推送权限，就看不到 push 的地址。

**** 工作区操作

    git init     初始化当前目录为 Git 仓库，创建。git 隐含目录保存进度
    git add aaa.txt                              添加一个新文件到暂存区来跟踪文件变化
    git add '*.txt'                              添加所有。txt 文件到暂存区，加单引号包括子目录内的文件。否则只加当前目录下的文件
    git add .                                    添加当前目录所有文件
    git add *                                    添加所有文件
    git rm --cached aaa.txt                      从暂存区移除一个文件
    git rm aaa.txt                               从仓库移除一个文件

**** 版本操作

    git reset --hard HEAD^                       恢复到上一个版本
    git reset --hard HEAD^^                      恢复到上上个版本
    git reset --hard HEAD20                      恢复到上 20 个版本
    git reset --hard commit_id                   恢复到指定 id 的版本
    git reset HEAD readme.txt                    可以把暂存区的修改撤销掉（unstage），重新放回工作区
    git diff file.txt                            比对修改后的文件
    git diff HEAD -- readme.txt                  查看工作区和版本库里面最新版本的区别
    git diff origin/master
    git checkout -- readme.txt                   回到最近一次 git commit 或 git add 时的状态。其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。

**** 提交操作

    git commit -m "history"                      提交代码并添加注释
    git commit -a                                将所有被修改或者已删除的且已经被 git 管理的文档提交倒仓库中。如果只是修改或者删除了已被 Git 管理的文档，是没必要使用 git add 命令的。
    git remote add origin                        此命令需要一个“远程名称"和"版本库 URL"，try-git 账号  try_git.git 一个仓库
    git remote rm origin
    git push -u origin master                    推送 master 到 origin  -u 只输入一次就自动记录，下次直接推送即可
    git push -f 解决冲突，如远程服务器与本地不一致，以本地为准
    git push -u origin master
    git pull origin master                       拉回 origin 到 master
    git clone git@github.com:chwin/chwin.git     克隆一个版本库

**** 分支操作

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
*** git 流程
** shell



