# Q: 如何在Proxmox中添加PAM管理员？

---
tags:
  - bash
  - shell
  - linux
  - proxmox
---
（假设root账号登录了主机的bash shell）
```shell
adduser <user>

pveum user add <user>@pam
pveum user list

pveum acl modify <PATH> --roles PVEAdmin --users <user>@pam

```
