---
author: "Simon"
title: "Rust Env"
date: 2024-03-09T03:50:28+08:00
description: "Guide to emoji usage in Hugo"
tags: ["emoji"]
ShowToc: false
ShowBreadCrumbs: false
---

### Rust 在 ubuntu 下环境搭建

1. 安装 C 语言编译器：
   Rust 对运行环境的依赖和 Go 语言很像，几乎所有环境都可以无需安装任何依赖直接运行。但是，Rust 会依赖 libc 和链接器 linker。所以如果遇到了提示链接器无法执行的错误，你需要再手动安装一个 C 语言编译器：

- macOS 下：

```
xcode-select --install
```

- Linux 下：

```
// Linux 用户一般应按照相应发行版的文档来安装 GCC 或 Clang。
// 例如，如果你使用 Ubuntu，则可安装 build-essential。

apt install build-essential
```

2. 安装 rustup

```
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

3. 安装 nvm

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

source ~/.bashrc

nvm ls-remote
nvm install ...
```
