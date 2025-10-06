# Q: 如何结合利用mitm和wireshark？

---
tags:
  - wireshark
  - mitmproxy
  - tips
  - tls
---
## 记录TLS Master Key 供Wireshark使用

```shell
$ SSLKEYLOGFILE="$PWD/.mitmproxy/sslkeylogfile.txt" mitmproxy
```
