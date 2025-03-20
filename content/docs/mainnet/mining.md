---
title: Mining
type: docs
prev: docs/mainnet/
---
## Bismuth Mining

### Bismuth Heavy3 Mining Algorithm
On October 8, 2018 - block height 854,660 - the new and novel Heavy3 mining 
algorithm was introduced on the Bismuth Mainnet.

**Properties**
- custom sha224
- tailored for GPU miners
- more resistant to FPGAs and ASICs miners

The idea behind the **“Heavy3”** algorithm designed by EggdraSyl is both simple
and effective: It requires a read from a random offset in a fixed lookup table,
for each tested nonce.

This concept can be applied to any other mining algorithm as an additional layer
to protect against a similar attack. If the matching algorithm uses hashcash or
not - bismuth does not - is irrelevant. The final hash state that is tested is
a vector of 32 bits words. Since it is a hash result, it can be considered as a
random vector, it can contain anything, and you can not reverse the process –
this is a hash core property – The lookup table also contains random data. For
each nonce, the extra step is applying a XOR transform to the hash output, given
a random vector from the lookup table, with the index begin determined by the
hash itself, therefore at a random, non predictable, location. The result – xor’d
hash state – is considered as the input vector to the difficulty matching function.

### Open-Source Miner & Pool

- [kbkminer](https://github.com/bismuthfoundation/kbkminer) - kbkminer is a GPU CUDA Miner for Bismuth.
- [Optipoolware](https://github.com/bismuthfoundation/Optipoolware) - Optipoolware is a Mining Pool application which supports kbkminer.

### Legacy Mining Pools That Have Ceased Operations
Significant old legacy pools, listed by alphabetical order.

- Bis-pool.net
- Bismuth.Coinsaurus.com
- EggPool.net
- Noncepool.com


### Blocks Distribution Chart

- [Miningpoolstats](https://miningpoolstats.stream/bismuth)

## References
- [Bismuth Whitepaper](/pdf/whitepaper.pdf)
- [kbkminer](https://github.com/bismuthfoundation/kbkminer)
- [Optipoolware](https://github.com/bismuthfoundation/Optipoolware)
- [Miningpoolstats](https://miningpoolstats.stream/bismuth)