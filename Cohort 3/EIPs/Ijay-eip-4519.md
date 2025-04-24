# EIP 4519: Non-Fungible Tokens Tied to Physical Assets
### Interface for non-fungible tokens representing physical assets that can generate or recover their own accounts and obey users.
#### Authors: Javier Arcenegui (@Hardblock-IMSE-CNM),       Rosario Arjona (@RosarioArjona), Roberto Román <roman@imse-cnm.csic.es>, Iluminada Baturone (@lumi2018)
#### Created	2021-12-03
#### Requires	EIP-165, EIP-721

### Abstract
This EIP standardizes an interface for non-fungible tokens representing physical assets, such as Internet of Things (IoT) devices. These NFTs are tied to physical assets and can verify the authenticity of the tie. They can include an Ethereum address of the physical asset, permitting physical assets to sign messages and transactions. Physical assets can operate with an operating mode defined by its corresponding NFT.

### Motivation
This standard was developed because EIP-721 only tracks ownership (not usage rights) and does not track the Ethereum addresses of the asset. The popularity of smart assets, such as IoT devices, is increasing. To permit secure and traceable management, these NFTs can be used to establish secure communication channels between the physical asset, its owner, and its user.

### Why It Matters
1. Solves a Key Limitation of Standard NFTs
EIP-721 NFTs only track who owns something, but they don’t control how it can be used.
ERC-4519 adds user permissions, allowing physical assets (like smart devices) to verify who is authorized to use them, not just who owns them.
2. Makes Physical Assets Smart & Secure
This standard allows physical objects (like cars, locks, and smart appliances) to authenticate their owner and users using cryptography.
This means a car could refuse to start unless the NFT proves the right owner or renter is present.
3. Enables Secure & Traceable Asset Management
The physical asset (e.g., a drone, a security system, or a medical device) gets a unique Ethereum address.
This allows it to securely communicate with its owner and users, ensuring only authorized people can operate it.
Also prevents theft or unauthorized control—if someone tries to hack the device, it won’t work without the proper cryptographic proof.
4. Enables Ownership & Access Rights Transfers Without Middlemen
Currently, if you sell a physical item with software (like a smart car or IoT device), you often need a centralized company (e.g., Tesla, Apple) to update ownership and permissions.
With ERC-4519, this process happens decentrally on the blockchain—without needing approval from a company.
This makes buying, renting, or lending physical assets easier and more trustless.
5. Strengthens Security Through Cryptography
Uses elliptic curve cryptography to ensure secure communication between an asset, its owner, and its users.
The device generates its own Ethereum address in a tamper-proof way to prevent identity theft or fake ownership claims.

### Test Cases
The test cases presented in the paper shown below are available [here](https://eips.ethereum.org/assets/eip-4519/PoC_SmartNFT/).

### Copyright
Copyright and related rights waived via [CC0](https://eips.ethereum.org/LICENSE).

### Citation
Please cite this document as:

Javier Arcenegui (@Hardblock-IMSE-CNM), Rosario Arjona (@RosarioArjona), Roberto Román <roman@imse-cnm.csic.es>, Iluminada Baturone (@lumi2018), "ERC-4519: Non-Fungible Tokens Tied to Physical Assets," Ethereum Improvement Proposals, no. 4519, December 2021. [Online serial]. Available: https://eips.ethereum.org/EIPS/eip-4519.