homebrew

# 查看
- 查看帮助信息
  brew help

- 查看版本
  brew -v

- 查询可更新的包
  brew outdated

- 查看包信息
  brew info [包名]

- 查看安装列表
  brew list
  brew list --cask

- 查询可用包
  brew search [包名]

# 更新
- 更新Homebrew自己
  brew update

- 更新包
  更新所有
  brew upgrade
  更新指定包
  brew upgrade [包名]

# 安装
- 安装软件包
  brew install [包名]
  brew install --cask [包名]


# 清理
- 清理旧版本
  清理所有包的旧版本
  brew cleanup 

  清理指定包的旧版本
  brew cleanup [包名]

  查看可清理的旧版本包，不执行实际操作
  brew cleanup -n

- 锁定不想更新的包
  锁定某个包
  brew pin $FORMULA
  取消锁定
  brew unpin $FORMULA   

# 卸载
- 卸载安装包
  brew uninstall [包名]

- 卸载Homebrew
  cd `brew --prefix`
  rm -rf Cellar
  brew prune
  rm `git ls-files`
  rm -r Library/Homebrew Library/Aliases Library/Formula Library/Contributions
  rm -rf .git
  rm -rf ~/Library/Caches/Homebrew


brew install wget: 安装wget包(Homebrew 会将软件包安装到独立目录, 并将其文件软链接至 /usr/local).
brew search mysql: 搜索.
brew info mysql: 主要看具体的信息. 比如目前的版本, 依赖, 安装后注意事项等.
brew update: 更新Homebrew.
brew outdated: 列出所有安装包里可以升级的包.
brew upgrade: 升级所有可以升级包.
brew cleanup: 清理不需要的版本极其安装包缓存.
brew reinstall mysql: 重新覆盖安装包.
brew doctor: 检查有没有问题
