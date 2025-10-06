# Q: 如何使用GDB查看代码和栈信息？

---
tags:
  - gdb
  - list
  - backtrace
  - frame
---
```shell
list
list lineno

info source

bt #backtrace当前thread的stack
frame #显示当前的stack frame
up #在当前stack中选择上一个frame
down #在当前stack中选择下一个frame

info args
info locals
```
