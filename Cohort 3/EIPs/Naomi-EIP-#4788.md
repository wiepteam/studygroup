# EIP Name

Beacon Block Root in the EVM

# EIP Number

 EIP-4788

## EIP Creation Date

 10th Feb, 2022

## EIP Authors

 Alex Stokes (@ralexstokes), Ansgar Dietrichs (@adietrichs), Danny Ryan (@djrtwo), Martin Holst Swende (@holiman), lightclient (@lightclient)

### Description of EIP

#### Problem

After Ethereum switched to Proof‑of‑Stake, smart contracts still needed fresh information from the beacon chain—like whether a validator was slashed or what the latest checkpoint is. Getting that data meant asking an external oracle, which adds cost, complexity, and trust. If the oracle lies, breaks, or gets censored, the on‑chain app is stuck with bad or missing information.

#### Idea of EIP‑4788

EIP‑4788 solves this by giving the EVM a built‑in window into the beacon chain. With every new block, a tiny system contract records the parent beacon block root—a 32‑byte hash that summarizes the whole consensus state—and keeps a one‑day rolling history. Any contract can read that root and verify Merkle proofs by itself, cutting out oracles entirely. This makes staking pools, bridges, and other apps both cheaper and more trust‑minimised.

### Aditional Information

[Ethereum Magicians](https://ethereum-magicians.org/t/eip-4788-beacon-root-in-evm/8281)

[ConsenSys Deep Dive by Alex Stokes](https://consensys.io/blog/ethereum-evolved-dencun-upgrade-part-3-eip-4788)


[Link to EIP 4788](https://eips.ethereum.org/EIPS/eip-4788)
