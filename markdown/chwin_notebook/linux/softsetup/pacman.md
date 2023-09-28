pacman

安装msys2
pacman -Syu
pacman -S openssh rsync vim
# 同步与升级
    pacman -Syy                  本地包数据库和远程的软件仓库同步
    pacman -Syu                  同时同步软件库并更新系统到最新状态
# 安装软件包
    pacman -S package1 package2  安装或者升级单个软件包，或者一列软件包（包含依赖包）
    pacman -Sy package           同步包数据库后再执行安装
 # 卸载软件包
    pacman -R package_name       删除单个软件包，保留其全部已经安装的依赖关系
    pacman -Rs package_name      删除指定软件包，及其所有没有被其他已安装软件包使用的依赖关系：
# 搜索包
    pacman -Ss 关键字            这将搜索含关键字的包。
    pacman -Qi 包名              查看有关包的信息。
    pacman -Ql 包名              列出该包的文件。
    pacman -Sw 包名              只下载包，不安装。
    pacman -Sc Pacman            下载的包文件位于 /var/cache/pacman/pkg/ 目录。该命令将 清理未安装的包文件。
    pacman -Scc                  清理所有的缓存文件。
    pacman -U                    安装一个本地包（不从源里）：
