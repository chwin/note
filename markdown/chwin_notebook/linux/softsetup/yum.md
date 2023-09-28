# cd 命令 – 进入目录

## 说明

## 实例

## 参数

| 参数  | 说明  |
| --- | --- |

yum 常用命令

1.  列出所有可更新的软件清单命令：yum check-update
    
2.  更新所有软件命令：yum update
    
3.  仅安装指定的软件命令：yum install &lt;package_name&gt;
    
4.  仅更新指定的软件命令：yum update &lt;package_name&gt;
    
5.  列出所有可安裝的软件清单命令：yum list
    
6.  删除软件包命令：yum remove &lt;package_name&gt;
    
7.  查找软件包命令：yum search
    
8.  清除缓存命令:
    

yum clean packages: 清除缓存目录下的软件包
yum clean headers: 清除缓存目录下的 headers
yum clean oldheaders: 清除缓存目录下旧的 headers
yum clean, yum clean all (= yum clean packages; yum clean oldheaders) : 清除缓存目录下的软件包及旧的 headers