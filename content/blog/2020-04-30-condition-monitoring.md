---
title: Decentralized Condition Monitoring
date: 2020-04-30
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/refs/heads/master/Logo_v2/bis300px.png
tags:
  - crystal
  - app
  - plugin
---
![](/images/2020-04-30-condition-monitoring.jpeg)
Condition monitoring (CM) is the basis for condition based maintenance (CBM). CBM is an alternative to calendar based maintenance, where an asset is serviced in regular time intervals.
<!--more-->

Calendar based maintenance is easy to plan and schedule but it has some weaknesses:

1) Assets which are in a good condition do not need to be regularly taken out of production for service, and 

2) an asset can still fail between regular calendar based maintenance events, causing downtime in production. CM and CBM are therefore used by many industries as an alternative to calendar based maintenance to strike a balance between maintenance costs and costs associated with unplanned downtime in production.

One example from everyday life is the annual service of your car. Since it is done on a regular basis without considering the actual condition of the car, this would be classified as calendar based maintenance. On the other hand, if you one day start to feel a small vibration in the steering wheel while driving and you take the car to service because of this observation, that would be classified as condition based maintenance.

CM and CBM work well in a single organisation where traditional database tools (or data historians) are used to store and secure the data. This single organisation then owns the data and can control who has access. However, when more than one organisation or individual are involved, CM and CBM initiatives often fail because of the following issue: who owns the data and controls the server storing the data? Data and data analysis can have large potential value, and organisations and individuals are often reluctant to give this value away for free or lose control.

However, data sharing among many participants can have large overall benefits for the group or society as a whole. A single asset does not normally operate in isolation, but forms part of a larger machinery or a plant. A condition which may be optimal for a single asset, may not be optimal for the overall machinery. By sharing data between participants, the performance of the overall machinery or industrial plant can be analyzed and optimized. Another example is the case where there are hundreds, thousands or millions of identical assets operating in the consumer industries. By sharing data, under-performing assets can be identified and corrective actions can be taken- benefiting society as a whole.

