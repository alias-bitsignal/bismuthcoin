---
title: Using the BIS<>BSC Bridge Crystal
date: 2021-05-12
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/refs/heads/master/Logo_v2/bis300px.png
tags:
  - bridge
  - crystal
---
![](/images/2021-05-12-bsc_bridge.png)

To swap between native BIS and BNB wBIS token, you need the newest Tornado wallet (v0.1.43 or more) with the BscBridge Crystal activated, as pictured above.
<!--more-->
[Tornado Bismuth Wallet releases](https://github.com/bismuthfoundation/TornadoWallet/releases)

Another version of this help, with more detailed info, can be found on our [Github Bismuth FAQ](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/BSC/README.md).

### The wBIS Token

wBIS is a BEP-20 BSC Token with 1:1 native BIS counterpart.

* Chain: BSC Smart Chain
* Contract address: `0x56672ecb506301b1E32ED28552797037c54D36A9` [View on bscscan](https://bscscan.com/token/0x56672ecb506301b1e32ed28552797037c54d36a9)
* Name: Wrapped BIS
* Decimals: 8 (same as native BIS)
* Custom logo: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/master/Logo_v2/wbis500x500.png
![](/images/2021-05-12-wbis125x125.png)

The Bsc bridge crystal comes with a one-click button to set up the correct custom token on your metamask extension.

The Bridge is decentralized and runs thanks to a custom BIS protocol.
It relies on Both a bridge and an oracle.

BIS Bridge Address: `Bis1FWBNBbrYZkQmCYQf8FQWTUCFEreUeT71`  
[Bridge Explorer Link](https://bismuth.im/search?quicksearch=Bis1FWBNBbrYZkQmCYQf8FQWTUCFEreUeT71) 

BIS Oracle Address: `Bis1XBNBY66wngPLVwbRbnSs4ScVBwE3iM7kL`  
[Oracle Explorer Link](https://bismuth.im/search?quicksearch=Bis1XBNBY66wngPLVwbRbnSs4ScVBwE3iM7kL) 


### Add BSC network to Metamask


Open Metamask and click on ‘My Accounts‘ > ‘Settings‘ > ‘Networks‘ > ‘Add Network‘
Fill in the following data for the BSC Mainnet.

– Network Name: BSC Smart Chain  
– New RPC URL: https://bsc-dataseed.binance.org/  
– ChainID: 56  
– Symbol: BNB  
– Block Explorer URL: https://bscscan.com  


[Detailed screenshots on Github](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/BSC/README.md#add-bsc-network-to-metamask)

### BIS to wBIS

Send native BIS to the bridge, get wBIS on BSC (same amount less 5 BIS fees)

* Pick “BIS->WBIS 1/2” menu – also available from “swaps” page
* Fill in BSC recipient and amount **double check your BSC address, no going back**
* Send the BIS
* Go to “Swaps” page
* wait for the BIS confirmations, then for the mint to be signed.
This can take a while depending on the timing and availability of the signers. Just be patient.
If your transaction is confirmed on the BIS chain, it will eventually go through.
* Use the “proxy mint” link to mint your wBIS (auto filled parameters)
* Your BNB wBIS balance is updated

[Detailed step by step guide with screenshots on Github](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/BSC/BIS_TO_WBIS_DETAIL.md)

### wBIS to BIS

Burn wBIS on BSC Smart Chain, get native BIS on BIS chain (same amount less 5 BIS fees)

* Pick “wBIS->BIS” menu – also available from “swaps” page
* Fill in BIS recipient and amount **double check your BIS address, no going back**
* Check and adjust gas price
* Burn the wBIS
* Wait for the BSC confs, then for the oracle and delivery to be signed.
This can take a while depending on the timing and availability of the signers. Just be patient.
If your transaction is confirmed on the BSC Smart Chain, it will eventually go through.
* You can go to “Swaps” page to monitor the progress
* Your BIS balance is updated

### Add liquidity

Once you have wBIS on BSC, you can provide liquidity by binding both $wBIS and $BNB to a liquidity pool. [wBIS/BSC Pool](https://exchange.pancakeswap.finance/#/add/BNB/0x56672ecb506301b1E32ED28552797037c54D36A9)

The more volume in the pool, the less the volatility and the more it can be noticed by BNB traders. Everyone is encouraged to contribute to the liquidity pool to support Bismuth. If you’re new to BNB and Pancakeswap, make sure you read about impermanent loss so you know what you’re doing and what the potential risks are.

### Farm wBIS on Pancakeswap

The Pancakeswap farm is WIP, an update will follow. Please check the [wBIS farming guide](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/BSC/pankeswap_farming.md).  
Staking on the farm will provide rewards as wBIS.

**Note:** Nothing in this post is to be considered as financial advice


## References

- [Tornado Wallet](https://github.com/bismuthfoundation/TornadoWallet/releases)
- [Github Bismuth FAQ](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/BSC/README.md)
- [wBIS on bscscan](https://bscscan.com/token/0x56672ecb506301b1e32ed28552797037c54d36a9)
- [BIS Bridge on Bismuth Explorer](https://bismuth.im/search?quicksearch=Bis1FWBNBbrYZkQmCYQf8FQWTUCFEreUeT71)
- [Oracle on Bismuth Explorer](https://bismuth.im/search?quicksearch=Bis1XBNBY66wngPLVwbRbnSs4ScVBwE3iM7kL)
- [Step by step Guide](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/BSC/BIS_TO_WBIS_DETAIL.md)
- [Add Liquidity](https://exchange.pancakeswap.finance/#/add/BNB/0x56672ecb506301b1E32ED28552797037c54D36A9)
- [wBIS farming guide](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/BSC/pankeswap_farming.md)