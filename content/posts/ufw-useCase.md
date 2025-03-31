---
author: "Simon"
title: "Ufw UseCase"
date: 2025-03-31T15:57:03+08:00
description: "Guide to emoji usage in Hugo"
tags: ["emoji"]
ShowToc: false
ShowBreadCrumbs: false
---

### in default

ufw is inactive

### usual setting

```
sudo ufw allow ssh
sudo ufw enable
```

### cheat sheet

```

sudo ufw allow 8000:10000/udp
sudo ufw allow 8899/tcp
sudo ufw allow from x.x.x.x to any port 27017
sudo ufw reload

sudo ufw status numbered


sudo ufw delete 2

sudo ufw delete allow 27017/tcp
sudo ufw delete out allow to 8.8.8.8 port 53 proto udp

# 原规则
sudo ufw allow from 192.168.1.100 to any port 27017 proto tcp

# 删除时必须完整匹配
sudo ufw delete allow from 192.168.1.100 to any port 27017 proto tcp

# 同时删除TCP和UDP规则
sudo ufw delete allow 27017/tcp
sudo ufw delete allow 27017/udp

sudo ufw reset  # 注意：这将清除所有配置！


sudo ufw disable
```
