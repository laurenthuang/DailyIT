# Q: 如何搭建TypeScripty开发环境？

---
tags:
  - nodejs
  - setup
---
## 在当前开发目录中搭建环境

前提：Node.js 已安装

```shell
npm install typescript --save-dev
```
`--save-dev` 代表安装到当前开发目录下，而不是`--global`

```shell
npm init
```
初始化开发目录，生成 `package.json`   

```shell
npm install ts-node --save-dev
```
`ts-node`用于在node.js中直接运行typscript脚本,   

```shell
npm install @types/node
```
这个包定义了node.js里的类型信息，可以帮助typescript开发工具提供代码提示、代码补全功能
