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

* System: Proof-of-Work (custom implementation) + HyperNodes (custom implementation)
* Hashing algorithm: SHA224
* Mining algorithm: Heavy3
* Signing algorithm: PKCS1_v1_5
* Block time interval: 60 seconds
* Transaction size: ~650 bytes + data fees
* Mining reward: Tapering from 15 at block 1 to 0 at block 7,100,000
* Difficulty: Proportional–integral–derivative controller
* Difficulty retarget: Every block
* Total PoW reward: 51,370,000 (plus 10% dev rewards)
* PoS reward (HyperNodes): 0.8 per block from block 800,000 to 1,200,000
* PoS reward (HyperNodes): 2.4 per block indefinitely from block 1,200,000
* Smallest unit: 0.00000001
* Confirmations before respending: 1
* Plain text peer list file
* Tor proxy support
* Optimized towards efficiency
* Dual database system for maximum performance
* Database compression/pruning
* Arbitrary data storage ecosystem and philosophy
* Address-based anonymizing transaction mixer
* Asymmetric message and data encryption
* Batteries included: Pool, casino, mixer, peer map
* Node options fully configurable
* All layers built from scratch
* 100% OpenSource
* Mainnet Port: 5658
* Testnet Port: 2829

## References
- [Github Bismuth Mainnet](https://github.com/bismuthfoundation/Bismuth)
