---
author: "Simon"
title: "Docker"
date: 2023-08-14T16:50:53+08:00
description: "Guide to docker"
tags: ["docker"]
ShowToc: false
ShowBreadCrumbs: false
---

1. 打开一个 ubuntu 命令行，使用宿主机器的网络

```sh
docker run -it --network host ubuntu:20.04
```
