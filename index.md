@ -0,0 +1,1071 @@
* TODO 待办事项 [0/13]

    - [ ] emacs org-mode 制作命令模板文件
    - [ ] Zotero # emacs 文献管理
    - [ ] org-roam # 安装双链笔记
    - [ ] 自动对齐注释
    - [ ] 快捷键映射命令
    - [ ] 学习配置文件
    - [ ] toc功能
    - [ ] git 功能
    - [ ] 打开行号功能
    - [ ] Emacs 自动换行功能打开
    - [ ] 对齐第一个非空格emacs
    - [ ] emacs 打开链接用浏览器
    [0/13] 会显示成 [0/13] 的形式。
    [0%] 会显示成 [0%] 的形式。
    C-c C-c # 标记待办事项
    C-c C-t # 标记 TODO 状态
    windows 文件夹管理
* linux
:PROPERTIES:
:collapsed: true
:END:
** 系统命令
*** 文件管理
**** TODO ls

**说明**
    显示文件目录结构
    ll 等同于 ls -l  少数 linux 版本不支持。

**实例**
    ls -ld chwin/      # 查看目录本身，而不是目录里的子目录 -d 不能单独使用，要和其它参数合用
    ls -lh             # 人性化显示容量信息
    ls -lt             # 查看档案信息并以修改时间排序
    ls -Z              # 显示 selinux 属性
    ls -tlr            # 按文件修改时间以列表形式倒序显示
    ls -d */           # 只查看目录
    ls -d .*           # 查看隐藏文件
    ls -l | grep -v ^d # 不显示目录
    ls -l | grep ^-    # 只显示文件
    ls -1              # 参数是阿拉伯数字，以单例形式只显示文件名
    ls -l  # 查看mtime
    ls -lc # 查看ctime
    ls -lu # 查看atime
    ls |grep -v chwin |xargs rm   # 删除chwin以外的所有文件
    ll /etc/init.d/ | wc -l       # 查看有多少个文件和子目录
    ls /etc/ -l |grep '^d' |wc -l # 查看有多少个子目录

    ls -ltr s*
    列出目前工作目录下所有名称是 s 开头的档案，愈新的排愈后面 :

    将 /bin 目录以下所有目录及档案详细资料列出 :

    ls -lR /bin

    列出目前工作目录下所有档案及目录；目录于名称后加 "/", 可执行档于名称后加 "*" :

    ls -AF

**参数**
    | 参数    | 说明                                                           |
    |---------+----------------------------------------------------------------|
    | -l      | 以长格式列出文件，包括文件大小、日期和时间、属性               |
    | -d      | 查看目录本身，而不是目录里的子目录                             |
    | -a      | 显示目录中所有的文件，包括隐藏文件                             |
    | -A      | 同 -a ，但不列出 “.” （当前目录） 及 “..” （父目录）       |
    | -h      | 人性化易读格式。用 k、M、G 等来标识文件大小。必须和 l 连用     |
    | -R      | 递归显示目录及子目录所有文件                                   |
    | -t      | 最后修改时间排序                                               |
    | -S      | 文件大小排序                                                   |
    | -r      | 与一个排序开关组合起来使用，逆序排列。                         |
    | -F      | 文件名追加类型符号                                             |
    | -k      | 显示文件大小以 k 为单位                                        |
    | -i      | 输出文件的 inode 节点信息                                      |
    | -X      | 按文件扩展名排序                                               |
    | -m      | 水平列出文件，以逗号间隔                                       |
    | -F      | 在列出的档案名称后加一符号；例如可执行档则加 "*", 目录则加 "/" |
    | --color | 输出信息中带有着色效果                                         |

    ctime 是在写入文件、更改属主、权限或着链接时随 Inode 的内容更改而变化的；
    mtime 是在写入文件时随文件内容的更改而变化的；
    atime 是在读取文件或者执行文件时变化的。
**** DONE cd

**说明**
  进入目录

**实例**
    cd ..        # 进入上一级目录
    cd ../..     # 进入上两级目录
    cd ../abc    # 进入上一级目录的 abc 子目录
    cd ../../abc # 进入上两级目录的 abc 子目录
    cd ~root     # 进入其它用户主目录
    cd ~         # 进入当前用户主目录
    cd -         # 切换目录

**参数**
    | 参数 | 说明     |
    |------+----------|
    | .    | 当前目录 |
    | ..   | 上层目录 |
    | -    | 切换目录 |
    | ~    | 用户目录 |
**** pwd
**** mkdir
**** touch
**** rm
**** cp
**** mv
**** ln
**** cat
**** more
**** head
**** tail
*** 文档编辑
****
*** 系统管理
**** date
**** cal
**** uptime
**** whoami
**** finger
**** uname
**** cat /proc/cpuinfo - 查看 cpu 信息
**** cat /proc/meminfo - 查看内存信息
**** df
**** du
**** free
*** 磁盘管理
*** 进程管理
**** ps
**** top
**** kill
**** killall
**** bg
**** fg
*** 文件传输
*** 文件权限
**** chmod
*** 压缩备份
**** tar
**** gzip
*** 网络通讯
**** ping
**** whois
**** dig
**** wget
*** 搜索工具
**** grep
**** find
*** 快捷键
**** 快捷键

    Ctrl + c # 停目当前命令
    Ctrl + z # 停目当前命令，并使用 fg 恢复
    Ctrl + d # 注销当前会话，与 exit 相似
    Ctrl + w # 删除当前行的字
    Ctrl + u # 删除整行
    !! # 重复上次的命令
    exit 注销当前会话
