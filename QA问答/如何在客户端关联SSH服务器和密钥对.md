# Q: 如何在客户端关联SSH服务器和密钥对？

---
tags:
  - ssh
  - client
  - config
  - identityfile
---
## 客户端建立主机和密钥对关联

编辑`C:\Users\用户名\.ssh\config`文件
```
Host your_alias
    HostName 服务器地址
    Port 端口号
    User 用户名
    IdentityFile C:\Users\用户名\.ssh\id_rsa
```
