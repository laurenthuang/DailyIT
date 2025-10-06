# Q: 如何更改container的存储路径？

---
tags:
  - podman
  - container
  - tips
---
## Podman更改imageroot路径

root用户在`/etc/containers/storage.conf`

非特权用户创建、编辑`$HOME/.config/containers/storage.conf`
```toml
[storage]
driver = "overlay"
imageroot = "..."
```
