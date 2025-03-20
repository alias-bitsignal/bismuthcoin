---
title: Bismuth Governance Shift - Part 1
date: 2019-08-29
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/refs/heads/master/Logo_v2/bis300px.png
tags:
  - vote
  - governance
  - mainnet
---
![](/images/2019-08-29-governance-shift-part_1.png)
During the first two and a half years of the Bismuth blockchain project, important governance actions have been decided by the group of foundation members. Now the core team finds it is time to involve the community deeper into governance questions, and make more use of community feedback.
<!--more-->

 The Bismuth project has had a very active Discord community since the beginning, and it is seen as a very valuable resource for the project and it makes sense to consult the community more than in the past for input on important decisions. Therefore, the foundation members have decided to introduce a shift in the governance, by letting the stakeholders involved vote on important decisions concerning the future of the project.

Discord alone however can’t be seen as a source of actionable feedback:

* Not everyone is active there.
* Some voices do flood day after day with the same suggestions (count as one, no matter how many times you repeat yourself).
* Not all suggestions are well presented and actionable.
* You can’t map a discord user to a Bismuth User (unless some flavor or KYC or associated wallets with Discord ids).

Twitter polls are also totally un-trustable:

* Like with Discord, you do not reach everyone.
* You can’t map a Twitter user to a Bismuth user (unless KYC/ de-pseudonymization).
* Twitter polls are easily manipulable, there are plenty of services to buy votes.

So, the core team came to realize that if Discord is ok to gather some feedback and proposals, if everyone’s voice is to be heard and a decision in the common interest is to be taken, the voting process has to go further than that.

Until then, the Bismuth team was the only responsible entity for core changes, like the introduction of the Hypernodes and related rewards, and later on, the move of some part of the mining reward toward Hypernodes. The Team always had in mind the long term success of the project, and took every class of user point of view into account before deciding: investors, miners, devs, etc.

Now, the core team feels that the time has come to let users hold their responsibilities and take the decision for everyone’s best interest, via a voting process. The team would prepare options to vote upon, the users will decide, the team will take action based on the final voting results.

### The first vote in Bismuth History

If you are familiar with the discord, you cannot avoid the economists lobbying for a supply modification.

The latest fork ([see here](/blog/2019-05-17-hard-fork-v4.3.0.0/)) was tailored to account for increased services to be provided by the Hypernodes, while not raising the dilution. It already went in the direction of reducing miner rewards. Currently the most vocal suggestions aim to address the dropping price concern, and are to significantly reduce the supply by cutting the emission: that is both block rewards and HN rewards.

The team ran simulations, examined the available data but still it is not clear what the global implications can be, nor how action or inaction would be welcome by the users and the markets. The problem really is complex with implications at the ethical, economical level, involving the equilibrium of the whole system. The more you dig, the more it appears complex.

It looks like it is the perfect case where a community vote is needed and will make sense.

A voting process can be an equally daunting task, because blockchain based voting is tricky and dangerous. The difficulty is two fold:

### A – What is “one” vote?

Blockchains usually are non-KYC (Know Your Customer) and anonymous or pseudonymous. One user can have many addresses. Some do require KYC (Like Tezos), that’s a road the core team does not want to take. So you never can map one vote to one user. Even if you could, voters could be bribed.

* Is a vote one address?
* One coin?
* One IP address?
* One hash unit? In any case, you could pretend you have several voices when all are yours.

### B – Will I vote for the best common interest?

In a blockchain context, you can have several classes of people with different objectives. For Bismuth for instance, a Proof-of-Work (PoW) utility token, you can think of:

* The miners.
* The holders.
* The dApps developers.
* The core foundation team.

Each of these classes can have a different egoistic goal when speaking of chain governance. Just as a quick illustration, miners would like higher fees or block rewards, holders want less dilution and more marketing, dapps developers want low fees and fast blocks, core team wants the token to go mainstream, be secure and used in the real world.

Game theory shows that this can lead to votes that are counter productive for the chain as a whole (see “tragedy of the commons“, this is somehow related).

### Ethereum Case – Carbonvote
Before presenting the proposed Bismuth voting model, an example vote based on the Ethereum blockchain is briefly discussed. In order to decide about the “ice age” issue, ETH owners could vote on a motion to delay it.

How did it work?

* Every address could vote, address balance = vote weight.
* 0 ETH sent, but consumes gas.
* You could change your vote anytime, or move ETH to change your vote weight.
* The current, real time state of the vote was public at carbonvote.com.

The core team feels this model has several flaws, that can be deduced from the voting protocol.

* Gives advantage to holders, exchanges and service providers (the higher your wallet balance, the more your weight).
* Public votes, real time stats, means you can play mind games, swap votes last moment and heavily influence the whole process.
* Users do vote but take no real risk, no responsibility. They have nothing to gain or lose if they don’t care about the results.
* You can be bribed to vote.

In a next article, you’ll be presented the Bismuth Governance Voting Model (BGVM), which is a novel protocol to address fair voting in the context of blockchain governance, and addresses the issues we just saw with the naive protocol above.

## Summary

The Bismuth team will begin to introduce governance to help decide about some core Bismuth choices.
A novel voting process was designed and will be used.
The first issue stakeholders will be able to vote upon is the need or not to change the core supply metrics.

## References

- [Markdown Syntax](https://www.markdownguide.org/basic-syntax/)
- [Hugo Markdown](https://gohugo.io/content-management/formats/#markdown)
