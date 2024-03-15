df


**** df
    -i # inode使用量信息
-h # 人性化方式显示信息(1024进制)
-H # 人性化方式显示信息(1000进制)
-T # 显示文件系统类型

显示已挂载的块设备（未挂载无法显示）
df -Th


名称:df
使用权限: 所有使用者>
使用方式: df [选项]... [FILE]...
显示档案系统的状况，或是看所有档案系统的状况(预设值)
-a, --all 包含所有的具有 0 Blocks 的档案系统
--block-size={SIZE} 使用 {SIZE} 大小的 Blocks
-h, --human-readable 使用人类可读的格式(预设值是不加这个选项的...)
-H, --si 很像 -h, 但是用 1000 为单位而不是用 1024
-i, --inodes 列出 inode 资讯，不列出已使用 block
-k, --kilobytes 就像是 --block-size=1024
-l, --local 限制列出的档案结构
-m, --megabytes 就像 --block-size=1048576
--no-sync 取得资讯前不 sync (预设值)
-P, --portability 使用 POSIX 输出格式
--sync 在取得资讯前 sync
-t, --type=TYPE 限制列出档案系统的 TYPE
-T, --print-type 显示档案系统的形式
-x, --exclude-type=TYPE 限制列出档案系统不要显示 TYPE
-v (忽略)
--help 显示这个帮手并且离开
--version 输出版本资讯并且离开
