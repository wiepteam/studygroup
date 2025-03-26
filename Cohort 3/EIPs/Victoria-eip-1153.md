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


## Additional Resources
- [EIP-1153](https://eips.ethereum.org/EIPS/eip-1153)
- [Ethereum Magicians discussion](https://ethereum-magicians.org/t/eip-1153-transient-storage-opcodes/553)
- [Fan Page](https://www.eip1153.com/)
- [Transient Storage in Solidity 0.8.24](https://soliditylang.org/blog/2024/01/26/transient-storage/)