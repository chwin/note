# find 命令 - 查找文件

## 说明

## 实例

```bash
    find .  -type f  -name *.log  -mtime +180  -exec rm {} \; # 删除 180 天之前的 log 文件
    find . -iname "*.jpg" -o -iname "*.png" -o -iname "*.gif" # 搜索多个类型的文件
    find . -name "file???"
    find . -iname "file"                 # 不区分大小写
    find / -mtime -3                     # 查找 3 天内被修改过的文件
    find / -mtime +4                     # 查找 4 天前被修改过的文件
    find / -mtime 2                      # 查找 2 天前被修改过的文件
    find ./ -size +10M                   # 查找大于 10M 的文件
    find ./ -type f                      # 查找所有普通文件
    find ./ -user tom                    # 查找所属用户 tom 的文件
    find ./ -size +1M -exec ls -l {} \;  # 查出大于 1M 文件后列出文件详细信息
    find ./ -size +1M -a -type f         # 查找所有大于 1M 的文件
    find /home -amin -10                 # 十分钟内存取的文件或目录
    find /home -atime -10                # 十小时内存取的文件或目录
    find /home -cmin -10                 # 十分钟内更改过的文件或目录
    find /home -ctime +10                # 十小时前更改过的文件或目录
    find /home -size +10k                # 大小 10K
    find / -name filename                # 从根目录开始查所有目录
    find / -name "*name*"
    find / -empty                        # 查找计算机上的所有空文件
    find / -group tom                    # 查找属组为 tom 的文件
```

## 参数

| 参数   | 说明                                                          |
|--------|---------------------------------------------------------------|
| -empty | 查找空白文件或目录                                            |
| -group | 按组查找                                                      |
| -user  | 按用户查找                                                    |
| -name  | 按名称查找                                                    |
| -iname | 按名称查找，不区分大小写                                      |
| -mtime | 按修改时间查找                                                |
| -size  | 按容量大小查找                                                |
| -type  | 按档案类型查找 f 文件 d 目录 b 块设备 c 字符型设备 l 链接文件 |
| -exec  | 对查找的档案执行命令                                          |
| -a     | 并且                                                          |
| -o     | 或者                                                          |

    find / -name "*name*" -ls
    find / -name "*name*" -exec file {} \; 查找的文件放到大括号内。查看结果的类型
    find / -name "*name*" -exec rm {} \; 删除查找到的内容
    find / -name "*name*" -ok rm {} \; 删除查找到的内容 （交互确认）
    find /home -user shrek -ls 以例表的形式显示 home 目录下用户 shrek 的文件。
    find /home -user shrek -a -group shrek -ls 以例表的形式显示用户和用户组同为 shrek 的文件。（-a 是 and 的意思，-o 是 or 的意思 默认是与，-a 可省略）
    find /home -user shrek -o -group shrek -a -type f -ls (-typef 文件，d 目录） 重点注意，-a -o 的混合使用。
    -user -type -name -group -perm -size -mtime -ok -exec -ls
    find / -perm -777 -type d -ls 入侵检测给常使用。（-type 前不用加 -a 默认就是 -a）
    递归查找文件内的字符串 find ./ -name ‘*.html’ -exec grep “breadcrumbs.inc.php” ‘{}’ \; -print 这条命令将查找所有包含 breadcrumbs.inc.php 的 HTML 文件。
    查找文件
    $ find . -maxdepth 1 -type f

    # 找出所有用户 xxx 拥有的文件，拷备到 /root/findfiles 目录

    find / -user xxx -type f -exec cp {} /root/findfiles \;

    # 查找 /home 目录下文件拥有人是 natasha, 但拥有组不是 natasha 的文件复制到  /root/backup 文件中

    find /home -user natasha -type f  -and ! -group natasha -exec cp {}  /root/backup \;

    其它下载，非视频教程内容
    find /home -name "*[a-z]",
    find /home -name \*txt -o -name \*doc
    find /home -regex '.*\.txt\|.*\.doc\|.*\.mp3'
    find ./ -regex '.*\(txt\|doc\)'
    find /home -name "*txt" -o -name "*doc" -o -name "*mp3"

    详解：

    名称 : find

    用法 : find path -option [ -print ] [ -exec -ok command ] {} \;

    使用说明 :

    将档案系统内符合 expression 的档案列出来。你可以指要档案的名称、类别、时间、大小、权限等不同资讯的组合，只有完全相符的才会被列出来。

    find 根据下列规则判断 path 和 expression，在命令列上第一个 - ( ) , ! 之前的部份为 path，之后的是 expression。如果 path 是空字串则使用目前路径，如果 expression 是空字串则使用 -print 为预设 expression。

    expression 中可使用的选项有二三十个之多，在此只介绍最常用的部份。

    -mount, -xdev : 只检查和指定目录在同一个档案系统下的档案，避免列出其它档案系统中的档案

    -amin n : 在过去 n 分钟内被读取过

    -anewer file : 比档案 file 更晚被读取过的档案

    -atime n : 在过去 n 天过读取过的档案

    -cmin n : 在过去 n 分钟内被修改过

    -cnewer file : 比档案 file 更新的档案

    -ctime n : 在过去 n 天过修改过的档案

    -empty : 空的档案 -gid n or -group name : gid 是 n 或是 group 名称是 name

    -ipath p, -path p : 路径名称符合 p 的档案，ipath 会忽略大小写

    -name name, -iname name : 档案名称符合 name 的档案。iname 会忽略大小写

    -size n : 档案大小 是 n 单位，b 代表 512 位元组的区块，c 表示字元数，k 表示 kilo bytes，w 是二个位元组。-type c : 档案类型是 c 的档案。

    d: 目录

    c: 字型装置档案

    b: 区块装置档案

    p: 具名贮列

    f: 一般档案

    l: 符号连结

    s: socket

    -pid n : process id 是 n 的档案

    你可以使用 ( ) 将运算式分隔，并使用下列运算。

    exp1 -and exp2

    ! expr

    -not expr

    exp1 -or exp2

    exp1, exp2

    范例：

    将目前目录及其子目录下所有延伸档名是 c 的档案列出来。

    # find . -name "*.c"

    将目前目录其其下子目录中所有一般档案列出

    # find . -ftype f

    将目前目录及其子目录下所有最近 20 分钟内更新过的档案列出

    # find . -ctime -20

    find . -name "*" -exec grep xxx {} ; -print |morexxx 为你想要找的字符串