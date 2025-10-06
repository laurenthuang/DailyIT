# Q: 如何使用OpenSSL将PEM格式证书转为DER格式？

---
tags:
  - openssl
  - certificate
  - pem
  - der
---
## 将PEM格式证书转为DER格式
```shell
$ openssl x509 -outform der -in <CERTIFICATE>.pem -out <CERTIFICATE>.der
```
