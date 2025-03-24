---
title: My Bismuth Wallet - Mobile Wallet
date: 2021-01-14
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/refs/heads/master/Logo_v2/bis300px.png
tags:
  - mobile
  - wallet
---
![](/images/2021-01-15/mobile-wallet.jpg)
For way too long, Bismuth had no proper mobile wallet, or was dependent on third party wallets.
Those days are over!
<!--more-->

### Downloading the Mobile Bismuth Wallet
The Bismuth team is proud to announce that its brand new mobile Wallet, “My Bismuth Wallet” app is available on:

* [Google Play (Android)](https://play.google.com/store/apps/details?src=AppAgg.com&id=io.reddwarf.my_bismuth_wallet)
* IOS (Work in progress)
* [Github (Source code)](https://github.com/bismuthfoundation/my_bismuth_wallet)

It was developed by our User RedDwarf as open source: awesome job!

## Wallet Walk-through

### Initial Setup

![](/images/2021-01-15/mobile-wallet-001.png)

### 1. Hierarchical Deterministic Key Generation

The new mobile My Bismuth Wallet is using the BIS HD standard for generating keys.
The mobile Wallet lets you either create a new wallet (seed) or you can import a seed which you already have.
Seeds and addresses are compatible with Angainor’s paper wallet. [link](https://angainordev.github.io/BIS-Paper/js/dist/index.html)

![](/images/2021-01-15/mobile-wallet-002.png)

### 2. QR Scan Option

When importing the secret phrase you have the option to QR Scan the secret phrase (seed) or you can copy and paste the seed.

![](/images/2021-01-15/mobile-wallet-003.png)

### 3. Password Protected & Biotmetrics

For security reasons you can define a password for opening the mobile wallet app. It is also possible to use biometrics instead.

![](/images/2021-01-15/mobile-wallet-004.png)

### 4. Backup Seed

When you have created a completely new secret phrase (seed), double check that you backup your secret phrase in a non digital manner.
This is the most important step to be able to recover the mobile wallet.
No one else but you is able to recover your wallet.

Do not use the sample secret shown here, since it’s public any fund will be robbed.
This seed is also available later on, provided you remind the PIN you used.

![](/images/2021-01-15/mobile-wallet-005.png)

### 5. Wallet PIN Support

Create and backup your wallet PIN to send Bismuth transactions.

![](/images/2021-01-15/mobile-wallet-006.png)

### 6. Send and Receive Transactions

This is the standard My Bismuth Wallet view after creating a completely new wallet.
Your first Bismuth address account has been created and you are all set for receiving Bismuth.
The wheel icon on the top left lets you edit your Wallet settings.
The cat avatar is auto-generated and is meant to easily identify your various addresses.

![](/images/2021-01-15/mobile-wallet-007.png)

### 7. Wallet Options

After clicking the top left icon wheel button you are able to select and change different Wallet options.

You can change the base fiat currency, switch the Wallet language, change security settings (e.g. authentication method, wallet password), displays the Bismuth Token list, manage your contacts, backup your secret phrase and lastly you can logout which wipes your seed phrase.

![](/images/2021-01-15/mobile-wallet-008.png)

### 8. Easy Handling of Addresses

To receive a Bismuth transaction you need to copy your Bismuth address and hand it to sender.
You can do this by clicking on the Receive button and copying the Bismuth address or handing the sender the generated qr code address.

![](/images/2021-01-15/mobile-wallet-009.png)

### 9. Copy & Paste Functionality

Sending a Bismuth transaction is very easy.
You can either enter all the data by yourself or you can use the copy and paste functionality.

There is also another option to use the QR Code scanner to either scan a Bismuth address or you could also scan a QR Code BIS URL transmitting all necessary data.

![](/images/2021-01-15/mobile-wallet-010.png)

### 10. Transaction Confirmation View

After you have successfully sent a transaction you see a confirmation view that the transaction has been sent.

![](/images/2021-01-15/mobile-wallet-011.png)

### 11. Transaction View List

Once you have sent and received Bismuth you will see the transaction list on the main view. This particular view shows that you can not only send Bismuth but also Bismuth based Tokens.
All transactions are listed in this view. If you want to see more information about a particular transaction, you can click on a transaction to see a detailed transaction view.

Note: swiping a tx to the left will prefill a new transaction with same amount and recipient.

![](/images/2021-01-15/mobile-wallet-012.png)

### 12. Bismuth Native Tokens

When you click on the middle bottom icon button from the main transaction view, the wallet will list all Bismuth native Tokens you own.

![](/images/2021-01-15/mobile-wallet-013.png)

### 13. Token List View

To see a list of all available Bismuth Tokens ever created, you can click on settings and then choose the Token List link.

![](/images/2021-01-15/mobile-wallet-014.png)

### 14. Easy Access to Send Bismuth based Tokens

You can send a Bismuth based Token from the normal send view, by sliding the “send a token” button to the right and then choose one of your available Token, add the amount and then send it.

Note: Bismuth native tokens have no decimals.



## References

- [Github - My_Bismuth Wallet](https://github.com/bismuthfoundation/my_bismuth_wallet)
- [HD Paper Wallet](https://angainordev.github.io/BIS-Paper/js/dist/index.html)


