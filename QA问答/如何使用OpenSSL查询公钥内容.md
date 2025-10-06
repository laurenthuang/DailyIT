# Q: 如何使用OpenSSL查询公钥内容？

---
tags:
  - openssl
  - key
  - public key
  - modulus
  - exponent
---
## 查询公钥内容（modulus和exponent）
```shell
$ openssl rsa -in some_public_key.pem -pubin -text
RSA Public-Key: (2048 bit)
Modulus:
    00:cc:ba:33:06:53:1a:f8:9c:69:da:0f:35:ca:4f:
    90:22:b9:d2:02:67:43:a9:c8:7f:d4:25:be:7c:8c:
    73:a0:94:e1:0b:8d:0a:2b:cf:a4:1e:fa:d7:ec:b5:
    3a:48:4d:35:e3:cb:ec:22:28:f4:47:6e:33:6b:83:
    74:82:22:cf:67:c2:c6:9c:b9:56:30:d3:80:b3:20:
    6b:8d:b8:f7:e1:50:d1:b2:88:b2:ae:70:a8:27:ad:
    8a:ee:0a:85:72:cb:05:a9:67:85:e5:96:14:6c:f0:
    33:c2:eb:7b:4c:17:8a:3a:80:27:5e:08:8b:16:c8:
    04:55:66:0c:9f:37:48:a0:b2:a6:61:79:2e:14:de:
    9c:a3:45:5d:b7:b7:de:da:79:86:c6:44:52:21:66:
    4b:5d:ac:f6:a2:85:41:8a:99:80:77:61:df:5e:e3:
    cd:6c:ed:5f:d5:4a:73:e5:89:38:94:33:31:e8:02:
    7c:ab:17:c4:61:14:7a:33:89:57:dc:a2:0c:af:b4:
    01:82:82:6e:2a:39:04:7b:93:83:f0:5b:3c:2c:03:
    de:ff:25:93:5d:50:a7:b9:ea:b5:55:ee:75:2e:e7:
    17:e5:97:8b:62:b7:b2:b9:fc:1c:8d:c9:6d:21:d6:
    96:73:f8:51:00:f6:bd:44:90:7c:c4:9a:20:12:9f:
    0b:d1
Exponent: 65537 (0x10001)
writing RSA key
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAzLozBlMa+Jxp2g81yk+Q
IrnSAmdDqch/1CW+fIxzoJThC40KK8+kHvrX7LU6SE0148vsIij0R24za4N0giLP
Z8LGnLlWMNOAsyBrjbj34VDRsoiyrnCoJ62K7gqFcssFqWeF5ZYUbPAzwut7TBeK
OoAnXgiLFsgEVWYMnzdIoLKmYXkuFN6co0Vdt7fe2nmGxkRSIWZLXaz2ooVBipmA
d2HfXuPNbO1f1Upz5Yk4lDMx6AJ8qxfEYRR6M4lX3KIMr7QBgoJuKjkEe5OD8Fs8
LAPe/yWTXVCnueq1Ve51LucX5ZeLYreyufwcjcltIdaWc/hRAPa9RJB8xJogEp8L
0QIDAQAB
-----END PUBLIC KEY-----
```
