---
author: "Simon"
title: "ubuntu cheatSheet"
date: 2023-08-14T16:50:53+08:00
description: "Guide to ubuntu"
tags: ["ubuntu"]
ShowToc: false
ShowBreadCrumbs: false
---

1. 打开一个 ubuntu 命令行，使用宿主机器的网络

```sh
docker run -it --network host ubuntu:20.04
```

2. 安装 go

```sh
apt update
apt install wget
cd ~
wget https://go.dev/dl/go1.21.0.linux-amd64.tar.gz
rm -rf ~/go && tar -C ~ -xzf go1.21.0.linux-amd64.tar.gz
echo "export GOPATH=$HOME/go" >> ~/.bashrc
source ~/.bashrc
echo "export GOBIN=$GOPATH/bin" >> ~/.bashrc
source ~/.bashrc
echo "export PATH=$PATH:$GOBIN" >> ~/.bashrc
source ~/.bashrc
go version
```
