---
title: Android Battery Monitoring
date: 2020-05-09
authors:
  - name: geho2
    link: https://github.com/geho2
    image: /favicon-32x32.png
tags:
  - battery
  - dapp
  - crystal
---
![](/images/2020-05-09/battery.png)
The Android operating system is installed in about 70% of mobile phones worldwide.
<!--more-->

The majority of these phones are using Lithium-Ion (Li-ion) battery cells. Li-ion batteries are relatively expensive. To make sure that the battery lasts as long as possible, below are some tips to achieve that.

- Li-ion chemistry prefers partial discharge to deep discharge, so it is best to avoid taking the battery all the way down to zero. Since Li-ion chemistry does not have a memory, the battery pack is not harmed with a partial discharge. If the voltage of a lithium-ion cell drops below a certain level, it is ruined.
- Li-ion batteries age and only last a few years, even if they are sitting on a shelf unused. So do not avoid using the battery with the thought that the battery pack will last longer. It will not. Also, if you are buying a new battery pack, you want to make sure it really is new. If it has been sitting on a shelf in the store for a year, it will not last as long as a brand new pack. Manufacturing dates are important.
- Avoid heat, which degrades the battery. If the battery gets hot enough to ignite the electrolyte, there will be a fire, usually caused by an internal short.


A new **decentralized distributed app** (dApp) has been developed with the aim of monitoring battery parameters, such as temperature, charging current, battery level and health status. The dApp uses the Bismuth public blockchain to store battery data, and makes use of a second layer asset protocol, see [Condition Monitoring Link](https://bismuthcoin.org/blog/2020-04-30-condition-monitoring/).

A phone battery monitoring dApp serves several purposes, some of which are: 
1) collect enough publicly available data to allow and encourage development and verification of battery analytics algorithms, 
2) to allow a user to monitor the performance of his/her mobile phone battery and to enable condition monitoring and hopefully early detection of abnormal performance, and 
3) to record an immutable performance record of an asset (the mobile phone battery), with the potential to increase future resale value. For example, if a user records on the blockchain the battery data before and after every charging event, the number of battery cycles can then be counted and estimated remaining lifetime potentially calculated.

The dApp has a public website available at `https://phone.batterylife.info`. At this site it is possible to search for and view performance data of different mobile phone batteries, submitted by users around the world. The submitted data can be linked to the serial number of the phone. This serial number can be submitted as is, or encrypted with a password to allow anonymous sharing of data. The encryption uses the password and the asset id as input to a sha256 hash, which guarantees anonymity. Later, if desired, the ownership of the asset can be proven by performing the hash calculation based on the password and the asset id again and comparing the result with the hash stored on the blockchain.

The public website allows for plotting of variables such as battery temperature, charging or discharging current and battery level. PDF reports can be generated and saved for individual mobile phones. Later, when more data has been submitted by a larger number of users, the data analysis section of the dApp will be expanded. The Bismuth project has several discussion channels on Discord and interested users submitting battery data could potentially discuss battery performance and warn each other if abnormal performance is detected.

In order to submit data to the public blockchain, it is necessary to run the Tornado wallet on the Android phone itself using Termux. 

Instructions for how to install the Tornado wallet on Termux can be found here:  
https://bismuthcoin.org/blog/2019-04-14-termux/ 

In addition to the instructions given, the Termux API must also be installed in order to collect battery data from the phone. Termux API can be installed with:

```
pkg install termux-api
```

To submit mobile phone battery data to the Bismuth blockchain, activate the crystal named Phonebattery. A screenshot of the main menu of this crystal is shown below:

![](/images/2020-05-09/battery-02.png)

Note that as a safety feature, the Tornado Wallet needs to be restarted after a crystal has been activated. In this case, press CTRL+C in Termux to stop the wallet and restart it again with: 

```
cd ~/TornadoWallet/wallet; python wallet.py
```

The top button in the menu above (Analyze Phone Data) leads to a screen which is identical to the one on the public website, https://phone.batterylife.info. The other two menu items (Register Phone and Fetch Phone Data) are only available in the crystal and will only work when run using Termux on an Android phone.

The screenshot below shows the plot and DataTable for one specific Android phone, generated using the public website. In the “Select ID” field different Android phones can be selected. The IDs displayed here are either the asset number of the phone, or the asset number encrypted with an anonymizer password.

![](/images/2020-05-09/battery-03.png)

Example of public website display for a particular Android phone asset id.
Data from individual phones can be exported to either PDF or CSV for further offline analysis. The screenshot below shows an example of a generated PDF file.

![](/images/2020-05-09/battery-04.png)

Note that it costs 5 BIS to register a phone to participate in the data displayed in the crystal and at the public website. In addition, it costs 1 BIS for every submission of a new data transaction from the phone. These fees are mainly introduced to reduce spam. 

BIS can be purchased on a number of exchanges, listed at [Coinpaprika](https://coinpaprika.com/coin/bis-bismuth/#!exchanges).

Any income generated by the paid fees will be used to reward new developers who would like to participate in further development of the dApp. The Tornado wallet itself and the Phone Battery crystal are both open source. 

The source code of all the available crystals is available at the [Github Tornado Wallet Repo](https://github.com/bismuthfoundation/TornadoWallet/tree/master/wallet/crystals ).


The following "Hello World" link explains how to get started with crystal development for the Tornado wallet: 
https://bismuthcoin.org/blog/2020-04-13-hello-world/

Pull Requests can be used by anyone who is interested in contributing to the source code of the Bismuth Foundation, see for example: 
http://oss-watch.ac.uk/resources/pullrequest

## References
- Termux Android: [Termux](https://bismuthcoin.org/blog/2019-04-14-termux/)
- Coinpaprika Exchanges: [Coinpaprika](https://coinpaprika.com/coin/bis-bismuth/#!exchanges)
- Hello World App: [Hello World](https://bismuthcoin.org/blog/2020-04-13-hello-world/)
- Pull Request: [Pull Request](http://oss-watch.ac.uk/resources/pullrequest)



