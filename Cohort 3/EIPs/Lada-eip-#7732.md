# An overview of [EIP-7732: Enshrined Proposer-Builder Spearation](https://eips.ethereum.org/EIPS/eip-7732)

**Created**: 2024-06-28

**Authors**: Francesco D'Amato, Barnabé Monnot, Michael Neuder, Potuz, Terence Tsao

`Short description`

This EIP introduces a separation of builders and proposers of blocks. Thus, execution validation and consensus validation are spearated. This creates a new role of a builder of block and  a new duty of submitting payload attestations. This EIP can be considered as formalizing MEV-Boost's core principles at the protocol level. On the technical side, it involves changes to the Beacon chain, fork choice and p2p. It's  backward incompatible and must be accompanied by a hard fork. Block builders pay to proposers for choosing their block. Builders are staked in the beacin chain which allows for trustless payments. The protocol requires that funds are available before the execution payload is revealed. A subset of validators is assigned to the Payload Timeliness Committee which attests to whether a builder has revealed the committed execution payload in a timely fashion after the block proposer has chosen the builder's block. The following features of fork choice are guaranteed under this design: proposal unconditional payment, builder reveal safety and builder withhold safety. This EIP is compatible with Inclusion lists and Slot auctions.


The EIP is motivated by several facts. First, a lot of beacon block proposers outsource the construction of the execution payload to a third party. Second, validators have little time to perform state transition functions, check blob data availability and evaluate new head of the blockchain between receiving the full beacon block and attesting deadline. Finally, this EIP removes the need to use trusted middleware for block construction, prevents validators from missing attestations, removes the increased reorg likeliness of including blob transactions in blocks and allows for faster network propogation. 

`Additional information`
* [Ethereum magicians blog discussion](https://ethereum-magicians.org/t/eip-7732-enshrined-proposer-builder-separation-epbs/19634)
* [Post by @potus on hackmd](https://hackmd.io/@potuz/rJ9GCnT1C)
* [Full specification](https://github.com/ethereum/consensus-specs/pull/3828)
* [Peep an EIP episode](https://youtu.be/Wo7IEUCGRxU?feature=shared)
* [One of the breakout rooms](https://youtu.be/Z4u0sJQl3HU?feature=shared)
* [Short introduction](https://youtu.be/P2DkizLb79w?feature=shared)
* [Galaxy research](https://youtu.be/KiUYsZAfZtI?feature=shared)
* [Devcon talk](https://youtu.be/w-VwYHq1FA4?feature=shared)

