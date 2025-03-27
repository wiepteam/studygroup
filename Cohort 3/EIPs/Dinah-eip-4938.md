# EIP-4938: Removal of GetNodeData

Created on: 2022-03-23

Authors: Marius van der Wijden (@MariusVanDerWijden), Felix Lange <fjl@ethereum.org>, Gary Rong <garyrong@ethereum.org>

Requires the following: EIP-2464, EIP-2481

EIP-2464 is about transaction announcements and retrievals.  
It introduces `NewPooledTransactionHashes`, `GetPooledTransactions`, and `PooledTransactions`.

EIP-2481 is about introducing a request id for all requests of the eth protocol

### Back to EIP-4938

#### Abstract

The Ethereum Wire Protocol defines request and response messages for exchanging data between clients. The GetNodeData request retrieves a set of trie nodes or contract code from the state trie by hash. The proposal was to remove the GetNodeData and NodeData messages from the wire protocol.

#### Specification

Basically, Ethereum Wire Protocol is the set of rules that Ethereum nodes use to communicate with each other over the network. It defines how nodes exchange data, such as block information, transactions, and state data.

`GetNodeData` and `NodeData` are messages within the wire protocol that were used for retrieving specific data related to the Ethereum state trie. The state trie is a data structure that stores the current state of all Ethereum accounts.

`NodeData` and `GetNodeData` were concepts introduced in protocol version eth/63 to allow for a sync mode called `fast sync`, which downloads the Ethereum state without executing all blocks. This sync algorithm works by requesting all state trie nodes and contract codes by their hash.

#### Motivation for Change

These were some challenges.

Serving `GetNodeData` requests requires clients to store state as a mapping of hashes to trie nodes.
At the time of the proposal, some client implementations cannot serve `GetNodeData` requests because they do not store the state in a compatible way.
These were some of the motivations for removing the request type.

#### Result

This removal simplified the eth protocol and made it more efficient.
However, they were replaced with more modern syncing methods like "snap sync" (this is a synchronization method in Ethereum, designed to significantly speed up the process of a new node joining the network)
Basically, clients made use of the `GetByteCodes` and `GetTrieNodes` messages instead of `GetNodeData`. For more context, Bytecodes are the compiled smart contract code, and trie nodes are parts of the Merkle Patricia Trie that represents the ethereum state.

In summary, EIP-4938 is an EIP that focuses on refining the Ethereum wire protocol, specifically by removing the `GetNodeData` and `NodeData` messages.

##### General Implications of the EIP-4938

- **It Improved Network Efficiency:**
  By removing unnecessary messages can reduce network bandwidth usage and improve synchronization times.

- **Modernization of Syncing:**
  This EIP is part of a broader effort to modernize Ethereum's syncing mechanisms, making them more efficient and scalable.

- **Impact on Node Software:**
  Ethereum client software (like Geth or Nethermind) needs to be updated to comply with this change.

- **Required change from backward compatibility:**
  This EIP changes the eth protocol and requires rolling out a new version, eth/67. Supporting multiple versions of a wire protocol is possible. Rolling out a new version does not break older clients immediately, since they can keep using protocol version eth/66.

- **Does not require hard fork:**
  This EIP does not change consensus rules of the EVM and does not require a hard fork

Basically, EIP-4938 is a technical optimization that contributes to the ongoing evolution of the Ethereum network, making it more efficient for nodes to communicate and synchronize.
Reference:

- [EIP-4938](https://eips.ethereum.org/EIPS/eip-4938)
- [Ethereum Wire Protocol](https://github.com/ethereum/devp2p/blob/40ab248bf7e017e83cc9812a4e048446709623e8/caps/eth.md)
- [Snap Sync](https://docs.nethermind.io/fundamentals/sync/)
