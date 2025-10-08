# Q: 如何加固Linux中root账户？

---
tags:
  - linux
  - account-management
  - security
---

## ⚠️务必先添加 admin 用户
```shell
$ adduser <user>
...
$ usermod -aG sudo <user>
```

## 禁止 root 用密码或口令登录
编辑`/etc/passwd`的 root 对应行，将`/bin/bash`改为`/sbin/nologin`，再执行

锁定root账户的密码认证。具体实现上它会在 shadow 文件中 root 的加密密码字段前加上一个感叹号（!），使得基于密码的认证失败，从而阻止通过密码交互式登录（例如控制台或使用密码的 SSH 登录）。
```shell
$ usermod -L root
```

## 禁止 SSH 客户端用 root 密码或口令登录
更改`/etc/ssh/sshd_config`，设置：
```shell
PermitRootLogin no
PasswordAuthentication yes
```

重新配置openssh-server
```shell
$ dpkg-reconfigure openssh-server
...
$ systemctl restart sshd
```
