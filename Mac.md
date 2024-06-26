# 初始配置

## 系统配置

- 查看 SIP 状态

```zsh
  csrutil status
  # 查看 SIP 状态

  System Integrity Protection status: enabled.
  # 未关闭 SIP

  System Integrity Protection status: disabled
  # 已关闭 已关闭 SIP
```

- 关闭 SIP

```zsh
  关机，然后重新启动你的 Mac 电脑，在开机时一直按住 Command+R 迸入 Recovery 模式。
  进入 Recovery 模式后打开终端。
  在终端上输入命令 csrutil disable 然后回车。
  点击左上角苹果图标，再点击重新启动
```

- 安装任何来源 app

```zsh
  sudo spctl --master-disable
```

- 加快 Time Machine 备份速度（降低速度 0 改为 1）

```zsh
  sudo sysctl debug.lowpri_throttle_enabled=0
```

- 终端代理配置

```zsh
  echo export http_proxy="http://127.0.0.1:8080" >> ~/.zshrc
  echo export https_proxy="http://127.0.0.1:8080" >> ~/.zshrc
  source ~/.zshrc # 让配置好的代理马上生效
  curl ifconfig.me # 查看是否生效
```

- brew 安装

```zsh
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

### 终端配置（未完成）

- oh-my-zsh 安装

```zsh
  sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  # 安装 oh-my-zsh（卸载命令 uninstall_oh_my_zsh）
```

- Powerline 安装

```zsh
  sudo easy_install pip
  # 安装 python 包管理工具
```

- autojump 安装

```zsh
  brew install autojump
  cd /autojump
  ./install.py
```

- zsh-autosuggestion 安装
- zsh-syntax-highlighting 安装

```zsh
  ## 终端配置
  # iTerm2 + zsh + oh-my-zsh + Powerline
  # 使用 iTerm2+Zsh+antigen 配置终端

  # agnoster
  # iTerm2 + Oh-My-Zsh + agnoster + Powerline + solarized
```

### MAS 配置

```zsh
  # 下载 MAS
    brew install mas
```

### Mackup 配置（未完成）

## 安装 Mackup

输入下面的命令安装 Mackup：

`brew install mackup`

### 选择你的同步文件夹

```
Mackup 默认会将配置文件备份到你的 Dropbox 本地存储文件夹，前提是你的电脑上已经安装了 Dropbox。如果你不想存储到 Dropbox 中，那就需要稍微配置一下。

这里以 iCloud 为例，介绍 Mackup 的备份路径配置方法。

首先，在终端输入命令： 
```

```zsh
vi ~/.mackup.cfg
# 在配置文件中添加如下内容
[storage]
engine = icloud
# 这样，你就已经设置好你的 Mackup 同步文件夹为 iCloud 了，剩下要做的就是保存这份配置
```

## Mackup 的操作

关于 Mackup 的操作其实非常简单，这里列出 Mackup 的常用操作命令：

- `mackup backup` 使用 Mackup 进行备份操作
- `mackup restore` 使用 Mackup 进行数据的恢复
- `mackup list` 查看 Mackup 支持的软件列表
- `mackup -h` Mackup 的帮助命令
- `mackup uninstall` 将配置文件拷贝回原来的系统目录

如果你想卸载 Mackup，输入以下命令即可：

`brew uninstall mackup`

首先，在终端输入命令：
vi ~/.mackup.cfg
继续在窗口中输入以下文字：
\[storage\]
engine = icloud
这样，你就已经设置好你的 Mackup 同步文件夹为 iCloud 了

```zsh
  brew install mackup # 安装 Mackup
  brew uninstall mackup # 卸载 Mackup
  mackup backup # 使用 Mackup 进行备份操作
  mackup restore # 使用 Mackup 进行数据的恢复
  mackup list # 查看 Mackup 支持的软件列表
  mackup -h Mackup # 的帮助命令
  mackup uninstall # 将配置文件拷贝回原来的系统目录

