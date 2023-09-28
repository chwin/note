# mount 命令 – 挂载目录

## 说明

## 实例

```bash
   mount # 查看挂载目录
   mkdir /mnt/cdrom # 建立挂载目录
   mount /dev/cdrom /mnt/cdrom/ # 挂载光驱
```

## 参数

| 参数 | 说明 |
|------|------|
|      |      |

   mount -o acl /dev/sdb /mnt  # 挂载时打开acl功能（根分区默认是打开的，其他分区需要手工打开）
   mount -o loop -t iso9600 /rhel4-1.iso /media/cdrom/ # 将本地ISO文件挂载到指定目录
   mount /192.168.1.250:/var/ftp/pub /media/cdrom      # 挂载FTP文件服务器目录到本地目录
   mount -t ext4 -o rw /dev/vg0/lv0 /database          # 以读写模式挂载EXT4文件系统逻辑卷
   mount -t iso9660 /dev/cdrom /media/cdrom/           # 将本地光驱挂载到指定目录
   mount -o loop /loop1.img /mnt/loop1                 # 将本地文件挂载到指定目录，挂载前使用mkfs指定文件系统
   mount -o remount,rw /mnt/loop1 # 以读写模式重新挂载
   mount -o remount,ro /mnt/loop1 # 以只读模式重新挂载
   mount -t vfat /dev/sda1 /mnt/  # 挂载fat32文件系统
   mount -t ntfs /dev/sda1 /mnt/  # 挂载ntfs文件系统
   mount -a                       # 把/etc/fstab中列出的路径全部挂载。
   mount -r                       # 将mount的路径定为read only。
   mount -t smbfs
   -t # 指定文件系统的类型
   iso9600
   ext4
   ext3
   smbfs
   ntfs
   vfat
   -o # 指定挂载选项
   ro, rw # 以只读或读写形式挂载，默认是rw
   sync # 不使用缓存，而是对所有操作直接写入磁盘
   async # 使用缓存，默认是async
   noatime # 每次访问文件时不更新文件的访问时间
   atime # 每次访问文件时更新文件的访问时间
   remount # 重新挂载文件系统
   linux和Windows混装时注意主分区数量 Linux挂载分区报错有可能是这原因
   linux中最多只能由四个IDE设备
   硬盘最多只能由四个主分区，逻辑分区是为了解决主分区数量不能满足系统要求而产生的。
   linux支持FAT32读写和NTFS的只读
   linux所有目录都可以创建独立分区，没有进行分区的子目录都会保存在跟分区中。

名称 : mount
使用权限 : 系统管理者或/etc/fstab中允许的使用者
使用方式 :
mount [-hV]
mount -a [-fFnrsvw] [-t vfstype]
mount [-fnrsvw] [-o options [,...]] device | dir
mount [-fnrsvw] [-t vfstype] [-o options] device dir
说明 :
将某个档案的内容解读成档案系统，然后将其挂在目录的某个位置之上。当这个命令执行成功后，直到我们使用 umnount 将这个档案系统移除为止，这个命令之下的所有档案将暂时无法被调用。
这个命令可以被用来挂上任何的档案系统，你甚至可以用 -o loop 选项将某个一般的档案当成硬盘机分割挂上系统。这个功能对于 ramdisk,romdisk 或是 ISO 9660 的影像档之解读非常实用。
参数
-V
显示程序版本
-h
显示辅助讯息
-v
显示较讯息，通常和 -f 用来除错。
-a
将 /etc/fstab 中定义的所有档案系统挂上。
-F
这个命令通常和 -a 一起使用，它会为每一个 mount 的动作产生一个行程负责执行。在系统需要挂上大量 NFS 档案系统时可以加快挂上的动作。
-f
通常用在除错的用途。它会使 mount 并不执行实际挂上的动作，而是模拟整个挂上的过程。通常会和 -v 一起使用。
-n
一般而言，mount 在挂上后会在 /etc/mtab 中写入一笔资料。但在系统中没有可写入档案系统存在的情况下可以用这个选项取消这个动作。
-s-r
等于 -o ro
-w
等于 -o rw
-L
将含有特定标签的硬盘分割挂上。
-U
将档案分割序号为 的档案系统挂下。-L 和 -U 必须在/proc/partition 这种档案存在时才有意义。
-t
指定档案系统的型态，通常不必指定。mount 会自动选择正确的型态。
-o async
打开非同步模式，所有的档案读写动作都会用非同步模式执行。
-o sync
在同步模式下执行。
-o atime
-o noatime
当 atime 打开时，系统会在每次读取档案时更新档案的『上一次调用时间』。当我们使用 flash 档案系统时可能会选项把这个选项关闭以减少写入的次数。
-o auto
-o noauto
打开/关闭自动挂上模式。
-o defaults
使用预设的选项 rw, suid, dev, exec, auto, nouser, and async.
-o dev
-o nodev-o exec
-o noexec
允许执行档被执行。
-o suid
-o nosuid
允许执行档在 root 权限下执行。
-o user
-o nouser
使用者可以执行 mount/umount 的动作。
-o remount
将一个已经挂下的档案系统重新用不同的方式挂上。例如原先是唯读的系统，现在用可读写的模式重新挂上。
-o ro
用唯读模式挂上。
-o rw
用可读写模式挂上。
-o loop=
使用 loop 模式用来将一个档案当成硬盘分割挂上系统。
范例
将 /dev/hda1 挂在 /mnt 之下。

mount /dev/hda1 /mnt
将 /dev/hda1 用唯读模式挂在 /mnt 之下。

mount -o ro /dev/hda1 /mnt
将 /tmp/image.iso 这个光碟的 image 档使用 loop 模式挂在 /mnt/cdrom之下。用这种方法可以将一般网络上可以找到的 Linux 光 碟 ISO 档在不烧录成光碟的情况下检视其内容。

mount -o loop /tmp/image.iso /mnt/cdrom
相关命令umount
