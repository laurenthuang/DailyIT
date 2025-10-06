# Q: 如何解决LM-Studio（Windows版）下载模型失败的问题？

---
tags:
  - windows
  - lmstudio
  - nodejs
  - troubleshooting
---

## 报证书链存在自签署的证书

原因：nodejs建立tls连接时拒绝接受self signed certificate

解决方法
```cmd
> set NODE_TLS_REJECT_UNAUTHORIZED=0
> "LM Studio.exe"
```
