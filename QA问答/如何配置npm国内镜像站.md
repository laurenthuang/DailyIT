# Q: 如何配置npm国内镜像站？

---
tags:
  - npm
  - mirror
  - setup
---

## `npm`

临时更改为 阿里源
```shell
npm config set registry https://registry.npmmirror.com
```

全局切换为 阿里源
```shell
npm install <package> --registry=https://registry.npmmirror.com
```
