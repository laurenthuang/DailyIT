# Q: 如何配置Pip国内镜像站？

---
tags:
  - pip
  - mirror
  - setup
---

## `pip`

方法一、编辑`~/.pip/pip.conf`
```toml
[global]
index-url = http://mirrors.aliyun.com/pypi/simple/

[install]
trusted-host=mirrors.aliyun.com
```

方法二
```shell
pip config set global.index-url https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple
```
