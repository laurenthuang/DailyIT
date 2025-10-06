# Q: 如何利用Tree命令显示目录树？

---
tags:
  - linux
  - shell
  - tips
---
## 仅显示目录树，不含文件名
```shell
tree -d /SOME_PATH | less
```

## 最多显示2级目录
```shell
tree -L 2 /SOME_PATH
```
