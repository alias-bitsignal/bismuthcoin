---
title: Overview
type: docs
prev: docs/mainnet/
---
## Bismuth Technical Overview

Bismuth, an **account-based model**, doesn’t require a unique identifier (like a nonce) to prevent replay attacks as Ethereum does. Instead, it uses its unique transaction signature for identification.

### How the Unique Signature Method Works
**Intrinsic Uniqueness:** In Bismuth, every transaction is signed in such a way that the resulting signature is unique. This signature then becomes also the transaction’s identity.  

**Replay Prevention:** Since a valid transaction is uniquely identified by its signature, if someone tries to replay the same transaction, the system can detect that the signature (and thus the transaction ID) has already been used and reject the duplicate.

Consensus mechanism:
    Pure Proof-of-Work (block 1 → 800,000)
    Hybrid PoW + Hypernodes (PoS sidechain) (800,000 → 4,380,000)
    Pure Proof-of-Work again (after block 4,380,000)

Hashing algorithm:
    SHA-224 (block header hashing)
Mining algorithm:
    Heavy3 (CPU/GPU friendly PoW function)

Block time:
    60 seconds (target)

Transaction size:
    ca. 650 bytes per transaction + dynamic data fees

Reward schedule:
    Mining reward decays from ~15 BIS → 0.5 BIS per block (tail emission)
    Tail emission: 0.5 BIS per block forever (~262,800 BIS/year)

Reward forks:
    HF1 (800k): Introduced Hypernode/PoS payouts (0.8 BIS)
    HF2 (1.2M): Adjusted emission slope
    HF3 (1.45M): BGV-01 emission change (new linear decay model)
    HF4 (4.38M, 2025): Removed Dev rewards & Hypernode payouts permanently

Current reward system (post-HF4):
    Miner reward only
    No Dev reward
    No PoS/Hypernode reward

PoS / Hypernode payouts:
    0.8 BIS (block 800k → 1,200,000)
    2.4 BIS (block 1.2M → 4.38M)
    Permanently removed at block 4,380,000

Dev reward:
    10% of miner reward (until block 4,380,000)
    Removed entirely at HF4

Total PoW minted to date:
    Dynamically calculated — see supply graphs in documentation

Smallest unit:
    0.00000001 BIS (8 decimals)

Difficulty algorithm:
    Proportional–Integral–Derivative (PID) controller

Difficulty retarget:
    Every block

Consensus rules:
    1 confirmation to respent funds
    No premine, no ICO

Addresses:
    Legacy RSA Bismuth addresses
    Supports ECDSA addresses (Bis1...)
    Also supports modern Ed25519 plug-ins (wallet-side)

Peer system:
    Plain-text peers list
    Tor proxy support available

Ledger database:
    Dual-database (RAM ledger + disk ledger)
    Hyperblock compression (≈96% RAM reduction)
    Pruning and snapshot support (fast bootstrapping)

Transaction layer:
    Arbitrary data fields
    Custom operation system (token:issue, token:transfer, etc.)
    Optional asymmetrically encrypted payloads

Projects:
    Mining pool
    Casino (experimental)
    Mixer (address-based anonymizer)
    Peer map
    Hypernode sidechain (for PoS era)

Node configuration:
    Fully customizable via config file
    Plugin system for wallet, explorer, monitoring, tokens

Open Source:
    100% open – https://github.com/bismuthfoundation

Mainnet port:
    5658/tcp

Testnet port:
    2829/tcp




## References
- [Github Bismuth Mainnet](https://github.com/bismuthfoundation/Bismuth)
