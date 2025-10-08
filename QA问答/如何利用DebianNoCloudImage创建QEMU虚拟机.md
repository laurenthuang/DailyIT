# Q: 如何利用DebianNoCloudImage创建QEMU虚拟机？

---
tags:
  - linux
  - qemu
  - tips
---
## 步骤1
```shell
$ wget https://cloud.debian.org/images/cloud/bullseye/latest/debian-11-nocloud-arm64.qcow2
```

## 步骤2
```shell
$ qemu-system-x86_64 -m 1G -smp 2 -nographic -device e1000,netdev=net0 -netdev user,id=net0,hostfwd=tcp::2222-:22 -hda debian-11-nocloud-arm64.qcow2
```
等待提示符，用root登陆（无密码）

## 步骤3 增加 admin 用户
```shell
$ adduser <user>
...
$ usermod -aG sudo <user>
```

## 步骤4 禁止 root 用密码或口令登录
编辑`/etc/passwd`的 root 对用行，将`/bin/bash改为/sbin/nologin`，再执行

锁定root账户的密码认证。具体实现上它会在 shadow 文件中 root 的加密密码字段前加上一个感叹号（!），使得基于密码的认证失败，从而阻止通过密码交互式登录（例如控制台或使用密码的 SSH 登录）。
```shell
$ usermod -L root
```

## 步骤3 禁止 ssh 客户端用密码或口令登录
更改/etc/ssh/sshd_config，设置：
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
