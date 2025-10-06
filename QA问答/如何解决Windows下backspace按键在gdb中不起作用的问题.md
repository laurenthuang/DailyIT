# Q: 如何解决Windows下backspace按键在gdb中不起作用的问题？

---
tags:
  - windows
  - gdb
  - troubleshooting
---
在gdb 9.0以后版本，会出现在windows下启动gdb，backspace按键不起作用的问题。老版本反而正常。

通过在启动gdb前，设置环境变量解决：
```shell
set TERM=#win32con
```