In the article [“Blockchain world – Do you need a blockchain? This chart will tell you if the technology can solve your problem”](https://ieeexplore.ieee.org/document/8048838), IEEE Spectrum, 2017, Morgan E. Peck presented the chart below.

![](/images/2020-04-30-condition-monitoring-002.jpeg)
Image from: Morgan E. Peck, “Blockchain world – Do you need a blockchain? This chart will tell you if the technology can solve your problem“, IEEE Spectrum, 2017.

This chart illustrates that a public blockchain may be a good solution for problems where:

* More than one participant needs to be able to submit and update data.
* The participants do not need to know and trust each other.
* The data does not need to be private.
* The database needs to be resistant to attacks or censorship.

In this article it will be explained how the Bismuth public blockchain can be used to implement a system for distributed condition monitoring. For more information about Bismuth, see the [whitepaper](/pdf/whitepaper.pdf).

Bismuth is ideally suited to this type of applications, because it contains two fields in the transaction structure which are named “operation” and “datafield”. These two fields allow for building new meta protocols on top of the core blockchain software. In this article it will be demonstrated how a new meta protocol can be used in the development of a solution for decentralized condition monitoring.

One general problem with a decentralized public blockchain is spam. Any participant can submit any data to the chain and this can not be avoided. Instead of trying to prevent spam from occurring completely, a supplementary approach would be to filter out fake data. There are several ways spam protection and filtering can be achieved, for example:

* Introducing fees to submit data. Anyone can still submit spam, but it will be expensive to do so.
* Introduce a meta protocol built on top of Bismuth’s operation and data fields to allow for filtering of fake data.

The class [BismuthSimpleAsset](https://github.com/bismuthfoundation/util/blob/master/bismuthsimpleasset.py) was written with this purpose, to provide tools for filtering of fake data. This class implements at the time of writing three operations in the meta protocol:

```
myapp:register
myapp:unregister
myapp:transfer
```

The app name, in this example `myapp`, can be renamed to distinguish the implementation from other use-cases also using the same public blockchain.

A physical asset often comes with a serial number or identification code printed on the asset itself somewhere. This number is in general not publicly available, but only known by the manufacturer initially, and later the customer. The manufacturer or the customer can use this identification number in Bismuth’s datafield, together with the **operation** `myapp:register` to link the serial number of the asset with his or her public/private key on the Bismuth blockchain.  
Valid **asset registrations** in this `myapp` example can also be filtered with a minimum amount paid, to discourage spammers from randomly guessing and submitting asset id numbers. In addition to being a tool for filtering spam, a registration amount also gives the developer of the myapp use-case an income which can be used to maintain and further develop the service. Similarly, there could be an amount requirement also on the actual asset data submitted.

One decentralized system everyone is familiar with and where everyone is allowed to submit data, is the email system. Anyone can set up a new email server and start sending from it. One of the techniques used in filtering email spam is to use a PTR record. A pointer record, or PTR record, maps an IP address to a FQDN (fully qualified domain name). It is the counterpart to the A record and is used for reverse DNS lookup, which can help with blocking spammers. Many SMTP servers reject emails if no PTR record is found for the sending server.

The proposed approach presented in this article where an asset id number is linked to the public/private key on the blockchain to filter spam is similar to the reverse DNS method to filter email spam. The first user to link the asset’s identification number to his or her account, can be considered to be the rightful owner of the asset. This information can then later be used to filter out fake data about this asset submitted by other users. The following Python function in **BismuthSimpleAsset** returns the valid registrant given an asset id:

```
def get_registrant(self,asset_id):
    """Returns the current registrant of a specified asset id"""
    regs = self.__get_reg_unreg_sorted(asset_id)
    registrant = self.__get_registrant_from_regs(regs)
    return registrant
```

If the asset owner later wants to release his or her registration of the asset, this can be done by submitting the **operation** `myapp:unregister` together with the asset id in the **datafield**. Alternatively, the asset owner can transfer the ownership of the asset to another account by submitting the operation myapp:transfer together with the following in the **datafield**: `asset_id,new address`.

Another function in the BismuthSimpleAsset class- `get_all_asset_ids()` -returns all valid asset id numbers and associated Bismuth accounts. This function handles multiple register, unregister and transfer events of assets.

Whenever a participant submits data to the public blockchain, the command `myapp:data` can for example be used, or something more specific, for example `myapp:vibration_data`. In the datafield a JSON string can be submitted, allowing for a flexible list of variables to be used. The asset id should be part of this JSON structure, to allow the filtering of fake data. Bismuth allows for a string of up to **100,000 characters in the datafield**, so relatively large amount of data can be submitted. However, the transaction fee increases linearly with the data size.

Having a decentralized public blockchain with open data for everyone to access has potentially many benefits. Some of the benefits are:

- It allows for independent 3rd party data analysts to offer services to the participants. This analysis can for example tell you about the performance of your asset, and what you can do to improve it.
- If someone registers a valid asset id and starts submitting fake data, this can potentially be detected by 3rd party data analysis. For example, some physical variables like the odometer value of a car can only increase over time. Invalid data based on more complex relationships between variables can potentially also be detected. The 3rd party service could then for example offer a whitelist and blacklist of asset id numbers, to allow for even more advanced data filtering.
- The owner of an asset can compare the performance of his or her asset with other peers, detect sub-optimal performance, and apply corrective actions.
If the owner later wants to sell the asset to someone else, he or she can provide proof of asset performance during it’s lifetime to the new owner by using the publicly available data. By giving proof that the asset has been operated with care and within the specifications, the resale value of the asset may be higher than it otherwise would be.
- An increasing number of assets and consumer products are connected to the internet, and come with API interfaces which the owner or operator can use. Hence, the submission of data to the public blockchain can easily be automated or semi-automated for such assets.

This article has given an introduction to some building blocks for decentralized condition monitoring using the Bismuth public blockchain. Several future applications and implementations using the principles laid out here are currently being worked on and will be published separately when ready.

## References

- [Blockchain World - Do you need a blockchain?](hhttps://ieeexplore.ieee.org/document/8048838)
- [Bismuth Whitepaper](/pdf/whitepaper.pdf)
- [Github - Bismuth SimpleAsset](https://github.com/bismuthfoundation/util/blob/master/bismuthsimpleasset.py)


