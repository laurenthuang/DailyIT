# Q: 如何使用GDB进行线程操作？

---
tags:
  - gdb
  - thread
  - scheduler-locking
---
```shell
info threads #一览所有thread
thread #显示当前选择的thread的threadno

thread threadno #选择切换到threadno

thread apply threadno1 [threadno2 ...] command
thread apply all command

break linespec thread threadno
break linespec thread threadno if ...

show scheduler-locking
set scheduler-locking on
set scheduler-locking off
set scheduler-locking step
```
