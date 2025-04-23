
# EIP-7594: PeerDAS - Peer Data Availability Sampling

Created on:	2024-01-12

Authors:	Danny Ryan, Dankrad Feist, Francesco D'Amato, Hsiao-Wei Wang

## Abstract

PeerDAS (Peer Data Availability Sampling) is a networking protocol that allows beacon nodes to perform data availability sampling (DAS) to ensure that blob data has been made available in the network while not requiring all nodes to download all blob data. PeerDAS utilizes gossip for distribution, discovery for finding peers of particular data custody, and peer requests for sampling.

DAS is a method of scaling data availability beyond the levels of EIP-4844. Providing additional data availability helps bring scale to Ethereum users in the context of layer 2 systems called “roll-ups” whose dominant bottleneck is layer 1 data availability.

## Specifications

The blobs introduced in EIP-4844 are extended using a one-dimensional erasure coding extension. Each row consists of the blob data combined with its erasure code. It is subdivided into cells, which are the smallest units that can be authenticated with their respective blob’s KZG commitments. Each column, associated with a specific gossip subnet, consists of the cells from all rows for a specific index. Each node is responsible for maintaining and custodying a deterministic set of column subnets and data as a function of their node ID.

Nodes find and maintain a diverse peer set and sample columns from their peers to perform DAS every slot.

A node can reconstruct the entire data matrix if it acquires at least 50% of all the columns. If a node has less than 50%, it can request the necessary columns from the peer nodes.

## References
- [eip-7594](https://eips.ethereum.org/EIPS/eip-7594)
- [Ethereum Magicians discussion](https://ethereum-magicians.org/t/eip-7594-peerdas-peer-data-availability-sampling/18215)
- [eip-specs](https://github.com/ethereum/consensus-specs/tree/b4188829b32139916127827c64ba17c923e66c3c/specs/_features/eip7594)
- [ethresear.ch article](https://ethresear.ch/t/peerdas-a-simpler-das-approach-using-battle-tested-p2p-components/16541)
- [Article by lighthouse](https://blog.sigmaprime.io/peerdas-distributed-blob-building.html)
- [Foundations of DAS](https://eprint.iacr.org/2023/1079.pdf)
- [A Documentation of Ethereum’s PeerDAS](https://eprint.iacr.org/2024/1362.pdf)
- [PeerDAS from scratch](https://hackmd.io/@manunalepa/peerDAS)


