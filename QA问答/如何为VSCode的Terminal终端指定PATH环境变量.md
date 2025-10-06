# Q: 如何为VSCode的Terminal终端指定PATH环境变量？

---
tags:
  - vscode
  - tips
---
例如：将node.js开发环境的`./node_modules/.bin`加入`PATH`搜索路径
```json
{
  "terminal.integrated.env.windows": {
    "PATH": "./node_modules/.bin;${env:PATH}"
  },
  "terminal.integrated.env.osx": {
    "PATH": "./node_modules/.bin;${env:PATH}"
  },
  "terminal.integrated.env.linux": {
    "PATH": "./node_modules/.bin;${env:PATH}"
  },
}
```
