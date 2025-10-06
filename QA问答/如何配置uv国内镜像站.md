# Q: 如何配置uv国内镜像站？

---
tags:
  - uv
  - mirror
  - setup
---

## `uv`
```shell
export UV_PYTHON_INSTALL_MIRROR="https://gh-proxy.com/github.com/indygreg/python-build-standalone/releases/download"
export UV_DEFAULT_INDEX="https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple"
```
