# Q: 如何输出Linux命令行的历史并重复执行？

---
tags:
  - tips
  - shell
  - linux
  - bash
---
## 查询上10次记录，并重复执行选取的历史命令
```bash
$ history
 1413  ll
 1414  pwd
$ !1413
```
说明：这里的效果就是重复执行了命令`ll`
