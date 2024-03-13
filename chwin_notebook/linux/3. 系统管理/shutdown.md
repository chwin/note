# shutdown 命令 – 关机命令

## 说明

## 实例

```bash
shutdown -h now
shutdown -h 12:00
shutdown -h +10
shutdown -r now
shutdown -r +30 'the system will reboot'
shutdown -k now 'the system will reboot'
```

## 参数

| 参数 | 说明                               |
|------|------------------------------------|
| -t   | 添加秒数，几秒后关机               |
| -k   | 不是真关机，而是发出警告信息       |
| -r   | 在系统服务都停止后，重起           |
| -h   | 在系统服务都停止后，关机           |
| -f   | 关闭并且开机以后，强行略过磁盘检查 |
| -F   | 重启后制进行磁盘检查               |
| -c   | 取消已经在进行的shutdown指令内容   |
