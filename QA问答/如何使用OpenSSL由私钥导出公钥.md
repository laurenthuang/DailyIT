# Q: 如何使用OpenSSL由私钥导出公钥？

---
tags:
  - openssl
  - key
  - public key
  - private key
---
## 由私钥导出公钥
```shell
$ openssl pkey -in some_private_key.pem -pubout -outform PEM -out some_public_key.pem
```
