# Q: 如何配置Git国内镜像站？

---
tags:
  - git
  - mirror
  - setup
---

## `github`

```shell
# gh-proxy为例
    # 使用镜像
git config --global url."https://gh-proxy.com/".insteadOf "https://"
    # 不使用
git config --global url."https://".insteadOf "https://gh-proxy.com/"
# gitclone.com为例
    # 使用镜像
git config --global url."https://gitclone.com/".insteadOf "https://"
```
