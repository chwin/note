brew cask

- 安装卸载软件 

```text
brew --version 或者 brew -v 显示brew版本信息
brew install <formula> 安装指定软件
brew unistall <formula 卸载指定软件
brew list  显示所有的已安装的软件
brew search text 搜索本地远程仓库的软件，已安装会显示绿色的勾
brew search /text/ 使用正则表达式搜软件
```

- 升级软件 

```text
brew update 自动升级homebrew（从github下载最新版本）
brew outdated 检测已经过时的软件
brew upgrade  升级所有已过时的软件，即列出的以过时软件
brew upgrade <formula>升级指定的软件
brew pin <formula> 禁止指定软件升级
brew unpin <formula> 解锁禁止升级
brew upgrade --all 升级所有的软件包，包括未清理干净的旧版本的包
```

- 清理相关

homebrew 在升级软件时候不会清理相关的旧版本，在软件升级后可以使用如下命令清理：

```text
brew cleanup -n 列出需要清理的内容
brew cleanup <formula> 清理指定的软件过时包
brew cleanup 清理所有的过时软件
brew unistall <formula> 卸载指定软件
brew unistall <fromula> --force 彻底卸载指定软件，包括旧版本
```



```
# 安装软件
brew cask install 软件名

# 卸载软件（卸载的应用的数据会被保留，比如偏好设置）
brew cask uninstall 软件名

# 卸载软件（把应用留下来的痕迹一起清理掉）
brew cask zap 软件名

# 查找相关软件的信息
brew cask info 软件名

# 删除 Homebrew Cask 下载的包
brew cask cleanup

# 列出通过 Homebrew Cask 安装的包
brew cask list

# 一键更新本地的程序包到最新版本。
brew update && brew upgrade
```





