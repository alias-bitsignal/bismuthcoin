---
title: The largest ignored use case for cryptocurrencies
date: 2020-05-30
authors:
  - name: HCLivess
    link: https://github.com/hclivess
    image: /favicon-32x32.png
tags:
  - exchange
---
![](/images/2025-03-26/bismuth-crypto.png)
Cryptocurrencies and trading. They are indivisible.
<!--more-->

 Since your first purchase of Bitcoin to your potential cashing out, be it for fiat or for products and services, **you have to deal with trading**. Considering the volatile nature of crypto, you are also most likely to be introduced to technicalities surrounding it – walls, spreads, supports, resistances, formations, trends, the list is endless.

It is often surprising, however, how divided the worlds of crypto traders and exchanges versus crypto developers and dedicated followers are. They seem to skip the most evident reality of crypto for ideology. But we should not ignore trading. We should take advantage of this most important use case there is, because there is no skipping it. It will always be here, and always be a major part. At least until Bitcoin surpasses fiat currencies as a world standard – the idealists “are already there”, **ignoring all the opportunities surrounding it**.

The realization of importance of trading led me to the programming of [qTrader](https://github.com/hclivess/qtrader), an interface which actively trades on one of the best crypto exchanges around, [qTrade](https://qtrade.io/). It is a simple bot designed for **automated trading**, it just places sell orders and buy orders on top of bid and ask sides, guaranteeing you best current prices for selling and purchasing your favorite projects. It is configurable for both distribution and accumulation. There it started. I entered the rabbit hole of algorithmic trading from a more active position than before. Suddenly, I was no longer just a fascinated consumer of other people’s bots. I was one of the authors.

My fascination led me onto [Freqtrade](https://www.freqtrade.io/en/latest/), which is far more versatile and dynamic tool than qTrader. It is completely free and you can import your favorite trading strategies based on technical analysis into it. It runs on two main pillars, [TA-Lib](https://github.com/mrjbq7/ta-lib) and [CCXT](https://github.com/ccxt/ccxt). I thought to myself: I clearly see what qTrader is missing as compared to Freqtrade. But what does qTrader have that Freqtrade does not? Then it struck me. It was the integration of the qTrade exchange.

From there, I contacted Eric from qTrade, who already previously talked to the CCXT team. With the CCXT team focusing on their own development and problems, the integration was pushed down on the priority list. Eric, however, said he would talk to the CCXT team again and he did. They promised they would add qTrade within 14 days and that’s what happened. Therefore, you will soon be able to trade there using Freqtrade. **Code merging** happened on **Monday, May 25**. After that, some testing might still be required to see if everything works as intended.

Freqtrade offers you a bundle of basic and more advanced trading strategies, which you can further adjust and customize using Python and the TA-Lib, which is a technical analysis trading library. Most of the hard stuff has already been written, you just need to configure your conditions for buying and selling based on indicators. Or you can try the bundled ones – moving averages, bollinger bands, scalping. You can backtest your strategy and preview its performance in the so called “dry run” before you’re ready to put your money to task.

I am continuing with research into algorithmic trading and thinking about **more ways on how to make Bismuth useful in this regard apart from it just being a traded cryptocurrency**. There could be services offering algorithmic trading that would incur minimal fees and would use Bismuth for purchase of individual plans. If we were capable of improving the existing strategies or developing our own with better profitability, this use case would **open a door to an entirely new level of crypto adoption**. Because everyone in crypto trades crypto, whether they like it or not.

Jan Kučera
Team Bismuth


## References

- [qTrader](https://github.com/hclivess/qtrader)
- [qTrade](https://qtrade.io/)
- [Freqtrade](https://www.freqtrade.io/en/latest/)
- [TA-Lib](https://github.com/mrjbq7/ta-lib)
- [CCXT](https://github.com/ccxt/ccxt)