*** 软件安装
*** 系统安装
***
***
***
***
** 文本编辑
*** emacs
**** org-mode
***** DONE 大纲
****** 标题移动

    TAB            # 循环切换光标所在大纲的状态
    S-TAB          # 循环切换整个文档的大纲状态
    C-c C-n/p      # 下/上一标题
    C-c C-f/b      # 下/上一标题（仅限同级标题）
    C-c C-u        # 跳到上一级标题
    C-c C-j        # 切换到大纲浏览状态
****** 标题操作

    M-RET          # 插入同级标题
    M-S-RET        # 插入同级 TODO 标题
    M-LEFT/RIGHT   # 将当前标题升/降级
    M-S-LEFT/RIGHT # 将子树升/降级
    M-S-UP/DOWN    # 将子树上/下移
****** 标题操作

    C-c C-t        # 变换 TODO 的状态
    C-c / t        # 以树的形式展示所有的 TODO
    C-c C-c        # 改变 checkbox 状态
    C-c,           # 设置优先级（方括号里的 ABC）
    C-c *          # 将本行设为标题/正文
    C-x n s/w      # 只显示当前子树/返回
    C-c C-x b      # 在新缓冲区显示当前分支（类似C-x n s)
-------------------------------------------------------
    C-c C-w        # 将子树或区域移动到另一标题处（跨缓冲区）
    C-c /          # 只列出包含搜索结果的大纲，并高亮，支持多种搜索方式
***** 格式转换

    pandoc -f markdown -t org -o newfile.org original-file.markdown
    解决方案是将 VoodooPad 文档作为文本导出到文件夹（“ 文件” >“ 导出文档” >“ 导出为文本...”）。然后 pandoc 通过 find 命令调用将它们一次转换：

    find . -name \*.txt -type f -exec pandoc  -f markdown -t org -o {}.org {} \;
    我看过的转换后的.org 文件格式精美，甚至包括代码块和格式样式。谢谢你 user2619203。

    要简单地将一个文件从 Markdown 转换为 Org，可以使用以下命令：

    pandoc -f markdown -t org -o newfile.org original-file.markdown
***** TODO 中文对齐

