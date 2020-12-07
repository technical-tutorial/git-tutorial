# 常见问题与解答

### 1.如何解决 git status 显示中文乱码？

> 在默认情况下，中文文件名在工作区中输出显示为八进制的字母编码，导致不能正确显示中文名

在 Git Bash Here 中输入命令:

```
git config --global core.quotepath false
```
