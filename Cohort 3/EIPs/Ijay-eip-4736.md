# EIP-4736: Consensus Layer Withdrawal Protection

**Number**: 4736  
**Name**: Consensus Layer Withdrawal Protection  
**Authors**: Benjamin Chodroff (@benjaminchodroff), Jim McDonald (@mcdee)  
**Created**: 2022-01-30  

## Description
EIP-4736 introduces an optional security enhancement for Ethereum’s consensus layer. It addresses the risk that arises if a validator’s mnemonic phrase becomes compromised. The core idea is to create a "social consensus" mechanism without altering Ethereum's core consensus protocol, favoring legitimate mnemonic holders in the event of a conflict. By leveraging the original execution layer (EL) deposit address and signed BLSToExecutionChange messages, this proposal enables node operators to filter, prioritize, and broadcast legitimate withdrawal credential updates, reducing the chances of an attacker successfully claiming withdrawals.

The motivation stems from the lack of absolute security guarantees before validator withdrawals became possible at the Capella hard fork. Before Capella, validators could not verify if their mnemonic or withdrawal keys had been compromised. By optionally loading verified BLSToExecutionChange messages into beacon node clients, node operators and client teams can help protect the network against large-scale compromise risks — without needing any protocol-level changes.

## Additional Resources
- [Official EIP-4736 Specification](https://eips.ethereum.org/EIPS/eip-4736)
- Ethereum Magicians discussion on [Validator Withdrawal Protection](https://ethereum-magicians.org/)
- Research and community thoughts on [Ethereum Research Forums](https://ethresear.ch/)
- Capella upgrade overview and withdrawal changes ([Ethereum Foundation Blog](https://blog.ethereum.org/))
- EthStaker community discussions on validator key management ([EthStaker Reddit](https://www.reddit.com/r/ethstaker/))

### Copyright
Copyright and related rights waived via [CC0](https://eips.ethereum.org/LICENSE)