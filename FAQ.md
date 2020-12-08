# 常见问题与解答

### 1.如何解决 git status 显示中文乱码？

> 在默认情况下，中文文件名在工作区中输出显示为八进制的字母编码，导致不能正确显示中文名

![中文乱码图片](https://user-images.githubusercontent.com/27407218/101326436-36cd0880-38a8-11eb-9b49-cde315821892.png)

在 Git Bash Here 中输入命令:

```
git config --global core.quotepath false
```

### 2.使用 homebrew 安装 Git 未成功，依然使用的是 Apple 自带的 Git，如何解决？

- 首先查看 Git 版本如下，说明使用的 Git 还是 Apple 自带的版本:

```
$ git version
git version 2.24.3 (Apple Git-128)
```

- 然后在`.bash_profile`或者`.zshrc`(没有配置文件的话，则在用户目录下新建即可)中加入`export PATH="/usr/local/bin:${PATH}"`

- 再执行

```
$ source ~/.bash_profile  # 或者 .zshrc
```