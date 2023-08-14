---
author: "Simon"
title: "Openzeppelin源码阅读总览"
date: 2023-08-04T10:14:49+08:00
description: "Openzeppelin 源码阅读"
tags: ["solidity", "ethereum"]
ShowToc: false
ShowBreadCrumbs: false
---

总体结构

<pre class="mermaid">
graph LR
A[openzeppelin-contracts] --> B[access] 
A --> C[finance] 
A --> D[governances]
A --> E[interfaces]
A --> F[metatx]
A --> G[mocks]
A --> H[proxy]
A --> I[security]
A --> J[token]
A --> K[utils]
A --> L[vendor]
</pre>
