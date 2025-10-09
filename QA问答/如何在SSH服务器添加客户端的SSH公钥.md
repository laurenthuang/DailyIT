# Q: 如何在SSH服务器添加客户端的SSH公钥？

---
tags:
  - ssh
  - public key
  - linux
  - server
---
## 将客户端公钥添加到配置文件
（假设文件名“id_rsa.pub”，并已上传）
```shell
cat id_rsa.pub >> ~/.ssh/authorized_keys
```
