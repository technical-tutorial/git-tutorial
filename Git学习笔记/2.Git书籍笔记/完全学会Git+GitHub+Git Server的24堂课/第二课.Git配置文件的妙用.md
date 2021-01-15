# 2.0.Git配置文件的妙用

- **Git 有三个不同级别的配置文件，他们有不同的优先权，高优先权文件的设置项会覆盖低优先权文件中相同的设置项**

- **Git 中三个不同级别的配置文件，并按照优先权从高至低排序如下:**

  - **文件夹中 “.git” 子文件夹内的 config 文件**（说明：该配置文件具有最高优先权，它将覆盖其他配置文件中相同的设置项）
  - **登录用户的 home directory 中的 .gitconfig 文件**（说明：只有在前一个配置文件中没有设置的项，该配置文件的设置才会生效，并且该配置文件只对登录用户有效）
  - **Git 程序的安装目录中的 etc/gitconfig 文件**（说明：只有在前两个配置文件中没有设置的项，这个配置文件的设置才会生效，这是公用的配置文件，它对所有登录用户和所有 Git 文档库有效。Linux 系统的配置文件所在位置: /etc/gitconfig，macOS 系统的配置文件所在位置：/usr/local/etc/gitconfig）

# 2.1.git config 指令的用法

- **显示三个配置文件中所有的设置项，它的顺序是先显示优先权最低的设置，如下图所示：**

![微信截图_20210105144150](https://user-images.githubusercontent.com/27407218/103615701-fa073680-4f65-11eb-8ea4-b04d40719b93.png)

- **通过 “git config” 指令的选项来读写不同级别的配置文件**
  - **--global** 使用全局配置文件(表示 home directory 中的 .gitconfig 配置文件，即 ~/.gitconfig)
  - **--system** 使用系统级配置文件(表示Git 安装目录下的 etc/gitconfig 配置文件，Linux 系统的配置文件所在位置：/etc/gitconfig，macOS 系统配置文件所在位置：/usr/local/etc/gitconfig)

- **如果要删除配置文件中的设置项，可以使用 “--unset” 选项，例如: `$ git config --global --unset user.name`** 

- **git 指令的 “长” 选项和 “短” 选项说明：**

  其实使用一个 “连字符” 开头的选项只是简便的形式，我们也可以把它换成完整的形式。简便形式只是缩短指令的长度，提高输入的方便性，但并非每一个选项都有简便形式。
  
  例子：`$ git commit -m '说明'` 的完整形式是 `git commit --message='说明'`（选项后面的 “=” 可以省略）
  
- **定义指令别名的方法如下：**
   ```
   $ git config alias.指令别名 '正式的指令和选项' # 指令别名不可以包含空格
    ```
   示例：
   ```
   $ git config alias.con 'config -l'
   ```
  那么执行 `$ git con` 相当于执行 `$ git config -l`

- **删除某个别名使用 “--unset” 选项：**
  ```
  $ git config --unset alias.con
  ```
  
# 2.2.修改默认的文本编辑器和文件对比程序

- **[详细的 core.editor 设置命令列表](https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Setup-and-Config)**

- **git diff 指令用来执行文件对比的功能，它可以在工作区、暂存区和 Git 仓库之间的文件对比差异。**

- **解读 “git diff” 指令输出:**

    ```
    $ git diff poem.txt
    diff --git a/poem.txt b/poem.txt  # “a/文件名” 表示 Git 仓库或索引中的文件（加上 --staged 选项时，表示 Git 仓库中的文件），“b/文件名” 表示工作区中的文件（加上 --staged 时，表示索引区中的文件）
    index fe09ad2..9a5507e 100644 # 
    --- a/poem.txt # “-” 表示 a 文件
    +++ b/poem.txt # “+” 表示 b 文件
    @@ -1,3 +1,3 @@ # 从该行开始才表示文件的差异，“-1,3” 表示 a 文件中从第一行开始的后面 3 行，“-” 只是表示 a 文件。“+1,3” 表示 b 文件中从第一行开始的后面 3 行，“+” 只是表示 b 文件。
    -2222 # 以 “-” 号开头表示从 a 文件变成 b 文件的时候，这一行被删除
     3333 # 没有正负号开头的部分表示没有被修改
     5555
    +4444 # 以 “+” 号开头则表示从 a 文件变成 b 文件的时候，这一行被加入
    ```
    
- **“git diff” 指令显示的信息中可能包含多段以 “@@” 开头的部分，这种情况表示文件中有多个段落都被修改过，每一个段落的差异都是用相同的方式描述**
