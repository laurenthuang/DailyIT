# Q: 如何使用OpenSSL查看网站证书链？

---
tags:
  - openssl
  - certificate
  - tls
  - website
---
## 查看网站证书链（及握手信息）
```shell
$ echo | openssl s_client -showcerts -connect www.feistyduck.com:443 2>&1
```
