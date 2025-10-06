# Q: 如何解决Git在企业内网中使用报SSL自签署证书错误的问题？

---
tags:
  - git
  - troubleshooting
---
# Git在企业内网中使用报SSL自签署证书错误

git clone时报错：
>SSL certificate problem: self-signed certificate in certificate chain

如果是Windows操作系统，可以在git-bash下执行如下命令解决：
```bash
$ git config --global http.sslBackend schannel
```
