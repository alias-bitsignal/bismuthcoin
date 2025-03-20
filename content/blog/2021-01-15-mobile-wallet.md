---
title: Bismuth Mobile Wallet - Genesis and Reward
date: 2021-01-15
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/refs/heads/master/Logo_v2/bis300px.png
tags:
  - wallet
  - mobile
  - android
---
![](/images/2021-01-15-mobile-wallet.jpg)
For way too long, Bismuth had no proper mobile wallet.
<!--more-->

One historical reason is that – despite being the fastest growing language – Python on mobile still is not mainstream. Sure, you can run a fully functional Tornado wallet on Android, but that’s not a 2 click install.

That’s certainly not an excuse however and the team saw the need for an easy to install and operate mobile wallet.

### The chameleon episode
Then, we paid an external team to integrate Bismuth as part of a multi-currency wallet. April 2019, Bismuth was available on the Chameleon wallet. A closed source multi currency wallet from Chainzilla.
There was two benefits for Bismuth:
– Instantly working wallet, from experienced team. No wasted time, no debug or support.
– Chameleon user base. We certainly gained some exposure being present on that wallet, and our potential user base grew immediately.

Alas, late 2020 Chainzilla announced they were stopping the wallet and would open source it. Despite numerous emails and tweets, to day the code is not available yet, and we got no answer from Chainzilla about the custom derivation scheme they used at start.

We were then in a worse position than ever… No more wallet, plus users stuck with a seed they couldn’t use anymore!
Later on, we were able to recover one of the two derivation scheme, the older one still is missing.

### Behind the scenes work
In the mean time, there was several aborted attempts to code our own wallet. This did not went through for lack of in house competences and time, but we had a few constraints in mind anyway, mainly with maintenance in mind:

- Use a known and future proof language and framework
- Aim for minimalist features first
- Ability to publish the wallet on app stores
- Cross platform
- Single code base if possible across platforms
- As close to native as possible
- We did some PWA – Progressive Web Apps experiments, looked at svelte.js, electron, and saw more and more mentions of Dart and Flutter.

Flutter looked like a really great candidate, fulfilling all of our criterion.
We began to search for Flutter experimented developers, and that’s when RedDwarf enters 🙂

RedDwarf had some experience with a previous crypto mobile app with flutter, and was happy to offer his help. He ended up doing way more than that, since he fully developed the current “my Bismuth Wallet” app.
The code is based upon Natrium Flutter wallet and is fully open source.

### End result and reward

If we aimed for a minimalist app to start with, RedDwarf worked faster than we could test and we finally have a full featured wallet that also includes tokens management for instance.

The team was very pleased to work with him and the end result really is impressive.
The Bismuth team happily awards a 20,000 BIS reward to RedDwarf and offers him free HN hosting if he needs.

The wallet is available on [Google Play Android](https://play.google.com/store/apps/details?src=AppAgg.com&id=io.reddwarf.my_bismuth_wallet) and the source code at [Github](https://github.com/redDwarf03/my_bismuth_wallet/).

### iOS Version
iOS Version is already working, thanks to Flutter and Dart, but Apple decided otherwise.
Very recent policies change at Apple store made it so Crypto related app (namely, wallets) are subject to pretty restrictive conditions to be released. As a result the iOS version is not publicly available for the time being, but the team is working on a solution. We expect good news in the next weeks or months.

## References

- [Google Play Android](https://play.google.com/store/apps/details?src=AppAgg.com&id=io.reddwarf.my_bismuth_wallet)
- [Github - My Bismuth Wallet](https://github.com/bismuthfoundation/my_bismuth_wallet)


