## 安装dos2unix

dos2unix 官网地址: [https://waterlan.home.xs4all.nl/dos2unix.html](https://waterlan.home.xs4all.nl/dos2unix.html)

### 在Linux上安装dos2unix

#### Ubuntu

##### 1.在 Terminal 中输入下面命令

```
$ sudo apt-get install dos2unix
```

### 在macOS上安装dos2unix

#### 1.安装[Homebrew](https://brew.sh)

```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### 2.安装dos2unix

```
$ brew install dos2unix
```

### 在Windows上安装dos2unix

>在Windows的MinGW64 Git Bash Here客户端上自带

## 使用dos2unix

文本文件在 DOS 和 UNIX 格式之间相互转换 

`dos2unix`: 将文本文件从 DOS 格式转换为 UNIX 格式

`unix2dos`: 将文本文件从 UNIX 格式转换为 DOS 格式

- 将 DOS 文件转换为 UNIX 格式

```
$ dos2unix <filename>...
```

- 将 UNIX 文件转换为 DOS 格式

```
$ unix2dos <filename>...
```

- 批量转换当前文件夹下的文件格式

```
$ find . -type f -print0 | xargs -0 dos2unix # 也可以是 unix2dos
```
