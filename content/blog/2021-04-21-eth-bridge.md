---
title: Using the BIS<>ETH Bridge Crystal
date: 2021-04-21
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/refs/heads/master/Logo_v2/bis300px.png
tags:
  - bridge
  - crystal
---
![](/images/2021-04-21-eth_bridge.png)

To swap between native BIS and ETH wBIS token, you need the newest Tornado wallet (v0.1.41 or more) with the EthBridge Crystal activated, as pictured above.
<!--more-->
[Tornado Bismuth Wallet releases](https://github.com/bismuthfoundation/TornadoWallet/releases)

Another version of this help, with more detailed info, can be found on our [Github Bismuth FAQ](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/ETH/README.md).

## The wBIS Token

wBIS is an ERC-20 ETH Token with 1:1 native BIS counterpart.

* Chain: ETH Mainnet
* Contract address: `0xf5cB350b40726B5BcF170d12e162B6193b291B41` [View wBIS on etherscan](https://etherscan.io/token/0xf5cB350b40726B5BcF170d12e162B6193b291B41)
* Name: Wrapped BIS
* Decimals: 8 (same as native BIS)
* Custom logo: `https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/master/Logo_v2/wbis500x500.png`
![](/images/2021-05-12-wbis125x125.png)

The Eth bridge crystal comes with a one-click button to set up the correct custom token on your metamask extension.

The Bridge is decentralized and runs thanks to a custom BIS protocol.
It relies on Both a bridge and an oracle.

* BIS Bridge Address: `Bis1UBRiDGEQc9mBywXpwFZX6LF7hN4i8Qy9m` [Bridge explorer link](https://bismuth.im/search?quicksearch=Bis1UBRiDGEQc9mBywXpwFZX6LF7hN4i8Qy9m)
* BIS Oracle Address: `Bis1XETHbisxnShtghYQJDbf8o5gsQczW8Gp2` [Oracle explorer link](https://bismuth.im/search?quicksearch=Bis1XETHbisxnShtghYQJDbf8o5gsQczW8Gp2)

## BIS to wBIS

Send native BIS to the bridge, get wBIS on ETH (same amount less 5 BIS fees)

* Pick “BIS->WBIS 1/2” menu – also available from “swaps” page
* Fill in ETH recipient and amount double check your ETH address, no going back
* Send the BIS
* Go to “Swaps” page
* wait for the BIS confirmations, then for the mint to be signed.
This can take a while depending on the timing and availability of the signers. Just be patient.
If your transaction is confirmed on the BIS chain, it will eventually go through.
* Use the “proxy mint” link to mint your wBIS (auto filled parameters)
* Your ETH wBIS balance is updated

Detailed [step by step guide](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/ETH/BIS_TO_WBIS_DETAIL.md) with screenshots on Github

## wBIS to BIS

Burn wBIS on ETH, get native BIS on BIS chain (same amount less 5 BIS fees)

* Pick “wBIS->BIS” menu – also available from “swaps” page
* Fill in BIS recipient and amount double check your BIS address, no going back
* Check and adjust gas price
* Burn the wBIS
* Wait for the ETH confs, then for the oracle and delivery to be signed.
This can take a while depending on the timing and availability of the signers. Just be patient.
If your transaction is confirmed on the ETH chain, it will eventually go through.
* You can go to “Swaps” page to monitor the progress
* Your BIS balance is updated

## Video walkthrough

{{<youtube 6CdenJJ28N4 >}}
Thanks Damian for the video!

## Add liquidity

Once you have wBIS on ETH, you can provide liquidity by binding both $wBIS and $ETH to a liquidity pool. [wBIS/ETH Pool](https://v2.info.uniswap.org/pair/0xf4f82f8d84c529987201609cecee8ab136a50c8c).

The more volume in the pool, the less the volatility and the more it can be noticed by ETH traders. Everyone is encouraged to contribute to the liquidity pool to support Bismuth. If you’re new to ETH and Uniswap, make sure you read about impermanent loss so you know what you’re doing and what the potential risks are.

## Farm wBIS on Unicrypt

The Unicrypt farm will operate from April 28 2021, you can already stake there. Please check the [wBIS farming guide](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/ETH/unicrypt_farming.md).

Staking on the farm will provide temporary rewards as wBIS.

**Note:** Nothing in this post is to be considered as financial advice!


## References

- [Tornado Wallet](https://github.com/bismuthfoundation/TornadoWallet/releases)
- [Github Bismuth FAQ](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/ETH/README.md)
- [wBIS on etherscan](https://etherscan.io/token/0xf5cB350b40726B5BcF170d12e162B6193b291B41)
- [BIS Bridge on Bismuth Explorer](https://bismuth.im/search?quicksearch=Bis1UBRiDGEQc9mBywXpwFZX6LF7hN4i8Qy9m)
- [Oracle on Bismuth Explorer](https://bismuth.im/search?quicksearch=Bis1XETHbisxnShtghYQJDbf8o5gsQczW8Gp2)
- [Step by Step Guide](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/ETH/BIS_TO_WBIS_DETAIL.md)
- [wBIS/ETH Pool](https://v2.info.uniswap.org/pair/0xf4f82f8d84c529987201609cecee8ab136a50c8c)
- [wBIS farming guide](https://github.com/bismuthfoundation/Bismuth-FAQ/blob/master/Bridges/ETH/unicrypt_farming.md)