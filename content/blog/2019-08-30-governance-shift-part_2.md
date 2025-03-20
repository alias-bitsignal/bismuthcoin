---
title: Bismuth Governance Shift - Part 2
date: 2019-08-30
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/refs/heads/master/Logo_v2/bis300px.png
tags:
  - vote
  - governance
  - mainnet
---
![](/images/2019-08-30-governance-shift-part_2.png)
### Preamble
In the previous post, the governance shift that is to take place with Bismuth was introduced, and the ETH voting protocol was examined. It was shown that this protocol does come with several issues that could be important flaws in the Bismuth context.
<!--more-->

### Issues with the ETH voting protocol

* There is nothing at stake. You do not directly win or lose anything by voting (just some gas)
* Exchanges as well as shared services, dev funds, and founders have a huge voting power
* The holders are by definition the ones getting the most votes, so the issue is likely to be in favor of the holders group, and potentially detrimental to others and the coin in general.
* Since the votes are public, it allows for any kind of psychological manipulation by influence groups. You could pretend to vote for the other group, so other users are not incited to vote as it appears there is a clear winner. Then swap votes at the very last moment. Influence groups can play mind games.
* You do not vote “your best”, you just vote enough so your group wins.
* You can bribe big balances who do not care to vote for your group, they have nothing to lose, so why not take the bribe and vote?
* Many users could also be bribed to vote against their long term interest: they would get the bribe right now, and have nothing immediate to lose.

In the case of Bismuth, mean exchanges – including Cryptopia’s inactive wallet – or one entity – including the core team – could vote and have chances to impose their own decisions.

### An alternate voting protocol

Now comes a description of the Bismuth Governance Voting Model (BGVM). The goal is to have voters put their money where their mouth is. With this protocol:

* You only vote for something you really want to happen.
* You do take risks, you have to show your motivation. Your vote is not an empty word, the core team is not the only one wetting the shirt.
* Every category has a similar weight and cost to vote. Big balances are not over-represented.
* Still, the richest wallets can have the most weight, and are also the ones benefiting from a higher future price.
* You help finance the project you voted for.
* There is no bribe advantage.
* If you lose, you can still be happy.
* There is no possible mind games nor manipulation until the vote is over.
* The voters involvement is known in real time
* The issue of the vote is secret until it is finished.

> «Bismuth defines a new voting protocol: users have to put their money where their mouth is. Involvement is known in real time but the issue of the vote is secret until over! Good idea?» [Click to tweet](https://x.com/intent/tweet?text=%23Bismuth%20defines%20a%20new%20voting%20protocol:%20users%20have%20to%20put%20their%20money%20where%20their%20mouth%20is.%20Involvement%20is%20known%20in%20real%20time%20but%20the%20issue%20of%20the%20vote%20is%20secret%20until%20over!)

### The protocol

The public interface of the protocol is as follows:

* A motion is proposed, with 2 or more options.
* You vote by sending $BIS + data to the vote address. The amount you send is public, whereas data (your vote) is encrypted and private.
* The $BIS you send are your voting weight. Their use – should the motion pass – are stated in the motion.

#### Options:

* You can issue several voting transactions, so you can increase your weight during the voting period.
* you can invert a previous transaction vote (but not cancel it) should you change your mind.

Once the voting period is finished:

* Votes – and related flips – are revealed.
* If you do not reveal your vote, it cannot be counted, and you do not get your money back.
* Losers get their $BIS back (less transaction fees).
* In the winners’ case, their $BIS go into a community fund to be used as stated by the motion.

### Pros

* There is no need to bribe people, you would have to bribe them more than by voting yourself.
* There will be no mind games, the issue is totally opaque until the end. Even the core team does not have access to the results before votes are revealed.
* You take risks, and only vote for what you really want, because if this happens, your $BIS vote will be used to build it.
* There is no incentive in voting for the other side, since if it wins, you lose your tokens.
* Trolls and fudders have no voice, no leverage. Only final $BIS votes count, once revealed.
* It’s safer for big holders with funds in cold wallet: you don’t have to move your cold funds out to vote. Just vote what you want.
* Involvement (total amount of $BIS) is known in real time.
* No need to run a balance vote on one side, then a miner vote by block signaling on the other side: everyone votes with the same protocol, the same unit.
* You know what the minimum proposal budget will be (at worse, 50.01% of the votes for a vote with 2 options).
* Every group has the same voting cost/power. Holders do not have more power than miners because they have a higher balance. What everyone bets for is what they risk, should they win. If the miners’ group want to overrule the holders, they do not need to have as much balance as the holders, they just need to vote as much as them.
* The amount you vote reflects your belief and involvement in the proposal you vote for, and what you are willing to contribute to see it succeed.

> «Contrary to the Carbonvote process, the #Bismuth “blind” voting protocol renders the vote immune to bribery attacks, and forces users to vote for the long term success of the project. Read more: » [Click to tweet](https://x.com/intent/tweet?text=Contrary%20to%20the%20Carbonvote%20process,%20the%20%23Bismuth%20%27blind%27%20voting%20protocol%20renders%20the%20vote%20immune%20to%20bribery%20attacks,%20and%20forces%20users%20to%20vote%20for%20the%20long%20term%20success%20of%20the%20project.)

### Conclusion

The “blind auction” introduced by the innovative and new BGVM avoids the pitfalls of more common voting and blockchain governance mechanisms seen to date. The protocol protects the project’s global interest by allowing everyone to be represented in a fair manner and forces voters to vote for what they really want in the long term, and not for what would give them the most short term advantage.
The vote issue is an Oracle whose value is only known once the decision is immutable.

> «The new #Bismuth voting protocol merges carbonvoting and block signaling into a single process where every actor votes with the same process and unit for a fair vote that can not be bribed nor manipulated. Read more: » [Click to tweet](https://x.com/intent/tweet?text=The%20new%20%23Bismuth%20voting%20protocol%20merges%20carbonvoting%20and%20block%20signaling%20into%20a%20single%20process%20where%20every%20actor%20votes%20with%20the%20same%20process%20and%20unit%20for%20a%20fair%20vote%20that%20can%20not%20be%20bribed%20nor%20manipulated.)

## References

- [Markdown Syntax](https://www.markdownguide.org/basic-syntax/)
- [Hugo Markdown](https://gohugo.io/content-management/formats/#markdown)
