rsync

---
tags: []
pinned: true
created: 2021-01-27T07:22:14.204Z
modified: 2021-02-17T17:28:17.989Z
---

rsync -avz /opt /mnt
# 将本地文件推送到远程服务器
    rsync -avz -e 'ssh -p 22' /etc/hosts username@192.168.1.2:/root
# 拉去远程服务器文件到本地
    rsync -avz -e 'ssh -p 22' username@192.168.1.2:/root /tmp

rsync -avz /opt/ /tmp/
rsync -avz /opt /tmp/

-a 归档模式,保持文件信息
-v 查看细则
-z 压缩传输,提高传输效率
-e 指定信道协议
-P 显示同步过程
--exclude=PATTERN 指定排除不需要传输的文件模式
/etc/rsyncd.conf