---
title: Autogame Tournament – One Million Block
date: 2019-01-21
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: /favicon-32x32.png
tags:
  - tournament
  - game
---
![](/images/2019-01-21/tournament.png)
20 Months after its mainnet launch, the Bismuth network reached the **1 000 000 blocks milestone**.
<!--more-->

### One million Blocks!
The Bismuth network reached the 1 000 000 blocks milestone.
As a celebration of this event, we’re running a free to play tournament, on top of the Bismuth Chain itself.

Total prizes are **2500 BIS**, split among the **top 10 distinct addresses**.


### What is Autogame?

Autogame is a new game concept by [HClivess](https://github.com/hclivess), Bismuth founder and core dev.

Here is how HClivess describes the game:
Autogame is a **deterministic semi-autonomous computer game** with RPG elements everyone in possession of Bismuth can participate in. […]

Progress in the world is linear, block by block and transaction by transaction. […] Each game ultimately ends in player’s death. The player who survives the longest takes the top spot in the high scores table. [Read more](https://github.com/hclivess/autogame/blob/master/about.md) about Autogame.

### How to play?

The free to play tournament is open from Bismuth **block 1005500** (that’s 2019/01/21,18:26:21 GMT) and will last **5 days**.

You can play Autogame by registering your Bismuth address. Up to 5 registrations will be taken into account. If you register more than 5 games, the 6th and following just will be ignored.

If you don’t have a Bismuth wallet yet, the easiest way is to head over to our [Discord Server](https://discord.gg/mDxgJc5) and use our **Pawer bot**.

##### Quick registration for casual users: just use the Bis url
```
bis://pay/fefb575972cd8fdb086e2300b51f727bb0cbfc33282f1542e19a8f1d/0.00000000/VRdwGXJKt+/bZ>QXZeeX@Zges/Fm1fB;Td+Lda@I9&$7E(
```

Usage of **Chaos Ring item, PvP** and **Ragnarök** event are allowed. You can [read about](https://github.com/hclivess/autogame/blob/master/about.md) them at Github.
> Since you need a few BIS dust to register, if you’re a new user, we will register for you.
Show us some public tweet, post – no spam!!! – where you talked of BIS, and we will register your Pawer address for free.

### See the current players and high scores
Direct link to the 1M Block tournament is http://autogame.bismuth.live:6060/league/tournament2

### Register with Pawer
![](/images/2019-01-21/tournament-002.png)

Pawer is our discord Bot, he can create an address for you and help with many commands.

- Go to the discord, #pawer-bot channel
- Create your address by typing `Pawer deposit`
- Then accept the conditions `Pawer accept`  
- You now have a Bismuth address

If you have BIS on your wallet already, you can register yourself (up to 5 times over the 5 days) with the following command.

`Pawer autogame register tournament2`

This lists your games, with status, current experience, and link to the replay (or ongoing game).
`Pawer autogame list`

![](/images/2019-01-21/tournament-003.png)

### More: Rings, Ragnarök and attack other players!

If you read the “about game”, you probably saw the extra commands you can run to get yourself the “chaos ring” (can do good or wrong, you won’t know until you slide it to your finger), trigger Ragnarök across all running matches, or attack another player!

Here are the matching Pawer commands, to use in DM with Pawer or in the dedicated #Pawer-bot channel:
(all are to be run on a single line)


- Give your running games a chaos ring:
Pawer operation autogame:add fefb575972cd8fdb086e2300b51f727bb0cbfc33282f1542e19a8f1d 0 item:chaos_ring
- Release Ragnarök across all running games:
Pawer operation autogame:add fefb575972cd8fdb086e2300b51f727bb0cbfc33282f1542e19a8f1d 0 event:ragnarok
- Attack another player:
Pawer operation autogame:add ADDRESS 0 pvp:attack
Replacing ADDRESS with the address to attack ofc.

### Register with the Tornado Wallet

Tornado Wallet is currently in Beta, available as package for Windows and Mac, source for Linux.
Get it there: [Tornado Wallet Beta Release](https://github.com/bismuthfoundation/TornadoWallet/releases).

I suppose you followed the install instructions, have an address and at least something like **0.1 BIS** on it. If not, head over to our Discord for help.

You’ll have to activate at least the “Autogame” Crystal. Crystals are like plugins you can add to your wallet.
Go to Crystals, tick Autogame and save.

Then go to the Autogame page, and you’ll be able to send your registration transaction from here.
Copy and paste the BIS url for the tournament, you’ll find it there:

- [Autogame Tournaments](https://github.com/hclivess/autogame/blob/master/leagues.md)

Send and confirm, take time to enjoy the nice popup. You should now be registered.

You can also use the “Transaction” then “Send” screen to make use of the special commands like chaos ring, Ragnarök or attack, refer to the Autogame guide.
Here is an example:

![](/images/2019-01-21/tournament-004.png)




## References
* Github [HClives](https://github.com/hclivess/)
* Github [Autogame](https://github.com/hclivess/BismuthProjects/blob/master/autogame/about.md)
* Github [Autogame Tournaments](https://github.com/hclivess/autogame/blob/master/leagues.md)
* Github [Tornado Wallet](https://github.com/bismuthfoundation/TornadoWallet/releases)


