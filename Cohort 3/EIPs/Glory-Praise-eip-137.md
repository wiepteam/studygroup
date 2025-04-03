## ERC-137: [Ethereum Domain Name Service](https://eips.ethereum.org/EIPS/eip-137)

**EIP Name:** Ethereum Domain Name Service(ENS)
**EIP Number:** 137
**Authors:** Nick Johnson
**Created:** 2016-04-04

EIP-137 introduced the **Ethereum Name Service (ENS)**, a decentralized system designed to map human-readable names (e.g., `alice.eth`) to machine-readable identifiers like Ethereum addresses, content hashes, or metadata. The proposal aimed to solve usability challenges in Ethereum by replacing cumbersome 42-character hexadecimal addresses with memorable names. This simplifies transactions, reduces errors, and enhances interoperability across dApps.

The ENS operates similarly to the Domain Name System (DNS) but uses Ethereum smart contracts for decentralized governance. Key components include:

- A registry to track domain ownership.
- Resolver contracts to translate names into addresses or other data.
- A hierarchical structure (e.g., `.eth` domains) with support for subdomains.

## Why It Matters

ENS has become a cornerstone of Ethereum’s infrastructure, with over 2.8 million registered domains as of 2025. It supports decentralized websites (via IPFS/Arweave), cross-chain addresses, and identity verification, cementing its role as critical Web3 middleware.

## Additional Resources

### 1. [ENS Documentation](https://docs.ens.domains/)

- Explains ENS architecture, technical specifications, and integration guides for developers.

### 2. [Ethereum Domain Name Service](https://eips.ethereum.org/EIPS/eip-137)

- EIP 137 specification documentation.

### 3. [ENS Contracts (GitHub)](https://github.com/ensdomains/ens-contracts)

- Open-source code for ENS core contracts, including the registry and resolver logic.

### 4. [How ENS is taking Ethereum to the rest of the Internet - Devcon5 (YouTube)](https://youtu.be/lys0yVxQt-o?si=vQ2uKHKVImBu0PEY)

- A talk by Brantly Millegan explaining ENS.

### 5. [ENS Roadmap Update (2023)](https://ens.domains/blog/)

- Covers recent upgrades like Layer 2 support, DNS integration, and expanded metadata capabilities.

---
