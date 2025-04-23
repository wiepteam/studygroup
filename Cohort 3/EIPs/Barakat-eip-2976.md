
### EIP-2976: Typed Transactions over Gossip  

**AUTHORS:** Micah Zoltu (@MicahZoltu)

**DATE Created**	2020-09-13

**CATEGORY:** Networking

**STATUS:** Final

**Requires:** EIP-2718

This eip adds support for transmission of typed transactions over devp2p. Its purpose is to allow Ethereum nodes 
to gossip typed transactions over the peer-to-peer network (devp2p), instead of just legacy transactions.

Typed transactions use a TransactionType || TransactionPayload format unlike the legacy transactions. 

This enables support
 for newer transaction types (like EIP-1559) without changing the devp2p version. Nodes can start supporting typed tx gossip
 as soon as they support the transaction type, even before forks activate them.


- If a node receives a transaction with an unknown type, it should disconnect from the sender. this could prevent DOS attack

- Clients must not send typed transactions before the fork block where they become valid.

- Typed txs are now accepted in messages like Transactions, BlockBodies, NewBlock, and Receipts.


Why This Matters
EIP-2718 introduced typed transactions, but this EIP makes them gossipable, allowing miners and validators to see and include them in blocks.

It ensures Ethereum can evolve transaction formats without needing devp2p protocol upgrades each time.

Although, Legacy transaction formats are still supported.No changes required for nodes that don't support new tx types,
 they will just disconnect from those who do.

**REFERENCES**

- [EIP-2976](https://eips.ethereum.org/EIPS/eip-2976)

- [Ethereum magicians](https://ethereum-magicians.org/t/eip-2976-eth-typed-transactions-over-gossip/4610)

- [Eip specs](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-2976.md)