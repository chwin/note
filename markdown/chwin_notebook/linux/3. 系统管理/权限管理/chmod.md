# chmod 命令 – 修改权限

## 说明

修改拥有者和所属组的权限

## 实例

```bash
chmod u+w abc.txt
chmod g-r abc.txt
chmod ugo=rwx abc.txt

```

## 参数

| 参数 | 说明 |
|------|------|
|      |      |
加减法：u/g/o +/-/=
数字法：r=4 w=2 x=1 三位 两位 一位

-=0
x=1
w=2
r=4

wx=3
rx=4+1=5
rw=4+2=6
rwx=4+2+1=7
