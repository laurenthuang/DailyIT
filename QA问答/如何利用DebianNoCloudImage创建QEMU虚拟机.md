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

## 步骤3
增加admin用户
```shell
$ adduser <user>
...
$ usermod -aG sudo <user>
```
编辑/etc/passwd的root对用行，将/bin/bash改为/sbin/nologin，再执行
```shell
$ usermod -L root
```

## 步骤3
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
