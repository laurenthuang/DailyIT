# Q: 如何使用ssh-keygen生成SSH密钥对？

---
tags:
  - ssh
  - keygen
  - key pair
---
## 客户端生成密钥对（假设512比特，ed25519算法）
```shell
ssh-keygen -b 512 -t ed25519
```
过程中，会提示输入
- 保存路径 (假设为"id_rsa"，最终会生成私钥“id_rsa”和公钥“id_rsa.pub”)
- 是否要加passphrase
