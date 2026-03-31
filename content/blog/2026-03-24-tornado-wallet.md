---
title: Tornado Bismuth Wallet v0.1.47 Released
date: 2026-03-24
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: /favicon-32x32.png
tags:
  - wallet
---
![](/images/2026/03.24-tornado-bismuth-wallet.jpg)
The latest release of Tornado Bismuth Wallet v0.1.47 brings an important step forward for Bismuth users, with a strong focus on expanded ED25519 support.
<!--more-->

### Tornado Bismuth Wallet Update

With the updated bismuthclient v0.0.55, Tornado Wallet now supports both ECDSA and ED25519 address schemes. Users can generate new wallet addresses in either format directly inside Tornado Wallet, giving more flexibility in how they manage their Bismuth accounts.

A key advantage of this release is improved compatibility with other tools in the ecosystem. Private keys can now also be imported from wallets such as BIS-Paper Wallet, which already supports ED25519 address generation. This makes it easier for users to move between wallet tools while keeping access to their funds.

Beyond address support, v0.1.47 also includes several quality-of-life improvements. The /messages/ functionality now supports RSA, ECDSA, and ED25519 signing, encryption, and decryption through the shared BismuthClient layer. Error handling for messages has also been improved, so backend issues now appear as clear popups instead of causing crashes.

The release also improves clarity in the message encryption interface by explaining that recipients must already have an outgoing on-chain transaction, so their public key is available for encryption. In addition, the wallet’s home-page news system has been updated, replacing hardcoded news with a local fallback news.json and optional remote GitHub-loaded news support.

Tornado Bismuth Wallet v0.1.47 is available for Windows 11, macOS (Arm-based), and Linux (AppImage).

### Github Download Link
Repository URL:
https://github.com/bismuthfoundation/TornadoWallet/releases/tag/v0.1.47
Feel free to fork or contribute. 

## References
- BIS-Paper Wallet: [BIS-Paper](https://github.com/bismuthfoundation/BIS-Paper)



