# macOS上安装Git

## 1.安装[Homebrew](https://brew.sh)

```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 2.安装Git

```
$ brew install git
```

## 3.查看已安装的Git

```
$ type -a git

git is /usr/local/bin/git # 该路径在上面表示 brew 安装Git成功
git is /usr/bin/git
```

## 4.安装gitk图形界面

```
$ brew install git-gui
```

## 5.查看已安装的gitk

```
$ gitk
```

## 6.关于gitk的更多信息，请在终端中输入以下命令

```
$ man git # Linux、macOS 系统
```

```
$ git help gitk # Linux、macOS、Windows 系统
```
