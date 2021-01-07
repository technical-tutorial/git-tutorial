## 安装完成后重要的设置

### 1.设置用户名和电子邮件地址

```
$ git config --global user.name "Mona Lisa"
$ git config --global user.email "email@example.com"
```

### 2.配置`core.autocrlf`属性

core.autocrlf 配置说明文档地址: https://github.com/progit/progit2/blob/master/book/08-customizing-git/sections/config.asc#coreautocrlf

```
$ git config --global core.autocrlf true // Windows 跨平台程序的设置
$ git config --global core.autocrlf input // Linux 和 macOS 跨平台程序的设置
$ git config --global core.autocrlf false // 仅运行在 Windows 平台程序的设置 
```

### 3.配置`credential.helper`属性






### n.以上步骤完成之后，查看 ~/.gitconfig 配置文件如下所示:

```
[user]
	name = chengxiaodong # 设置用户名
	email = 990094523@qq.com # 设置用户电子邮箱
[core]
	editor = code --wait # 设置默认的文本编辑器
	quotepath = false # 设置默认是否转义
	safecrlf = true # 设置在工作区中是否是换行符，当值为 true 时，会阻止提交，也可以设置成 warn，Git 只会显示警告而不会阻止提交，与 core.autocrlf 相关
	autocrlf = true # 设置是否自动转换行结束符，在 Windows 上设置为 true, 在 Linux 和 macOS 上设置为 input 即可
[gui]
	encoding = utf-8 # 设置 git-gui 的编码
[diff]
	tool = vscode # 设置对比工具的名称
[difftool "vscode"]
	cmd = code --wait --diff $LOCAL $REMOTE # 设置对比工具的命令行启动方式，这里使用的是 vscode 作为合并工具
[difftool]
	prompt = false # 设置 Git 在启动外部程序之前，是否要询问我们
[merge]
	tool = vscode # 设置合并工具的名称
[mergetool "vscode"]
	cmd = code --wait $MERGED # 设置合并工具的命令行启动方式，这里使用的是 vscode 作为合并工具
	trustExitCode = true # 设置外部程序结束之后，Git 是否直接使用它的返回值来判断合并是否成功
[mergetool]
	keepBackup = false # 设置是否要备份原来含有冲突标示的文件
	prompt = false # 设置 Git 在启动外部程序之前，是否要询问我们
```



