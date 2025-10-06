# Q: 如何在cp或mv命令中利用shell的花括号扩展功能？

---
tags:
  - bash
  - linux
  - shell
  - tips
---
可以参考如下例子
```shell
$ sudo mv /etc/apt/apt.conf.d/proxy.conf{,.bak}
```

```shell
$ echo a{d,c,b}e
ade ace abe
```
