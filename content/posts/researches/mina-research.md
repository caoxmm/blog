---
author: "Simon"
title: "Mina Research"
date: 2023-07-06T10:20:02+08:00
description: "All things about mina"
tags: ["blockchain", "zk", "work", "layer-1"]
ShowToc: false
ShowBreadCrumbs: false
---

Mina is a layer-1 blockchain with a 22KB blockchain & zero knowledge smart contracts (“zkApps”) written in TypeScript.

### Wallet

currently only Auro Wallet for Chrome supports interactions with zkApps.
[Auro Wallet](https://www.aurowallet.com/)
[Auro Wallet 交互文档](https://docs.aurowallet.com/general/reference/api-reference/mina-provider/methods)

### Faucet

[Testnet Faucet](https://faucet.minaprotocol.com/)

### Quickstart

1. install the zkApp CLI and make the zk command available on your system

```bash
npm install -g zkapp-cli
```

2. create a new project

```bash
zk project hello-mina
```

3. config&deploy project

```bash
zk config
zk deploy
```

### how to compile

编译部署都是通过安装 zkapp-cli，来操作的，于是我们去查看了 zkapp-cli 的源码，由于 mina 的合约是 typescript 写的，所以我们也看到`src\lib\deploy.js`的 126 行：

```javascript
await sh("npm run build --silent");
```

然后在样例工程里面`package.jaon`查看 build 任务：

```json
   "build": "tsc",
```

从上述过程看出，mina 的合约编译完全是通过`tsc`来完成的,浏览器端本身不支持编译 typescript 语言的。

### how to deploy

官方教程部署是通过 zkapp-cli，然后源码是通过请求服务
