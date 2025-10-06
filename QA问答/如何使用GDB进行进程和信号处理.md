# Q: 如何使用GDB进行进程和信号处理？

---
tags:
  - gdb
  - process
  - signal
  - handle
---
```shell
info proc

info handle

handle SIGINT print stop pass
handle SIGINT print stop nopass
```
