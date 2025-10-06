# Q: 如何使用OpenSSL查看网站证书？

---
tags:
  - openssl
  - certificate
  - tls
  - website
---
## 查看网站证书
```shell
$ echo | openssl s_client -connect www.feistyduck.com:443 2>&1 | openssl x509 -noout -text -fingerprint -sha256
```
