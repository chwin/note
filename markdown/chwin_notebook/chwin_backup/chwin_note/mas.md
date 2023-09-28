mas

## 安装

[Homebrew](https://brew.sh/index_zh-cn.html) 是安装 mas 的最好方式，在只要把以下代码复制到终端（Terminal）后运行即可：

```
brew install mas
```

## 查询与安装应用

1. 用命令 `mas search 关键词` 查询应用。比如在终端中执行 `mas search xcode`，大概 1 秒就显示了结果；

2. 用命令 `mas list` 查询已安装应用及其识别码。

## 更新应用

 `  mas upgrade `  更新所有软件

如果更新特定应用，需要使用命令 `mas outdated` 先查询待更新列表以获取应用识别码，再更新一个或几个应用：

```
mas upgrade 甲应用识别码
mas upgrade 甲应用识别码 乙应用识别码 丙应用识别码
```

## 切换 Mac App Store 账号

这是多区账号拥有者的福音，我们终于可以更方便地下载和更新其他区的应用了。如果忘记了当前帐号，使用命令 `mas account` 查询。可用命令 `mas signout` 退出当前帐号，并按如下命令登陆新的账号：

```
mas signin Apple ID "密码"
如：mas signin mas@example.com "mypassword"