1 ;; Setting for English font
2 (set-default-font "monospace-15")
3 ;; Setting for Chinese font
4 (dolist (charset '(kana han symbol cjk-misc bopomofo))
5 (set-fontset-font (frame-parameter nil 'font)
6 charset
7 (font-spec :family "WenQuanYi Micro Hei" :size 24)))

(注：这里英文采用 monospace，size 为 15，中文显示采用 WenQuanYi Micro Hei，size 为 24，这是经过博主不断微调 size 才匹配的，假如你用的字体或者 size 不是这个，需要自己进行不断微调后按 C-c C-c 来看表格是否对齐，一般来说先固定一方的 size，然后再不断修正另一方的 size，来查看是否已经对齐)

 设置完后，再回到 org-mode 下的表格，按 C-c C-c，就会对齐
***** DONE 表格

    C-c |     # 建立表格
    C-c C-c   # 对齐表格
    TAB       #	移动到下一区域，必要时新建一行
    S-TAB	    # 移动到上一区域
    M-a       # 移动到当前表格的第一个格，或者移动前到一个格
    M-e       # 光标移动到当前格的尾部或者移到下一格的尾部。
    M-left    #	向左移动当前列，如果快捷键效果不对，可以使用前面的命令
    M-right   # 向右移动当前列，如果快捷键效果不对，可以使用前面的命令
    M-S-left	# 删除光标所在列。如果快捷键效果不对，可使用前面命令
    M-S-rigth	#	在光标所在位置插入一列，如果快捷键效果不对，可使用命令
    C-c -	    # 添加水平分割线
    C-c RET	  # 添加水平分割线并跳到下一行
    C-c ^     # 当前列排序，可以选择排序方式
***** TODO 注释
****** 文本注释

# this is a comment

#+BEGIN_COMMENT
    this is a comment
#+END_COMMENT
****** 代码注释
***** DONE 字体

    *粗体*
    /斜体/
    +删除线+
    _下划线_
    下标： H_2 O(这里必须留一个空格要不然2和O都成为小标，目前还不知道怎么去掉空格)
    上标： E=mc^2
    等宽字：  =git=
***** TODO 列表

    无序列表
    +
    -
    *
    有序列表
    1.
    1)

    TAB	折叠列表项
    M-RET	插入项
    M-S-RET	插入带复选框的项
    M-S-UP/DOWN	移动列表项
    M-LEFT/RIGHT	升 / 降级列表项，不包括子项
    M-S-LEFT/RIGTH	升 / 降级列表项，包括子项
    C-c C-c	改变复选框状态
    C-c -	更换列表标记（循环切换）
***** DONE Tags

    C-c C-q # 为标题添加标签
    C-c / m # 生成带标签的树
    C-c \   # 生成带标签的树
***** TODO 时间管理

      任务与子任务
      ===================
      * 一个一级标题对应的就是一个任务
      * 一个二级标题对应的是一级标题的子任务
      * 三级标题，四级标题分别是二级标题，三级标题的子任务；依次类推

      任务状态 --TODO,DONE
      ===================
      在标题前直接加上任务状态
      C-c C-t 可以在 TODO,DONE, 无 三种状态之间切换

      情景模式 --TAG 标签 :tag:
      =======================
      在标题后面用 :tag: 标注任务的情景
      C-c C-q 可以编辑 TAG

      规划，记录与分析时间
      =======================

      规划时间
      ~~~~~~~~~~~~~~~
      C-c C-s 规划日程
      C-c C-s 设置期限

      记录时间
      ~~~~~~~~~~~~~~~
      C-c C-x c-i 开始计时
      C-c C-x C-o 结束计时
      C-c C-x C-x 取消计时

      分析时间
      C-c C-x C-r 创建今日的时间统计表格
      C-c a agenda view
      R 创建时间统计表格

      导出
      =========
        * C-c C-e
***** TODO org-roam
***** DONE 链接操作

    C-c l          # 保存至 buffer 中，以便后续使用。但是在我的版本中提示没有这个快捷键
    C-c C-l        # 光标处无连接时表示插入链接，要求输入链接内容，光标处有链接时表示修改链接
    C-c C-o        # 光标在链接位置时，表示打开链接
    C-c %	buffer   # 中记忆一个位置
    C-c &	从 C-c % # 的记录中，逐一回溯
**** emacs 安装与配置
***** 安装

    1. [[https://www.gnu.org/software/emacs/emacs.html][点击安装 emacs]]
    2. 配置系统home变量
***** 配置
****** 最开始的配置

    (setq make-backup-files nil)                 ; 关闭文件自动备份
    (column-number-mode t)                       ; 在 Mode line 上显示列号
    (global-auto-revert-mode t)                  ; 当另一程序修改了文件时，让 Emacs 及时刷新 Buffer
    (global-display-line-numbers-mode 1)         ; 在 Window 显示行号
    (setq display-line-numbers-type 'relative)   ; 显示相对行号

    (setq confirm-kill-emacs #'yes-or-no-p)      ; 在关闭 Emacs 前询问是否确认关闭，防止误触
    (electric-pair-mode t)                       ; 自动补全括号
    (add-hook 'prog-mode-hook #'show-paren-mode) ; 编程模式下，光标在括号上时高亮另一个括号
    (delete-selection-mode t)                    ; 选中文本后输入文本会替换文本（更符合我们习惯了的其它编辑器的逻辑）
    (setq inhibit-startup-message t)             ; 关闭启动 Emacs 时的欢迎界面
    (add-hook 'prog-mode-hook #'hs-minor-mode)   ; 编程模式下，可以折叠代码块
    (tool-bar-mode -1)                           ; （熟练后可选）关闭 Tool bar
    (when (display-graphic-p) (toggle-scroll-bar -1)) ; 图形界面时关闭滚动条

    (savehist-mode 1)                            ; （可选）打开 Buffer 历史记录保存
    (add-to-list 'default-frame-alist '(width . 90))  ; （可选）设定启动图形界面时的初始 Frame 宽度（字符数）
    (add-to-list 'default-frame-alist '(height . 55)) ; （可选）设定启动图形界面时的初始 Frame 高度（字符数）
****** 配置生效

    M-x eval-region # 运行选中的这部分代码
    M-x eval-buffer # 执行当前 Buffer 的所有代码
****** 配置快捷键
**** emacs 常用命令

    M-x     # 输入命令
    C-g     # 取消正在编辑的命令
    C-x C-j # 可以打开当前文件所在的目录
    M-q     # 合并行
    M-t     # 交换两个单词位置
    ---------------------------------
    C-s     # 查找字符串
    C-r     # 光标上、中、下跳转
    C-x-c   # 关闭 Emacs
    C-z     # 保留 Emacs
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
***** 基础编辑

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
***** evil-mc 多光标修改

首先需要进入 visual 模式，然后使用 C-n 进行选择，然后修改，然后 grq 退出功能。

常用的快捷键如下：

    C-n # 标记当前，找下一个匹配值
    C-p # 标记肖前，找上一个匹配值
    M-n # 在已经标记的光标中向后跳转
    M-p # 在已经标记的光标中向前跳转
    C-t # 跳过这个，找下一个相同的内容（同 grn）
    grn # 跳过这个，向后找下一个相同的内容
    grp # 跳过这个，向前找下一个相同的内容
    grf # 跳到标记的第一个
    grl # 跳到标记的最后一个。
    grj # 标记这个位置的的下一行的同一位置
    grk # 是标记上一行的相同位置。
    grs # 暂停光标移动
    grr # 恢复光标移动。
    gru # 撤消最后添加的游标
    grq # 删除所有游标

*实验*
    abc 123 abc 123 abc 123 abc 123 abc 123
    abc 123 abc 123 abc 123 abc 123 abc 123
    abc 123 abc 123 abc 123 abc 123 abc 123
    abc 123 abc 123 abc 123 abc 123 abc 123
**** TODO 目录操作
**** 文档元素

    C-c C-e t # 插入选项
**** Spacemacs
***** pacemacs 安装

    brew install emacs     # MAC
    // or
    sudo apt install emacs # Linux
    rm -rf ~/.emacs.d .emacs
    git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d emacs
***** TODO 基础操件

    g       # 跳转
    z       # 
    SPC f f # 文件查找
    SPC p f # 项目内文件查找
    SPC b b # 缓冲区（buffer）列表
    SPC p p # 项目列表
    SPC SPC # 输入命令行
    SPC b h # 打开主页面 buffer
    SPC b b # 打开 buffer 例表
    SPC b n # 打开下一个 buffer
    SPC j j # 跳转到指定字符串
    SPC q q # 退出 Emacs 提示保存
    SPC q Q # 退出 Emacs 不保存
    SPC c t # 注释
    M-m     # 打开命令窗口，空格键不能用时用这个命令
***** 窗口操作

    SPC w / # 垂直分割窗口
    SPC w - # 水平分割窗口
    SPC n   # 快速功换窗口（n代表任意数字）
    SPC w j # 移动光标到下边的窗口
    SPC w k # 移动光标到上边的窗口
    SPC w h # 移动光标到左边的窗口
    SPC w l # 移动光标到右边的窗口
    SPC w d # 关闭当前窗口
    M-0     # 跳转到项目管理窗口
    M-1     # 跳转到第一个窗口
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
**** elisp语言
*** vim
**** DONE 使用技巧

    C-[     # 可以代替 esc
**** DONE 移动
***** 上、下、左、右

    k # 上
    j # 下
    h # 左
    l # 右
***** 行内移动

    w  # 跳转到下一个单词的开头
    e  # 跳转到下一个单词的结尾
    b  # 跳转到上一个单词的开头
    fx # 往右移动到 x 字符上
    Fx # 往左移动到 x 字符上
    tx # 往右移动到 x 字符前
    Tx # 往左移动到 x 字符后
    ;  # 配合 f 和 t 使用，重复一次
    ,  # 配合 f 和 t 使用，反方向重复一次
    ^  # 跳转到当前行的第一个非空字符（空格 /tab)
    $  # 跳转到当前行的末尾
    0  # 跳转到当前行首
***** 行数移动

    gg    # 跳转到文件第一行 (goto)
    G     # 跳转到文件最后一行
    -     # 移动到上一行首
    enter # 移动到下一行首
***** 文本块移动

    %	  # 括号匹配及切换
    ``  # 来回跳转
    `.  # 跳到最后修改点
    g;  # 跳到上一次修改点
    g,  # 跳到下一次修改点
    `   # 跳转到某标签的光标位置
    '   # 跳转到某标签的行首
    ma  # 在当前光标位置设置标签 a 标记
    `a  # 跳转到 a 标记
    C-o # 跳回上一次的 jump
    C-i # 跳回下一次的 jump
    C-] # 跟着 link/tag 转入 (follow link/tag)
    (   # 跳转到上一个句子的开头
    )   # 跳转到下一个句子的开头
    {   # 跳转到上一个段落的开头
    }   # 跳转到下一个段落的开头

    以上句字和段落操作可用于删除，例如 d + ( 可删除一句话
    同时也可以用 v 键选取一个句字或一个段落
***** 屏幕移动

    C-f # 往前滚动一整屏 forward
    C-b # 往后滚动一整屏 back
    C-d # 往前滚动半屏 down
    C-u # 往后滚动半屏 up
    C-y # 往前滚动一行
    C-e # 往后滚动一行
    H   # 跳转到屏幕的顶部 (head)
    M   # 跳转到屏幕的中间 (middle)
    L   # 跳转到屏幕的底部 (low)
    zt  # 将当前行滚动至屏幕顶部 (top)
    zz  # 将当前行滚动至屏幕中间（同'z.')
    zb  # 将当前行滚动至屏幕底部 (bottom)（同'z-')
**** DONE 插入

    i   # 在光标位置前进入插入模式
    I   # 在当前行的第一个非空字符进入插入模式
    a   # 在光标位置后进入插入模式
    A   # 在当前行的末尾进入插入模式
    o   # 在当前行的下一行添加一个空行进入插入模式
    O   # 在当前行的上一行添加一个空行进入插入模式
    C-w # 删除光标前的一个单词（插入模式）
    C-u # 从光标位置删除到行首（插入模式）
    C-y # 复制上一行内容（插入模式）
    C-e # 复制下一行内容（插入模式）
    C-n # 使用关键词自动完成（插入模式）
    C-p # 使用关键词自动完成（插入模式）

    *连续插入*
    例如：********** 连续 10 个星号
    要实现这个效果可以在 命令模式 下

    输入 10，表示要重复 10 次
    输入 i 进入 编辑模式
    输入 * 也就是重复的文字
    按下 ESC 返回到 命令模式，返回之后 vi 就会把第 2、3 两步的操作重复 10 次
**** DONE 删除

    x       # 向后删除一个字符 （相当于 [del] 按键）
    xp      # 交换两个字符位置
    X       # 向前删除一个字符（相当于 [backspace] 亦即是退格键）
    d       # 删除
    ddp     # 交换行
    D       # 删除光标位置到行尾（等同于 d$)
    d/chwin # 配合使用查找 / 删除到 chwin 处
    dd      # 删除当前行
    dj      # 向下删一行
    dk      # 向上删一行
    dgg     # 删除光标所在到第一行的所有数据
    dG      # 删除光标所在到最后一行的所有数据
    dw      # 删当前字符到单词尾（包括空格） 3dw  (delete word)
    de      # 删当前字符到单词尾（不包括空格） 3de
    db      # 删除到某个单词的开始位置
    d2fa    # 删除光标到第二个字母 a
    d/chwin # 配合使用查找 / 删除到 chwin 处
    dtc     # 删除当前行直到下一个字符"c"所出现位置之间的内容
    :5,10d  # 删除 5-10 行
    d0      # 删除到行首
    d^      # 删除到行的第一个非空字符（空格 /tab)
    d)      # 删除从光标位置到下一个句子的开始
    d}      # 删除从光标位置到该段落的末尾
    diw     # 删除一个单词
    di{     # 删除花括号之间的内容 (delete inner {})（同'dib')
    di(     # 删除小括号之间的内容 (delete inner ())（同'dib')
    dit     # 删除闭合标签之间的内容 (html/xml 等标签，delete inner tag)
    dat     # 删除左右尖括号及之间的内容 (delete a tag)
    da<     # 删除左右尖括号及之间的内容 (delete a <>)
    di"     # 删除引号之间的内容 (delete inner "")
    da"     # 删除左右引号及之间的内容 (delete a "")
    daw     # 删除一个单词 (delete a word)
    d}      # 从光标位置删除到段落结尾
    ndd     # 从光标位置向下连续删除 n 行
    d代码行G # 从光标所在行 删除到 指定代码行 之间的所有代码
    d'a     # 从光标所在行 删除到 标记a 之间的所有代码
**** DONE 修改

    s        # 删除当前字符进入插入模式
    S        # 删除当前行进入插入模式
    r        # 替换单个字符
    R        # 替换多个字符
    c        # 修改选中区域里的文本
    C        # 修改光标到行尾
    cc       # 修改整行
    cl       # 修改当前字符
    cf[char] # 修改光标位置到 [char]
    ct[char] # 修改光标位置到 [char] 前
    ce       # 删除光标之后的一个单词
    cw       # 修改到某个以空格作为分隔符的单词的结尾位置
    cb       # 修改到某个单词的开始位置
    cb       # 修改到某个以空格作为分隔符的单词的开始位置
    c0       # 修改到行首
    c^       # 修改到行首非空格位置
    c)       # 修改到某个语句的结尾位置
    c(       # 修改到某个语句的开始位置
    c}       # 修改到某个段落的结尾位置
    c{       # 修改到某个段落的开始位置
***** DONE 行操作

    C-j  # 加入新行
    J    # 合并行
    5J   # 合并 5 行
    3,9J # 合并 3-9 行
***** 大小写转换

    ~    # 切换光标下字符的大小写
    v ~  # 切换选定的文本大小写（可视模式）
    u    # 更改选定的文本为小写（可视模式）
    U    # 更改选定的文本为大写（可视模式）
    guw  # 将光标所在的单词变为小写
    gUw  # 将光标所在的单词变为大写
    guu  # 光标所在的行所有字符变为小写
    gUU  # 光标所在的行所有字符变为大写
    g~~  # 光标所在的行所有字符大小写反向转换
**** DONE 撤销，重复
***** 撤销

    u            # 撤销 (undo)
    U            # 行撤销，撤销所有在前一个编辑行上的操作
    C-r          # 重做
    3 C-r        # 重做 3 次
    3 u          # 撤销 3 次
    .            # 重复最后一个命令
    22.          # 重复最后一个命令 22 次
    :undolist    # 查看撤消分支
    :undo        # 命令并指定编号做为参数，则能够撤销到某个分支。
    g-           # 返回较早的文本状态
    g+           # 返回较新的文本状态
    :earlier 10m # 命令退回到 10 分钟前的文本状态。
    :later 5s    # 命令跳转到 5 秒以后的编辑状态。命令参数中的"s"代表秒，"m"代表分钟，"h"代表小时。
***** 录制命令

    qq  # 录制到 q
    ..  # 输入一系列复杂的指令
    q   # 再次按 q 停止录制
    @q  # 执行 q 中存储的指令
    @@  # 重复执行
    5@q # 表示重复执行宏 q 5 次
**** DONE 复制，粘贴

    y       # 抽出选择的文本到寄存器
    yy      # 复制当前行
    y$      # 复制光标位置到行尾
    y^      # 复制光标位置到行首
    yw      # 复制光标之后的单词剩余部分 (yank word)
    yb      # 复制光标之前的单词剩余部分
    yiw     # 复制一个单词
    yip     # 复制当前段落 (yank inner paragraph)
    yas     # 复制一个句子 (yank a sentence)
    yi<     # 复制尖括号之间的内容 (yank inner <>)
    p       # 将剪贴板中的内容粘贴在光标后（小写 p)
    P       # 将剪贴板中的内容粘贴在光标前（大写 p)
    yfa     # 表示拷贝从当前光标到光标后面的第一个 a 字符之间的内容。
    y2fa    # 表示拷贝从当前光标到光标后面的第二个 a 字符之间的内容。
    "ayy    # 复制当前行到寄存器'a'（可使用范围'a-z')
    "ap     # 粘贴从寄存器'a'
    "2p     # 粘贴 2 次
    :12,24y # 表示拷贝第 12 行到第 24 行之间的内容。
    :12,y   # 表示拷贝第 12 行到光标所在行之间的内容。
    :,24y   # 表示拷贝光标所在行到第 24 行之间的内容。删除类似。
    <C-r>"  # 粘贴（插入模式）

    寄存器
    :reg   # 查看所有寄存器中的内容
    ""     # 无名寄存器，最近一次删除 / 修改 / 替换操作的文本都会放入这个寄存器
    0-9    # 10 个数字寄存器，拷贝或者删除的文本存入这些寄存器，这些寄存器是循环使用的，在每次存入内容到寄存器 1 时，原有的内容会依次存入到后一个寄存器中。
    -      # 小删除寄存器，删除内容少于一行时放入这个寄存器。
    a-za-z # 26 个命名寄存器，大小写无关。这些寄存器可以在拷贝或者删除等操作中指定使用。
    :.%    # # 四个只读寄存器
    =      # 表达式寄存器
    /# +~  # 选择和拖放寄存器，用于与系统剪切板交互，以及接收拖放操作的内容。
    _      # 黑洞寄存器，放到这里面的内容都被丢弃，这样可以删除或拷贝时不影响其它寄存器。
    /      # 最后一次搜索模式寄存器，保存最后一次搜索的正则表达式。
**** DONE 缩进，对齐
***** 缩进

    >>        # 缩进当前行
    <<        # 向左缩进当前行
    >         # 向右缩进选定的行（可视模式）
    <         # 向左缩进选定的行（可视模式）
    >}        # 向右缩进光标处到段落尾部
    >G        # 缩进到文件尾部
    >gg       # 缩进到文件顶部
    5>>       # 向下缩进 5 行
    5>k       # 向上缩进 5 行
    :3,9>>>>> # 将 3-9 行缩进 5 个 tab
    :12,24>   # 将 12 行到 14 行向右移动一个 tab
    :12,24>>  # 将 12 行到 14 行的数据都向右移动两个 tab
    :5,10>>   # 第 5-10 行向右缩进两个 tab
    :5,10<    # 第 5-10 行向左缩进一个 tab
    >i{       # 缩进花括号之间的内容 (indent inner {})（同'>ib')
    >a{       # 缩进花括号及之间的内容 (indent a {})（同'>ab')
***** 对齐

    v         # （进入 visual 模式），选中部分行，然后按＝对齐到左边界
    =G        # 当前行到文件尾部对齐到左边界
    =5        # 向下 5 行对齐到左边界
    gg=G      # 全文对齐 / 格式化
    =}        # 对齐当前段落
**** TODO 查找，替换

    + 查找
      /[word]           # 向下搜索 [word] 字符串
      ?[word]           # 向上搜索 [word] 字符串
      n                 # 跳转到下一个匹配的字符串（相对于搜索命令的方向）
      N                 # 跳转到上一个匹配的字符串（相对于搜索命令的方向）
      /#                # 向前搜索光标所在单词
      /*                # 向后搜索光标所在单词

    + 替换
      * 局部替换
        :s/old/new        # 只替换当前行第一个匹配的字符串
        :s/old/new/g      # 替换当前行或选中行所有字符串
        :s/old/new/gc     # 替换前确认
        :13,18s/old/new/g # 替换 13 到 18 行的内容

      * 全局替换
        :%s/old/new/g      # 替换当前文件所有行
        :%s/old/new/gc     # 替换当前文件所有行（替换前确认）

      * 可视区域替换
        先选中要替换文字的范围
        :s/old/new/g

      * 确认替换
        如果把末尾的 g 改成 gc 在替换的时候，会有提示！推荐使用！
        :%s/旧文本/新文本/gc
        y - yes 替换
        n - no 不替换
        a - all 替换所有
        q - quit 退出替换
        l - last 最后一个，并把光标移动到行首
        ^E 向下滚屏
        ^Y 向上滚屏

------------------------------------------------------------------

    :%s/\s\+$#   去除行尾空白字符 ('\s'表示空白字符'空格 /tab'，'\+'表示一个或多个）
    :3s/w1/r2/g   将第 3 行到文件末尾所有的'w1'替换为'r2'
    :s/old/new/c       当前行 old 替换成 new ， 只替换当前行第一个匹配的字符串
    :s/old/new/gc      替换当前行所有
    :13,18s/old/new/gc 替换 13 到 18 行的内容
    :%s/old/new/gc     替换当前文件所有行前确认
    :g/hello/d         删除含有 hello 的行
    :g!/hello/d        删除不含 hello 的行
    :v/hello/d         与 :g! 同

    :%s/^\n#g         删除空行
    :%s/^ ##g         删除行首的空格
    :%s/ #$#g         删除行尾的空格
    :%s/^\n\{3}#      可以用以下命令删除三行空行：
    :%s/\n\n/\r/g      可以用以下命令将连续的两个空行替换成一个空行
    :0,$s/^/#/gc       在行首加一个#号
    :6,10s/^/#/gc      在 6~10 行的行首加一个#号
    :%s= #$==          将所有行尾多余的空格删除
    :g/^s#$/d          将所有不包含字符（空格也不包含）的空行删除。
    :s# 和：g#，:!g#
    这两个命名加上正则表达式，常常能完成非常复杂的编辑任务，可以毫不夸张地说是 vim 的两柄瑞士军刀。:s 是替换操作，:g 是查找匹配模式的行，:!g 是查找不匹配模式的行。
**** TODO 窗口操作
***** 命令行窗口

    q:         # 正常模式下输入 q: 打开命令行窗口查看、执行输入过的命令。编辑新的命令或修改旧的命令。可以拷贝粘贴。
    :%s/ C-f p # 假定要将 123 替换成 456，现 yw 复制 123，然后在底行输入 :%s/ 这个时候输入 C-f, 会在当前窗口下面
                 出现一个小窗口用来编辑命令。在这个新窗口用 p 将 123 粘贴过来就可以了。剩下的命令要直接在这个新窗口完成。
    :C-r       # 命令窗口下粘贴。先在普通模式下用 y 复制。到命令行模式下 ctrl-r 然后“进行粘贴，可重复多次粘贴
    C-cc       # 关闭命令行窗口
***** DONE 新建窗口

    C-w n      # 新建一个缓冲区
    C-w v      # 左右切割窗口新建缓冲区
    C-w s      # 上下切割窗口新建缓冲区
    :sp        # 水平分割当前窗口 (split)
    :sp [file] # 水平分割一个新窗口，并编辑文件 [file]
    :vs        # 垂直分割当前窗口 (vertical split)
    :vs [file] # 垂直分割一个新窗口，并编辑文件 [file]
    :only      # 关闭其他窗口
***** DONE 关闭窗口

    C-w c  # 关闭当前窗口，与 q 的区别是不能退出最后一个窗口
    C-w q  # 退出当前窗口，如果剩最后一个窗口，则退出 vim
    C-w o  # 使光标所在缓冲区最大化，其他缓冲区隐藏，再次使用则恢复恢原貌
***** DONE 移动窗口

    C-w w   # 所有窗口循环移动
    C-w l   # 光标移到右边窗口
    C-w h   # 光标移到左边窗口
    C-w k   # 光标移到上边窗口
    C-w j   # 光标移到下边窗口
    C-w L   # 窗口移动到最右边
    C-w H   # 窗口移动到最左边
    C-w K   # 窗口移动到最上边
    C-w J   # 窗口移动到最下边
    C-w p   # 移动到前一个访问的窗口
    C-w r   # 向右或向下方交换窗口
    C-w R   # 向左或向上方交换窗口
    C-w x   # 交换同列或同行的窗口
    C-w t   # 移动到最左上角的窗口
    C-w b   # 移动到最右下角的窗口
***** DONE 调整窗口大小

    分屏窗口都是基于 CTRL + W 这个快捷键的，w 对应的英文单词是 window
    调整窗口宽高的命令可以和数字连用，例如：5 CTRL + W + 连续 5 次增加高度
    C-w +  # 增加窗口高度
    C-w -  # 减少窗口高度
    C-w >  # 增加窗口宽度
    C-w <  # 减少窗口宽度
    C-w =  # 等分窗口大小
    C-w |  # 最大宽度
    C-w 1  # 最小宽度
***** 分割窗口模式打开文件

    vim  -o5 /a /b # 将分配 5 个相同的窗口，有 3 个是闲置的
    vim -o2        # 垂直分两个屏
    vim -o /a /b   # 垂直分屏打开两个文件
    vim -o /a /b   # 水平打开现个文件
    vim -d /a /b   # 垂直 diff 两个文件
    vim -do /a /b  # 垂直分屏比较两个文件
***** 多文件操作

    vim 1.txt 2.txt 3.txt 同时打开多个文档
    :args 查看多文件状态，可以简写成 ar
    :next 切换下一个文件
    :prev 切换上一个
    :next! 切换下一个文件，并强制丢弃修改
    :prev! 切换上一个文件，并强制丢弃修改
    :first 首文件
    :last 尾文件
    C-^ 切换两个其它切换命令切换后的两个文件
***** TODO 标签操作

    :tabnew        # 标签命令 gt gt 进行标签切换
**** DONE 折叠

    zo  # 打开光标下的折叠 (open)
    zc  # 关闭光标下的折叠 (close)
    zr  # 打开所有的折叠
    zm  # 关闭所有的折叠
**** TODO 保存退出
:e .	edit	会打开内置的文件浏览器，浏览要当前目录下的文件
:n 文件名	new	新建文件
:w 文件名	write	另存为，但是仍然编辑当前文件，并不会切换文件
    :w              # 保存文件
    :w!             # 文件属性为『只读』时，强制写入该档案。不过，到底能不能写入， 还是跟你对该档案的权限有关
    :wa             # 保存所有文件
    :wq             # 强制性写入文件并退出。即使文件没有被修改也强制写入，并更新文件的修改时间。
    :wq!            # 强制保存文件并退出 vi
    :wqa            # 保存退出所有窗口
    :wqa!           # 强制保存退出所有窗口
    :q              # 不保存退出
    :q!             # 不保存强制退出
    :qa             # 退出所有窗口
    :qa!            # 强制退出所有文件
    :x              # 写入文件并退出。仅当文件被修改时才写入，并更新文件修改时间，否则不会更新文件修改时间。
    :X              # 保存并退出，同时清除加密信息
    ZZ              # 保存当前文件，然后退出！效果等同于 :wq
    ZQ              # 不保存，强制退出。效果等同于 :q!
    :w [file]       # 另存为 file 文件，不退出 vi
    :w! [file]      # 强制另存覆盖已有文件
    :e [file]       # 打开另一个文件
    :pwd            # 输出当前工作目录到状态栏
    :cd [dir]       # 切换当前工作目录到 [dir]
    :w > [file]     # 将当前文件内容写入 [file] 文件（文件不存在，同':saveas')
    :e [dir]        # 打开一个目录，以例表的形式展示文件 (vim7.0 后续版本 netrw.vim 插件来实现）
    :e!             # 重新载入当前文件，放弃所有的修改，从上次保存文件开始再编辑
    :e! [file]      # 不保存当前的文件，强制打开新文件
    :r [file]       # 读入另一个文件，将 [file] 文件内容插入到下一行 (read)
    :r !command     # 读取 shell 命令输出结果
    :3,9w >> [file] # 将 3-9 行的内容追加到 [file] 文件末尾（文件已存在）
    :n,mw [file]    # 将第 n-m 行的文本保存到指定的文件 filename 中。
    :m,nw >> <file> # 将 m 行到 n 行的内容添加到文件 <file> 的末尾
**** DONE 块操作

    v   # 进入可视模式，以字符为单位选择
    V   # 进入可视模式，以行为单位选择
    C-v # 进入列块可视模式
    gv  # 重新选择最后选定的区域
    v(  # 选中一个句字
    v{  # 选中一个段落

  **块替换**

    源始状态：
    chwin ch
    chwin ch
    chwin ch
    ctrl-v 进入块选择模式，只选择 chwin 部分，按 c/d/r 键后输入要批量更改的字符串，然后按 esc 键批量更改如下：
    win ch
    win ch
    win ch
    win ch
**** TODO 缓冲区

    :ls             查看缓冲区列表
    :bn             编辑下一个缓冲区 (buffer next)
    :bp             编辑上一个缓冲区 (buffer previous)
    :b[n]           编辑缓冲区列表中第 [n] 个缓冲区
    :b a.txt        编辑缓冲区列表中 a.txt 缓冲区
    :bd             卸载当前缓冲区 (buffer delete)
    :bn             跳转到下一个 buffer
    :bp             跳转到上一个 buffer
    :wn             存盘当前文件并跳转到下一个（又是“超级……”,ft!)
    :wp             存盘当前文件并跳转到上一个
    :bd             把这个文件从 buffer 列表中做掉
    :bun            卸掉 buffer （关闭这个 buffer 的窗口但是不把它从列表中做掉）
    :badd file.c    把文件 file.c 添加到 buffer 列表
    :b 3            跳到第 3 个 buffer
    :b main         跳到一个名字中包含 main 的 buffer, 例如 main.c               : (ultra，这个怎么翻译？:()
    :sav php.html   把当前文件存为 php.html 并打开 php.html
    :sav! %<.bak    换一个后缀保存
**** DONE 常用命令

    set nu   # 打开行号
    set rnu  # 打开相对行号
    set nonu # 关闭行号
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
* windows
:PROPERTIES:
:collapsed: true
:END:
** 软件安装列表
*** 办公软件

    1. qq 五笔
    2. wps
    3. 有道词典
*** 网络工具

    1. 微信
    2. 迅雷
    3. 百度网盘
    4. RaiDrive
    5.
*** 程序开发

    1. emacs
    2. git
    3. Sourcetree
    4. Cygwin64
    5. python
* mac
** 去 fs
* 检测监控