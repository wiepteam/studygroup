# EIP-4938: Removal of GetNodeData

Created on: 2022-03-23

Authors: Marius van der Wijden (@MariusVanDerWijden), Felix Lange <fjl@ethereum.org>, Gary Rong <garyrong@ethereum.org>

Requires the following: EIP-2464, EIP-2481

EIP-2464 is about  transaction announcements and retrievals.   
It introduces `NewPooledTransactionHashes`, `GetPooledTransactions`, and `PooledTransactions`.

EIP-2481 is about introducing a request id for all requests of the eth protocol

### Back to EIP-4938


#### Abstract

The Ethereum Wire Protocol defines request and response messages for exchanging data between clients. The GetNodeData request retrieves a set of trie nodes or contract code from the state trie by hash. The proposal was to remove the GetNodeData and NodeData messages from the wire protocol.


#### Specification 

Basically, Ethereum Wire Protocol is the set of rules that Ethereum nodes use to communicate with each other over the network. It defines how nodes exchange data, such as block information, transactions, and state data.

`GetNodeData` and `NodeData` are messages within the wire protocol that were used for retrieving specific data related to the Ethereum state trie. The state trie is a data structure that stores the current state of all Ethereum accounts.

EIP-4938 is an EIP improvement protocol that focuses on refining the Ethereum wire protocol, specifically by removing the `GetNodeData` and `NodeData` messages. 

##### Implications of the EIP-4938 

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


