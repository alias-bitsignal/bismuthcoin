---
title: How to Run Tornado Wallet with a Custom IP
date: 2023-11-15
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: /favicon-32x32.png
tags:
  - tornadowallet
---
![](/images/2023-11-15/header.webp)
Here is the Tornado Bismuth Wallet Startup Guide.
<!--more-->

### Overview

**Issue:** The Tornado Bismuth Wallet fails to start because it needs an updated server list, but the default API is inaccessible.

**Solution:** Manually specify a server IP and port from a **backup API URL** that’s synchronized to the latest block height.

## Windows OS Hotfix
#### 1. Get a Valid IP and Port:

* Go to the backup API URL:
https://bismuth.world/api/legacy.json
* Choose an IP address and port listed at the latest (highest) block height.

#### 2. Create a Batch File:
* Create a text file named `tornado.txt` and then rename it to `tornado.bat`.

#### 3. Add Launch Commands:
* If the Tornado Wallet and your batch file are on the same drive, use:
```
cd "C:\Program Files (x86)\TornadoWallet"
"TornadoBismuthWallet.exe" --server=192.99.34.19:8150
```
* If they are on different drives, use:
```
C:
cd /d "C:\Program Files (x86)\TornadoWallet"
"TornadoBismuthWallet.exe" --server=192.99.34.19:8150
```

#### 4. Save and Run:
* Save the file and double-click `tornado.bat` to launch your Tornado Wallet with the manually selected IP.

## macOS Hotfix
1. Create a Shell Script:
* Open a text editor and create a file named `tornado.sh`.

2. Add Launch Commands:
```
#!/bin/bash
open "/Applications/Tornado Bismuth Wallet.app" --args --server=192.99.34.19:8150
```

3. Make the Script Executable:
* In Terminal, run:
```
chmod +x tornado.sh
```

4. Execute the Script:
* In Terminal, run:
```
./tornado.sh
```

Use these steps to manually set a connection IP for Tornado Bismuth Wallet when the default API is inaccessible. Always ensure the chosen IP is at the latest block height for a successful connection.

--- 

### Bismuth Market Data & Exchanges
- Bismuth CoinMarketCap Information: https://coinmarketcap.com/currencies/bismuth/
- Bismuth Coingecko information: https://www.coingecko.com/en/coins/bismuth
- Uniswap Exchange (DEX): [Wrapped BIS/ ETH Pair](https://www.dextools.io/app/ether/pair-explorer/0xf4f82f8d84c529987201609cecee8ab136a50c8c)
- Pancakeswap Exchange (DEX): [Wrapped BIS/ BSC Pair](https://www.dextools.io/app/bsc/pair-explorer/0x731b8244f818fd488d9dc516edd976a96459ae59)
- ViteX (DEX): [BIS/ BTC Pair](https://x.vite.net/trade?symbol=BIS-000_BTC-000)
- Graviex: [BIS/ BTC Pair](https://graviex.net/markets/bisbtc)

## References
- Backup API URL: [Bismuth World API](https://bismuth.world/api/legacy.json)
- Tornado Wallet: [Github Tornado Wallet](https://github.com/bismuthfoundation/TornadoWallet)


