# touch 命令 – 创建空文件

## 说明

当前没有文件时建立新文件，已有同名文件时对当前文件更新三个时间。
将 file 的时间记录改为 5 月 6 日 18 点 3 分，公元两千年。时间的格式可以参考 date 指令，至少需输入 MMDDHHmm ，就是月日时与分。

## 实例

```bash
touch a # 创建一个空文件
touch a b c # 同时创建3个文件
touch -d "6/20/10 18:32" aa.txt # 创建并修改文件时间
touch -c "6/20/10 18:32" aa.txt # 修改文件时间
touch -d "2010-05-31 08:10:30" test.doc # 同时修改文件的修改时间和访问时间
touch -m -d "2010-05-31 08:10:30" test.doc # 只修改文件的修改时间
touch -a -d "2010-05-31 08:10:30" test.doc # 只修改文件的访问时间
touch -c -t 05061803 file
touch -c -t 050618032000 file
```

## 参数

| 参数  | 说明  |
| --- | --- |
| -a  | 改变档案的读取时间记录 |
| -c  | 仅修改时间，而不建立文件。 |
| -d  | 设定时间与日期，可以使用各种不同的格式 |
| -m  | 改变档案的修改时间记录 |
| -t  | 后面可以接时间，格式为 \[YYMMDDhhmm\] |

将 file 的时间记录改成 5 月 6 日 18 点 3 分，公元两千年。时间可以使用 am, pm 或是 24 小时的格式，日期可以使用其他格式如 6 May 2000 。
　　touch -d "6:03pm" file
　　touch -d "05/06/2000" file
　　touch -d "6:03pm 05/06/2000" file
　　touch 也可以制造一个空档 (0 byte). 例如 DHCP Server 所需的 /etc/dhcpd.leases,dhcpd 必须要有这个档案才能运作正常。\[root@/root\]#touch /etc/dhcpd.leases\[root@/root\]#ls -l /etc/dhcpd.leases-rw-r--r-- 1 root root 0 Jul 3 05:50 /etc/dhcpd.leases
　　记得上一次重灌前把 /etc 下的设定档 tar 起来，重灌好之后把原有设定还原，却发现系统检查设定档的时间有问题，这个时候用
　　find /etc -name * -exec touch {};
　　就可以把设定档的时间更新到与现在一致了。