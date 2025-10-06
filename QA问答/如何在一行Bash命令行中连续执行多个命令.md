# Q: 如何在一行Bash命令行中连续执行多个命令？

---
tags:
  - linux
  - shell
  - bash
  - tips
---


依次执行，不管前一个命令成功与否
```bash
# cmd1; cmd2
$ cd myfolder; ls   # no matter cd to myfolder successfully, run ls
```

前一个命令成功，才执行后一个
```bash
# cmd1 && cmd2
$ cd myfolder && ls  # run ls only after cd to myfolder
```

前一个命令失败，则执行后一个命令
```bash
# cmd1 || cmd2
$ cd myfolder || ls  # if failed cd to myfolder, `ls` will run
```
