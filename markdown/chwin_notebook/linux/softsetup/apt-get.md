apt-get

- 查看帮助信息

```bash
brew help
```

- 查看版本

```bash
brew -v
```

- 更新Homebrew自己

```bash
brew update
```

- 更新包 

```bash
//更新所有
brew upgrade

//更新指定包
brew upgrade [包名]
```

- 安装软件包

```bash
brew install [包名]
```

- 卸载安装包

```bash
brew uninstall [包名]
```

- 查询可更新的包

```bash
brew outdated
```

- 清理旧版本

```bash
//清理所有包的旧版本
brew cleanup 

//清理指定包的旧版本
brew cleanup [包名]

//查看可清理的旧版本包，不执行实际操作
brew cleanup -n 
```

- 锁定不想更新的包

```bash
//锁定某个包
brew pin $FORMULA  
//取消锁定
brew unpin $FORMULA     
```

- 查看包信息

```bash
brew info [包名]
```

- 查看安装列表

```bash
brew list
```

- 查询可用包

```bash
brew search [包名]
```

- 卸载Homebrew

```bash
cd `brew --prefix`
rm -rf Cellar
brew prune
rm `git ls-files`
rm -r Library/Homebrew Library/Aliases Library/Formula Library/Contributions
rm -rf .git
rm -rf ~/Library/Caches/Homebrew
```

- 显示包的依赖关系

```bash
brew deps --installed --tree
```