```

## 常用软件例表

### 系统工具

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| ActiveDock | 强大的 Dock 个性定制增强工具 |     |     |
| Deeper | 解锁 Mac 的隐藏功能 |     |     |
| Magnet | mac 窗口整理神器 |     |     |
| MultiDock | 创建多个 Dock 栏 |     |     |
| Paste |     |     |     |
| Recents |     |     |     |
| SizeUp | 分屏工具 |     |     |
| istat | 系统监控软件 |     |     |
| 即刻地球 |     |     |     |
| Keyboard Maestro | 键盘大师 | brew install keyboard-maestro | 1   |
| Parallels Desktop | 虚拟机 | 破解安装 | 1   |
| the-unarchiver | 解压缩 | brew install the-unarchiver | 1   |
| 腾讯柠檬清理 | 卸载工具 | brew install tencent-lemon | 1   |
| HyperDock | 仿 windows 窗口预览工具 |     | 2   |
| Launchpad Manager | 启动台应用图标批量管理 | 破解安装 | 2   |
| Moom | 窗口整理、排列、缩放工具 |     | 2   |
| Avira | 杀毒软件 | brew install avira-antivirus | 3   |
| LuLu | 开源的 mac 应用防火墙软件 | brew install lulu | 3   |
| OnyX | 系统工具箱 | brew install onyx | 3   |
| qlcolorcode | 代码块预览插件 | brew install qlcolorcode | 3   |
| qlmarkdown | Markdown 预览插件 | brew install qlmarkdown | 3   |
| qlvideo | 视频预览插件 | brew install qlvideo | 3   |
| 夜神安卓模拟器 | 安卓模拟器 |     | 3   |
| Account Switcher | App Store 帐号切换器 | 破解安装 | 4   |
| AirServer | 手机投屏 Mac 神器 | 破解安装 | 4   |
| MacZip | 很好用的压缩解压软件 | brew install maczip | 4   |
| SyncSettings | 备份所有软件配置 | brew install syncsettings | 4   |
| AirServer | 手机投屏到电脑 | brew install airserver | 5   |
| MacWk 应用更新器 |     | macwk.com | 5   |
| MonitorControl | 调节显示器亮度和音量 | brew install MonitorControl | 5   |
| OnyX | 系统维护优化工具 | 破解安装 | 5   |
| flux | 根据时间调整显示器亮度 | brew install flux | 5   |
| iStat Menus | 系统活动监控 |     | 5   |
| mac OS 小助手 |     | macwk.com | 5   |

TechTool Pro 13.0.2 中文破解版 （强悍的 mac 测试及维护工具）

### 效率工具

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| magnet | 窗口分屏管理神器 | 破解安装 | 5   |
| iCollections | 桌面文件整理神器 |     | 4   |
| Vimac | 通过用键盘代替鼠标操作从而提高电脑使用效率，非常适合程序员使用 |     | 4   |
| 简悦 · 同步助手 |     |     | 3   |
| 自动切换输入法 |     | mas install 1470350547 | 3   |
| 简达  | app 配合 edge 插件使用 |     | 3   |
| Copy+ | 剪贴板历史记录管理 |     | 3   |
| Yoink | 一款移动复制文件效率工具 |     | 2   |
| SpamSieve | 强大的垃圾邮件过滤器 | 破解安装 | 2   |
| Recents | 快速打开应用最近打开的文件 |     | 2   |
| One Switch | 系统功能快速开关工具 |     | 2   |
| Better And Better | Mac 手势神器 |     | 1   |
| PopClip | 划词扩展工具 |     | 1   |
| utools 启动器 | 快速启动 app | brew install utools | 1   |
| Bartender | 整理导航栏图标 |     | 1   |
| Things3 | 日程和任务管理工具 |     | 1   |
| 键指如飞 | 查看软件快捷键 |     | 1   |
| Mission Control Plus | 窗口管理软件 |     | 1   |
| 超级右键 | 超级右键 | 破解安装 | 1   |
| AltTab | 预览窗口快速切换利器 |     | 1   |
| Shortcut Bar | 菜单栏快速启动工具 |     |     |
| Workspaces | 方便的快速操作组织工具 |     |     |

### 办公软件

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| 清歌输入法 | 五笔输入法 |     |     |
| 扫描王 |     |     |     |
| hallelujah | 英文输入法 |     |     |
| RightFont | 字体管理软件 | brew install rightfont |     |
| 微信  |     | brew install wechat | 1   |
| qq 聊天 |     | brew install qq | 1   |
| 千牛  |     | brew install aliworkbench |     |
| iText | 截图翻译 |     | 1   |
| WeChatPlugin | 微信助手 |     | 1   |
| Microsoft edge | 浏览器 | brew install microsoft-edge | 1   |
| Microsoft Office | 微软办公软件 | 破解安装 | 1   |
| PDF Expert | 最好用的 PDF 编辑器 | 破解安装 | 3   |
| Xmind | 思维导图软件 | 破解安装 | 4   |
| MindNode | 老牌思维导图软件 |     | 4   |

### 文件管理

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| File Multi Tool | 文件创建 / 修改日期编辑 |     |     |
| Big Mean Folder Machine | 文件管理软件 |     |     |
| UltraCompare | 优秀的文本对比工具 |     |     |
| Tidy Up | 强大的重复文件清理工具 |     |     |
| Umbrella | 可以结合 Tidy Up 5 进行使用，保持 Mac 的清洁高效 |     |     |
| Sync Folders Pro | 同步软件 |     |     |
| File Cabinet | 文件管理器 |     |     |
| Duplicate File Finder Pro | 重复文件清理 |     | 1   |
| TotalFinder | 最好用的 Finder 增强工具 |     | 1   |
| FE File Explorer | 一款功能强大的文件管理器 |     | 1   |
| A Better Finder Rename | 文件批量重命名软件 |     | 2   |
| renamer | 文件批量重命名软件 |     | 2   |
| Beyond Compare | 同步工具 |     | 2   |
| 百度云盘 |     | brew install baidunetdisk | 2   |
| onedrive | 微软网盘（要求密码，放最后） | brew install onedrive | 2   |
| Disk Analyzer Pro | 查看磁盘大文件 |     | 2   |
| Hazel | 自动整理，让你的 Mac 井井有条 |     | 2   |
| A Better Finder Attributes | 更改 JPEG 和 RAW 拍摄日期 |     | 3   |
| Scherlokk | 文件搜索 |     | 3   |
| HoudahSpot | 超级搜索 |     | 3   |
| Disk Analyzer | 磁盘分析工具 |     | 3   |
| Folder Tidy | 文件整理神器 |     | 4   |
| Big Mean Folder Machine 2 |     |     | 4   |
| DEVONthink | 最好用的 mac 文件管理工具 |     | 4   |
| Big Mean Folder Machine 2 |     |     | 4   |
| DEVONthink | 最好用的 mac 文件管理工具 |     | 4   |

### 作图软件

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| 看图  |     | mas install 1314842898 |     |
| 扫描王 |     |     |     |
| 光影魔术手 |     |     |     |
| photoshop 作图软件 |     |     |     |
| Sketch | 矢量绘图软件 |     |     |
| Photoshop Elements | ps 简化版 |     |     |
| Photolemur 3 | AI 自动优化图片 |     |     |
| PhotoBulk | 图片批量压缩重命名添加水印 |     |     |
| Image Crop for Mac | 图片批量按比例裁切工具 |     |     |
| Iconjar | 图标素材管理工具 |     |     |
| GraphicConverter 11 | 图片浏览 |     |     |
| Eagle | 收藏图片管理 |     |     |
| GraphicConverter | 图片浏览 |     |     |
| Auto CAD |     |     |     |
| ArcSoft Photo+ | 图片浏览 |     |     |
| Adobe Lightroom Classic | 照片整理软件 |     |     |
| Adobe Bridge | 多媒体文件组织管理工具 |     |     |
| ACDSee Photo Studio 6 | 图片浏览 |     |     |
| References.Design | 照片管理 |     |     |

Photos Exif Editor 2.14 破解版 （图片元数据 EXIF 编辑器）
Duplicate Photos Fixer Pro for Mac （重复照片清理工具）
ON1 Portrait AI 2021 15.1.0 (10100) 中文破解版 (AI 智能人像处理软件）
Picture Colorizer Pro 2.0.2 破解版 （黑白照片上色软件）
ON1 Resize 2021 15.1.0 (10100) 中文破解版 （不错的图片无损放大软件）
ON1 Photo RAW 2021 15.1.0.10100 中文破解版 （专业级摄影后期图像处理软件）
Image Crop 1.3.1 破解版 （图片批量按比例裁切工具）
PhotoBulk 2.2 (270) 中文破解版 （图片批量压缩重命名添加水印）
ON1 HDR 2021 15.1.0 (10100) 中文破解版 （制作完美无瑕的 HDR 照片）
Tweak Photos 2.3 破解版 （图片批量编辑神器）
Movavi Photo Editor 6.7.1 破解版 （国外版的美图秀秀）
ColorWell 7.2.6 破解版 (mac 调色板 / 配色工具）
Iconjar 2.7.3 (46884) 破解版 （图标素材管理工具）
AirMagic 1.0.2.7263 中文破解版 （一键优化图片品质）
Topaz Sharpen AI 2.2.4 破解版 （最好的图片清晰度增强软件）
Artista Impresso Pro 1.8.16 破解版 （艺术照片生成制作工具）
Pastello Pro 1.1.16 破解版 （将照片转为蜡笔画铅笔画）
ABBYY FineReader OCR Pro 不仅是一款将纸质文档，PDF 和图片转换为可编辑和可搜索的文件，还是一款专业的 OCR 图片识别工具，文本识别准确性行业最高，

### 学习软件

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| 电子书管理软件 |     | brew install calibre |     |
| 爱英阅 | 提取分析英文生词 |     |     |
| 每日英语听力 | 最好的英语学习类软件 |     |     |
| 有道词典 |     | brew install youdaodict |     |
| 摸鱼  | 背单词 |     |     |
| 年轮 3 | 记忆软件 |     |     |
| marginnote | 强大的电子书阅读器（必装——stor） |     |     |
| calibre | 电子书管理 |     |     |
| Typora | Markdown 编辑器 |     |     |
| Type Fu | 打字速度练习应用 |     |     |
| Text Scanner | 超强 OCR 扫描截图识别翻译软件 |     |     |
| MarginNote 3 | 强大的阅读软件 |     |     |
| Koodo Reader | 电子书管理 |     |     |
| Koodo Reader | 开源电子书阅读神器 |     |     |
| Knotes | 管理 Kindle |     |     |
| Anki 志愿者版 |     |     |     |
| Anki | 超强辅助记忆软件 |     |     |

### 开发软件

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| tmux |     | brew install tmux |     |
| scrutiny | 网站链接检查工具 |     |     |
| pycharm | Python 编辑开发 |     |     |
| nacicat premium | 一款易于使用的多连接数据库管理工具 |     |     |
| iTerm2 | 安装  | brew install iterm2 |     |
| desh | 文档查询工具 |     |     |
| WebStorm | Web 前端开发神器 |     |     |
| Visual Studio Code | 编辑器 | brew install visual-studio-code |     |
| Termius for Mac | SSH 客户端） v4.9.20 激活版 |     |     |
| Termius 7.4.1 破解版 | 最好用的 SSH 连接客户端 |     |     |
| TeamViewer | 远程控制（要求密码，放最后） | brew install TeamViewer |     |
| Swift Playgrounds | 编程学习软件 |     |     |
| Sourcetree | git 客户端 | brew install SourceTree |     |
| SourceTree | 免费的 Git 客户端 |     |     |
| Lookin | 开发 iOS App 时的 UI 调试软件 |     |     |
| Go2Shell | 访达工具栏快速打开终端窗口。支持与 Terminal.app，iTerm2，xterm 一起使用。 | brew install Go2Shell |     |
| Fork | 最好用的 GUI 版 Git 工具之一 |     |     |
| FinalShell FinalShell | 是一体化的的服务器，网络管理软件 |     |     |
| Dash | 代码文档管理工具 |     |     |

Remote Desktop Manager Enterprise 2020.3.4.0 中文破解版 （强大的远程连接工具）
OpenInTerminal 是一款快速在终端中打开指定目录的效率工具
Blocs 4.1.0 (410) 中文破解版 （可视化网页设计工具）

### 网络工具

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| telegram |     | brew install telegram-desktop | 3   |
| 熊猫代理 | 代理软件 |     | 1   |
| ShadowsocksX-NG | 代理软件 |     | 1   |
| Downie | 最好用的视频下载工具 |     |     |
| 迅雷  |     |     |     |
| iTerm2 | 终端命令行工具 |     |     |
| TripMode | 流量限制工具 |     |     |
| Simon mac | 网站监控工具 |     |     |
| Dejal Simon | 服务器监控软件 |     |     |
| wifi explorer | wifi 管理 | brew install wifi-explorer |     |
| Motrix | 一款全能的下载工具 | brew install Motrix |     |

### 多媒体

#### 音频软件

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| SoundSource | 音频切换工具 |     |     |
| TunePat Apple Music Converter | 苹果音乐下载转换器 |     |     |
| TunePat Spotify Converter | Spotify 音乐转换器 |     |     |
| Music Tag Editor Pro | 音乐标签管理软件 |     |     |
| KeepVid Music Tag Editor | 音乐标签编辑器 |     |     |
| Yate 6.3 破解版 | 强大的音乐标签编辑管理工具 |     |     |
| adobe audition | 音频制作软件 |     |     |
| Audio Hijack | 录音工具 |     |     |
| LoopBack | 虚拟声卡 |     |     |
| Fission | 音频编辑软件。智能分割：基于静音自动分割文件 |     |     |
| Background Music | 音量控制工具，播放视频时自动控制背景音乐的播放与暂停 | https://github.com/kyleneideck/ |     |

#### 影音播放

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| 射手影音 |     |     |     |
| 央视影音 |     |     |     |
| 5KPlayer | 下载、播放、dlna 分享 |     |     |
| serviio | 建立 dlna 服务器 |     |     |
| Shazam | 音乐雷达 |     |     |
| 喜马拉雅 |     | brew install ximalaya |     |
| 高清播放器 |     | brew install iina |     |

#### 视频制作

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| Final Cut | 影音剪辑软件 |     |     |
| Compressor | 视频解码格式转换工具，与 Final Cut Pro 无缝集成 |     |     |
| Wondershare Filmora | 视频编辑软件 |     |     |
| Camtasia 2019 | 视频录制和剪辑软件 |     |     |
| Movavi Screen Recorder | 屏幕录像软件 |     |     |
| iMovie for Mac | 专业视频剪辑软件 |     |     |
| 爱剪辑 |     |     |     |
| Effect Creator | 抖音视频特效软件 |     |     |
| Final Cut | 影音剪辑软件 |     |     |
| VideoProc | 全能视频处理软件 |     |     |
| Wondershare Filmora | 好用的视频剪辑软件 |     |     |
| Camtasia 2019 | 视频录制和剪辑软件 |     |     |
| Movavi Screen Recorder | 屏幕录像软件 |     |     |
| iMovie for Mac | 专业视频剪辑软件 |     |     |
| 爱剪辑 |     |     |     |
| Effect Creator | 抖音视频特效软件 |     |     |
| Wondershare UniConverter | 最好的视频格式转换器 v 11.6.4.6 |     |     |
| ScreenFlow | 排名第一的录屏软件 |     |     |
| Permute 3 | 万能音视频转换器 |     |     |

### 手机管理

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| AnyTrans | 管理苹果手机软件（破解） | 破解安装 |     |
| UltData | IOS 设备数据还原工具 | 破解安装 |     |
| iMazing | 最好用的 iOS 设备管理工具 | 破解安装 |     |
| SyncBird | 可以在 iPhone，iPad，iPod 和 Mac 之间传输音乐，照片，视频等 |     |     |

### 黑苹果工具

| 名称  | 用途  | 安装方式 | 评级  |
| --- | --- | --- | --- |
| hackintool |     | brew install hackintool | 1   |
| OpenCore Configurator | 黑苹果 OC 引导配置工具 | brew install opencore-configurator | 1   |
| balenaEtcher | U 盘启动盘制作工具 | brew install balenaetcher | 1   |
| QtOpenCoreConfig | 系统安装工具 |     | 2   |

### 临时收集待整理

[简阅同步助手](https://onedrive.live.com/?authkey=%21AIsCKC8oZsYQczM&id=11407577D948B8E6%21968&cid=11407577D948B8E6)

BetterTouchTool for Mac（触摸板增强神器）
Tenorshare UltData for Mac(iOS 数据恢复软件）

Display Maid 允许您根据配置保存和还原窗口位置。通过 Display Maid 您可以在每次连接 / 断开显示器时自动恢复 / 保存当前显示器的桌面窗口位置，这在使用一个或多个显示器时很有用。

文件比较 / 合并神器：Araxis Merge
终端模拟器：SecureCRT

Crystal Crystal 是针对 Mac 平台的设计软件 Sketch 而制作的伴侣应用，可以方便的在 Android 设备上看效果，对于 Mac 的设计师而言是非常不错的工具。Android 端需下载客户端
24 Hour Wallpaper 4.0 破解版 （精美的 5K 动态桌面壁纸）