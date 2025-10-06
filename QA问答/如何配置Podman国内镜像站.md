# Q: 如何配置Podman国内镜像站？

---
tags:
  - podman
  - mirror
  - setup
---

## `Podman`

编辑 `/etc/containers/registries.conf`
```toml
unqualified-search-registries = ["docker.io"]
[[registry]]
prefix = "docker.io"
location = "docker.m.daocloud.io"
insecure = true

[[registry.mirror]]
...

```


国内dockerhub镜像：
https://www.wangdu.site/course/2109.html
