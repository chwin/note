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
```

也可以设置命令别名以得到更爽快的体验，在隐藏文件 `.bashrc` 中添加以下内容：其路径为 `~/.bashrc`，同时按 `shift + command + .` 可显示隐藏文件。

```
alias masus='mas signout && mas signin myusappleid "mypassword"'
alias mascn='mas signout && mas signin mycnappleid "mypassword"'
alias mas?='mas account'
```

需重新打开终端以载入设置，那么在终端中执行 `masus` 即可切换到美区帐号，`mascn` 即切到中区，`mas?` 可查询目前登陆帐号。但如果开启了双重认证，可能遇到错误信息：

```
Error: Sign in failed: The operation couldn’t be completed. (mas.MASError error 1.)
```

关闭双重认证则一切正常，但并不建议这样做，可以考虑关闭非重要帐号的双重认证，但 iOS 10.3 或 macOS Sierra 10.12.4 及更高版本中创建的某些帐户，[无法关闭双重认证](https://support.apple.com/zh-cn/HT204915)。mas 团队正在着手处理开启双重认证无法登陆的问题，可去 [督促一番](https://github.com/mas-cli/mas/issues/56)。

在问题解决之前该怎么办：在 Mac App Store 中登陆帐号，然后重新打开终端（Terminal）即可。