Mackup

## 安装 Mackup

输入下面的命令安装 Mackup：

```brew install mackup```

### 选择你的同步文件夹

Mackup 默认会将配置文件备份到你的 Dropbox 本地存储文件夹，前提是你的电脑上已经安装了 Dropbox。如果你不想存储到 Dropbox 中，那就需要稍微配置一下。

这里以 iCloud 为例，介绍 Mackup 的备份路径配置方法。

首先，在终端输入命令：

```
vi ~/.mackup.cfg
在配置文件中添加如下内容
[storage]
engine = icloud
```

这样，你就已经设置好你的 Mackup 同步文件夹为 iCloud 了，剩下要做的就是保存这份配置

## Mackup 的操作

关于 Mackup 的操作其实非常简单，这里列出 Mackup 的常用操作命令：

- `mackup backup` 使用 Mackup 进行备份操作
- `mackup restore` 使用 Mackup 进行数据的恢复
- `mackup list` 查看 Mackup 支持的软件列表
- `mackup -h` Mackup 的帮助命令
- `mackup uninstall` 将配置文件拷贝回原来的系统目录

如果你想卸载 Mackup，输入以下命令即可：

```
brew uninstall mackup
```