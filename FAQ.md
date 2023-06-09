# 常见问题与解答（先将常见问题整理到该文件下，再同步至 github Issues 上）

### 2.在 macOS 系统使用 homebrew 安装 Git 未成功，依然使用的是 Apple 自带的 Git，如何解决？

- 首先查看 Git 版本如下，说明使用的 Git 还是 Apple 自带的版本:

```
$ git version
git version 2.24.3 (Apple Git-128)
```

- 然后在`.zshrc`(没有配置文件的话，则在当前用户目录下新建即可，查看[macOS 默认 Shell](https://support.apple.com/zh-cn/HT208050)，再进行配置文件的相关配置，因为不同版本的 macOS 的默认 Shell 不同)中加入`export PATH="/usr/local/bin:${PATH}"`

- 再执行

```
$ source ~/.zshrc
```

### 3.Git 命令行中的提示如何在中英文之间切换？

> 使用 homebrew 安装 Git 后，Git 命令行的提示语言变成中文

- 编辑家目录下的 .zshrc

```
$ vim ~/.zshrc
```

- 输入以下内容，并保存

```
# 终端国际化语言转化(中文：zh_CN)
export LC_ALL=en_US.UTF-8 
export LANG=en_US.UTF-8
```

- 执行以下命令立即生效

```
$ source ~/.zshrc
```

### 4.
