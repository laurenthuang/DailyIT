# Q: 如何使用OpenSSL进行rsa-pss验签？

---
tags:
  - openssl
  - rsa-pss
  - signature
  - verify
---
## 使用rsa-pss验签
```shell
$ openssl dgst -verify some_public_key.pem -signature some_binary_signature_file -sigopt rsa_padding_mode:pss some_binary_file
```
