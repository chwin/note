# LAMP 安装部署

## 安装软件包

```zsh
    yum -y install httpd
    yum -y install mariadb mariadb-server
    yum -y install php php-mysql
```

## 编写php首页进行测试机

cd /var/www/html/
vim index.php
<?php
phpinfo();
?>

## 关闭防火墙、SELinux

systemctl stop firewalld
setenforce 0
