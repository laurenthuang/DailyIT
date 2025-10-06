# Q: 如何使用OpenSSL提取网站证书链到文件？

---
tags:
  - openssl
  - certificate
  - tls
  - website
  - extract
---
## 提取网站证书链到文件
```shell
$ echo | openssl s_client -showcerts -connect www.feistyduck.com:443 2>&1 | sed --quiet '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > feistyduck.chain
```
