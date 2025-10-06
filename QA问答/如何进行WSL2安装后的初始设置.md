# Q: 如何进行WSL2安装后的初始设置？

---
tags:
  - windows
  - wsl
  - linux
  - setup
---

编辑`/etc/wsl.conf`使能和Windows应用的互操作，但不要导入Windows下的`PATH`环境变量，添加：
```toml
[interop]
enabled = true
appendWindowsPath = false
```

设置boot的一些参数：
```toml
[boot]
systemd = true
command = mount --make-rshared /
```
