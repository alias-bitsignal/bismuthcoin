---
title: Overview
type: docs
prev: docs/mainnet/
---

## Bismuth Technical Overview

Bismuth uses an **account-based model** with a unique signature-based transaction identifier.  
Unlike Ethereum, Bismuth does **not** require a nonce to prevent replay attacks.

### Unique Transaction Signature Model

**Intrinsic Uniqueness**  
Every transaction is signed in a way that guarantees a unique digital signature.  
This signature *is* the transaction ID.

**Replay Prevention**  
If someone attempts to replay a transaction, the node detects that the signature/ID already exists in the ledger and rejects it automatically.

---

#### Consensus & Mining

* Consensus Timeline
  - **Pure Proof-of-Work:** block `1 → 800,000`  
  - **Hybrid PoW + Hypernodes (PoS sidechain):** block `800,000 → 4,380,000`  
  - **Pure Proof-of-Work (Post-HF4):** from block `4,380,000` onward

* Algorithms
  - **Hashing:** SHA-224
  - **Mining:** Heavy3 (CPU/GPU-friendly)  
  - **Difficulty:** PID controller (retargets every block)  
  - **Block Time:** 60 seconds target

* Reward Schedule
  - Mining reward declines from **~15 BIS → 0.5 BIS**  
  - Tail emission: **0.5 BIS per block indefinitely** (~262,800 BIS/year)  
  - No premine, no ICO

* Historical Reward Forks
  - **HF1 (800k):** Introduced Hypernode/PoS rewards (0.8 BIS)  
  - **HF2 (1.2M):** Adjusted emission slope  
  - **HF3 (1.45M):** BGV-01 linear emission model  
  - **HF4 (4.38M, 2025):** Removed Dev rewards & Hypernode payouts permanently

* Current Reward Model (Post-HF4)
  - Miner reward only  
  - No Dev reward  
  - No PoS/Hypernode reward

* Hypernode (PoS) Era Summary
  - **0.8 BIS:** block `800k → 1,200,000`  
  - *2.4 BIS:** block `1.2M → 4.38M`  
  - **Removed:** at block `4,380,000`

* Dev Reward
  - 10% of miner reward (until HF4)  
  - Removed permanently after block `4,380,000`

* Supply
  - Total PoW minted is calculated dynamically  
  - See *Supply & Charts* section of the documentation

#### Addresses & Identity

- **Legacy RSA** addresses  
- **ECDSA (Bis1...)** address format  
- **Ed25519 support** modern address format  
- Smallest unit: **0.00000001 BIS (8 decimals)**  
- 1 confirmation required before respending

#### Networking

- Plain-text peers list  
- Optional Tor proxying  
- **Mainnet port:** `5658/tcp`  
- **Testnet port:** `2829/tcp`

#### Ledger & Storage

- Dual-database system: RAM ledger + disk ledger  
- Hyperblock compression (≈96% RAM reduction)  
- Pruning & snapshot support for fast bootstrapping

#### Transaction Layer

- Supports arbitrary data fields  
- Custom operations (e.g., `token:issue`, `token:transfer`)  
- Optional encrypted payloads (asymmetric crypto)

#### Projects & Ecosystem

- Mining pool  
- Experimental casino  
- Mixer (address-anonymization)  
- Peer map  
- Hypernode sidechain (historical PoS era)

#### Node Configuration & Extensibility

- Fully configurable via `config.txt`  
- Plug-in system for:  
  - Wallet  
  - Explorer  
  - Monitoring  
  - Tokens  
  - Custom features

#### Open Source

- 100% open source  
- Repository: https://github.com/bismuthfoundation

---

### References

- [Bismuth Mainnet – GitHub](https://github.com/bismuthfoundation/Bismuth)
