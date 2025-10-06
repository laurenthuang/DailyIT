# Q: 如何将SSH公钥添加到目标Linux主机？

---
tags:
  - ssh
  - public key
  - linux
  - authorized_keys
---
## 将公钥添加到目标主机
（假设文件名“id_rsa.pub”，并已上传）
```shell
cat id_rsa.pub >> ~/.ssh/authorized_keys
```
