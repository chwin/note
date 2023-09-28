du

**** du
    du -sh /opt/oracle # 查看目录大小
    du -s # 查看目录
    du -h #人类的简写，可读性。
    du -h --max-depth=1 # 目录层数
    du -h --max-depth=0
    du -b（以byte为单位）-k（以K为单位）-m（以M为单位）
    du -h --max-depth=1 | sort -n -r #查看目录的磁盘占用情况
    du -hs #查看目录大小


    df -lh

    du -s /usr/* | sort -rn
    这是按字节排序

    du -sh /usr/* | sort -rn
    这是按兆（M）来排序

    4.选出排在前面的10个
    du -s /usr/* | sort -rn | head

    5.选出排在后面的10个
    du -s /usr/* | sort -rn | tail

    du -h –-max-depth=0 user
    du -sh –-max-depth=2 | more

    常用命令
    du -h --max-depth=1 |grep [TG] |sort #查找上G和T的目录并排序
    du -sh #统计当前目录的大小，以直观方式展现

    du -h --max-depth=1 |grep 'G' |sort #查看上G目录并排序
    du -sh --max-depth=1 #查看当前目录下所有一级子目录文件夹大小
    du -h --max-depth=1 |sort #查看当前目录下所有一级子目录文件夹大小 并排序

    du -h --max-depth=1 |grep [TG] |sort -nr #倒序排

    功能说明：显示目录或文件的大小。
    语　　法：du [-abcDhHklmsSx][-L <符号连接>][-X <文件>][--block-size][--exclude=<目录或文件>][--max-depth=<目录层数>][--help][--version][目录或文件]
    补充说明：du会显示指定的目录或文件所占用的磁盘空间。
    参　　数：
    -a或-all 显示目录中个别文件的大小。
    -b或-bytes 显示目录或文件大小时，以byte为单位。
    -c或--total 除了显示个别目录或文件的大小外，同时也显示所有目录或文件的总和。
    -D或--dereference-args 显示指定符号连接的源文件大小。
    -h或--human-readable 以K，M，G为单位，提高信息的可读性。
    -H或--si 与-h参数相同，但是K，M，G是以1000为换算单位。
    -k或--kilobytes 以1024 bytes为单位。
    -l或--count-links 重复计算硬件连接的文件。
    -L<符号连接>或--dereference<符号连接> 显示选项中所指定符号连接的源文件大小。
    -m或--megabytes 以1MB为单位。
    -s或--summarize 仅显示总计。
    -S或--separate-dirs 显示个别目录的大小时，并不含其子目录的大小。
    -x或--one-file-xystem 以一开始处理时的文件系统为准，若遇上其它不同的文件系统目录则略过。
    -X<文件>或--exclude-from=<文件> 在<文件>指定目录或文件。
    --exclude=<目录或文件> 略过指定的目录或文件。
    --max-depth=<目录层数> 超过指定层数的目录后，予以忽略。
    --help 显示帮助。
    --version 显示版本信息。
