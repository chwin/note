stat

*** stat
    stat a.txt
    查看文件建立时间、修改时间、访问时间。
    Access: 文件最近一次被访问的时间
    Modify: 文件内容最近一次被修改的时间
    Change: 文件属性最近一次被改变的时间
    假如用cat命令将文件a.txt的内容输出到终端（ 执行 cat a.txt）, 那么只有a.txt的Access就被刷新了
    假如我们把当前的时间追加到a.txt(执行 date >> a.txt) ， 那么a.txt的Modify和Change都被刷新
    假如我们把a.txt的权限改为777(执行 chmod 777 a.txt) , 那么只有a.txt的Change被刷新
    假如我们用vi命令把文件a.txt打开, 然后保存退出，那么a.txt的Access，Modify和Change都被刷新
    功能说明：显示inode内容。
    语　　法：stat [文件或目录]
    补充说明：stat以文字的格式来显示inode的内容。
