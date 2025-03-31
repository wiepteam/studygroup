# EIP-1153: Transient storage opcodes

Created	2018-06-15

Authors	Alexey Akhunov [@AlexeyAkhunov](https://github.com/AlexeyAkhunov), Moody Salem [@moodysalem](https://github.com/moodysalem)

EIP-1153 introduces transient storage to the Ethereum Virtual Machine (EVM). It adds two new opcodes, TSTORE and TLOAD, which enable temporary storage that only persists within a single transaction.

This proposal introduces transient storage opcodes, which manipulate state that behaves identically to storage, except that transient storage is discarded after every transaction, and TSTORE is not subject to the gas stipend check as defined in EIP-2200. In other words, the values of transient storage are never deserialized from storage or serialized to storage. Thus transient storage is cheaper since it never requires disk access. Transient storage is accessible to smart contracts via 2 new opcodes, TLOAD and TSTORE, where “T” stands for "transient:"

## Key Features of EIP-1153:

1. **Transient Storage**: 
   - Unlike regular storage (`SSTORE`), transient storage is **not persistent across transactions**. It resets at the end of a transaction, making it useful for temporary data.

2. **Cheaper than SSTORE**: 
   - `TSTORE` and `TLOAD` are cheaper than modifying persistent storage, reducing gas costs.

3. **Optimized Use Cases**:
   - **Reentrancy Locks**: Prevents reentrancy without modifying state storage.
   - **Temporary Caching**: Storing intermediate values within a transaction.
   - **Optimized Contract Interactions**: Improves efficiency in multi-call contract executions.



## Why Does EIP-1153 Matter?

- **Gas Efficiency**: Since it avoids costly state writes, it lowers transaction fees.
- **More Secure Reentrancy Guards**: Contracts like those using OpenZeppelin's `ReentrancyGuard` could use `TSTORE` instead of storage variables.
- **Better Multi-Call Logic**: It allows smart contracts to manage temporary variables efficiently.

EIP-1153 is particularly useful for **DeFi protocols**, **rollups**, and **contract optimizations** where gas savings and temporary state tracking are important.

## EIP-1153: Does Transient Storage Contradict Blockchain Principles?

## Is Transient Storage Against Blockchain’s Core Ideas?  
At first glance, transient storage might seem to contradict blockchain’s core principle of **immutability**, where data is meant to last forever. However, EIP-1153 **does not** violate this principle because:  

### 1. Blockchain Still Remains Immutable
- Transient storage (`TSTORE` and `TLOAD`) exists **only within a single transaction** and is **not written to permanent blockchain storage**.  
- Even though the data disappears after a transaction ends, the transaction itself (and its effects) **remain on-chain and verifiable**.  

### 2. Solving Temporary Data Needs Efficiently
- Some operations, like managing **reentrancy locks** or **caching intermediate values**, require **temporary** storage.  
- Without transient storage, developers would need to use **expensive storage operations (`SSTORE/SLOAD`)** or inefficient workarounds (like passing data via function parameters).  

### 3. Cost and Performance Improvements
- Regular storage in Ethereum is costly because it must be **persisted across blocks and retrieved later**.  
- EIP-1153 introduces a **gas-efficient alternative** for temporary data, making transactions cheaper without affecting **long-term blockchain integrity**.  

---

## Breaking Down the Motivation of EIP-1153 

### **1️⃣ Inter-Frame Communication in Ethereum Transactions**  
Ethereum transactions involve **nested execution frames**, especially when a contract calls another contract using `CALL` or `DELEGATECALL`.  

🔹 **Problem:**  
- Contracts within the same transaction **cannot easily share temporary data** across these execution frames.  
- **Current Solutions:**  
  - **Function Parameters (CALL inputs/outputs):** Unreliable if intermediate contracts are untrusted.  
  - **Storage (`SSTORE/SLOAD`):** Secure but **expensive** due to high gas costs.  

 **EIP-1153 provides a middle ground:** It allows **secure** and **low-cost** temporary data storage within a transaction.  

---

### **2️⃣ Gas Refund Issues Due to [EIP-3529](https://eips.ethereum.org/EIPS/eip-3529)**  
- **Before EIP-3529 (London Hard Fork):** Developers could manipulate gas refunds by writing and clearing storage.  
- **After EIP-3529:** Refunds are limited to **20% of gas spent in a transaction** to prevent gas refund exploits.  
- **Impact:**  
  - Makes reentrancy locks and other **transient storage use cases more expensive** with `SSTORE/SLOAD`.  
  - A simple lock using storage (`SSTORE`) now requires **80k gas** worth of other operations to get a full refund.  

 **EIP-1153 avoids this by removing the need for storage refunds entirely.**  

---

## Why Transient Storage is More Efficient?
- **No Need to Load From Storage:** Unlike `SSTORE`, `TSTORE` does not read an existing storage value (it’s always `0` by default).  
- **Simpler Gas Rules:** No need to refund gas, making execution and gas calculation **more predictable and efficient**.  

---

## Conclusion: EIP-1153 Aligns with Blockchain Principles
- It does **not** affect blockchain immutability or long-term data storage.  
- It makes Ethereum **more efficient** by **reducing gas costs** and **improving contract execution**.  
- It introduces a secure and gas-efficient way to handle **temporary** data needs.  

---


## Additional Resources
- [EIP-1153](https://eips.ethereum.org/EIPS/eip-1153)
- [Ethereum Magicians discussion](https://ethereum-magicians.org/t/eip-1153-transient-storage-opcodes/553)
- [Fan Page](https://www.eip1153.com/)
- [Transient Storage in Solidity 0.8.24](https://soliditylang.org/blog/2024/01/26/transient-storage/)