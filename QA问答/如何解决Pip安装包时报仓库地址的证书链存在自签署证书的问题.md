# Q: 如何解决Pip安装包时报仓库地址的证书链存在自签署证书的问题？

---
tags:
  - bash
  - linux
  - troubleshooting
  - pip
---

原因：内网代理服务器替换了仓库地址的根证书

通过增加命令参数`--trusted-host <仓库域名>`解决：
```bash
$ pip install oneccl_bind_pt --extra-index-url https://pytorch-extension.intel.com/release-whl/statble/cpu/us/ --trusted-host pytorch-extension.intel.com 
```
