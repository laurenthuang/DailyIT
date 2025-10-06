# Q: 如何修改目标Linux主机的sshd配置？

---
tags:
  - ssh
  - linux
  - sshd_config
---
## 修改目标主机的sshd配置
```shell
PubkeyAuthentication yes
```

（可选）禁用root账号登录
```shell
PermitRootLogin no
```

（可选）禁用密码登录
```shell
PasswordAuthentication no
PermitEmptyPasswords no
```

重启sshd服务
```shell
systemctl reload sshd.service
```
