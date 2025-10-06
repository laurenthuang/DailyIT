# Q: 如何解决Obsidian无法联网的问题？

---
tags:
  - obsidian
  - troubleshooting
---
## 问题根源1

由于网关或者防火墙阻止了内网设备对外网的直接访问。

需要在启动Obisidian时设置proxy参数：
```shell
obsidian.exe --proxy=socks://<server name or ip>:<port>
```
