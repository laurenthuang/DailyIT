# Q: 如何配置uv国内镜像站？

---
tags:
  - uv
  - mirror
  - setup
  - python
  - pypi
---

## `uv`本身安装

默认uv-installer.sh安装方式，需要配置GitHub的镜像
```shell
export UV_INSTALLER_GITHUB_BASE_URL="https://gh-proxy.com/github.com"
```

## 用 `uv` 安装python包

需要配置pypi的镜像
```shell
export UV_DEFAULT_INDEX="https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple"
```
