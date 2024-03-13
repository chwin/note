

[Homebrew](https://brew.sh/index_zh-cn.html) 和 [MAS](https://github.com/mas-cli/mas) 正是为解决这个而生的，后者能够操纵 Mac App Store 接口来安装其中的应用，而前者适用于非 MAS 的几乎所有软件。



```
# 下载 Homebrew
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# 下载第三方应用
brew cask install alfred
brew cask install google-chrome
brew cask install iina
brew cask install steam
brew cask install virtualbox
brew cask install virtualbox-extension-pack

# 下载 MAS
brew install mas

# 下载 Mac App Store 应用
mas install 441258766 # magnet
mas install 425424353 # the unarchiver
mas install 836500024 # wechat
mas install 863486266 # sketchbook
mas install 595191960 # copyclip
mas install 880001334 # reeder
mas install 1254743014 # lyricsx
mas install 937984704 # amphetamine
mas install 1081413713 # gif brewery 3

# 重置启动台图标顺序
defaults write com.apple.dock ResetLaunchPad -bool true; killall Dock
```

