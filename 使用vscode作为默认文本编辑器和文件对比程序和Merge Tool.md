# 使用vscode作为默认文本编辑器、文件对比程序和Merge Tool

[参考答案链接](https://stackoverflow.com/questions/44549733/how-to-use-visual-studio-code-as-the-default-editor-for-git-mergetool)

#### 1. 安装 vscode

链接地址：https://code.visualstudio.com/

#### 2. 安装 code 命令到 PATH

macOS 安装 PATH 链接：https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line ，Windows 和 Linux 在安装软件时已自动配置好。

#### 3. 将 vscode 设置成默认的文本编辑器

```
$ git config --global core.editor "code --wait"
```

#### 4. 将 vscode 设置成默认的文件对比程序（Diff Tool）

```
$ git config --global diff.tool vscode
$ git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'
```

#### 5. 将 vscode 设置成默认的 Merge Tool 工具

```
$ git config --global merge.tool vscode
$ git config --global mergetool.vscode.cmd 'code --wait $MERGED'
```
