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

# utils/context.sol

```solidity
// SPDX-License-Identifier: MIT
// OpenZeppelin Contracts v4.4.1 (utils/Context.sol)

pragma solidity ^0.8.20;

/**
 * @dev Provides information about the current execution context, including the
 * sender of the transaction and its data. While these are generally available
 * via msg.sender and msg.data, they should not be accessed in such a direct
 * manner, since when dealing with meta-transactions the account sending and
 * paying for execution may not be the actual sender (as far as an application
 * is concerned).
 *
 * This contract is only required for intermediate, library-like contracts.
 */
abstract contract Context {
    function _msgSender() internal view virtual returns (address) {
        return msg.sender;
    }

    function _msgData() internal view virtual returns (bytes calldata) {
        return msg.data;
    }
}

```
