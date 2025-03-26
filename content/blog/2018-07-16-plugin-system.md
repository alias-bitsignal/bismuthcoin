---
title: Exploring the Bismuth Plugin System
date: 2018-07-16
authors:
  - name: bitsignal
    link: https://github.com/alias-bitsignal
    image: /favicon-32x32.png
tags:
  - plugin
  - Bisbabble
---
![](/images/2018-07-16/plugin-system-001.png)
When noticing that Bismuth ($BIS) has a **plugin system**, I was somewhat surprised—because I don’t know any other blockchain-based cryptocurrency that openly promotes having a plugin system.
<!--more-->

### Interview with Developers EggdraSyl & Iyomisc
------

The plugin feature immediately stood out to me. Plugins have long been powerful components in blogging and forum platforms—so seeing this concept in a blockchain context was exciting. Plugins enhance another software application. This alone sounds intriguing.

The following questions came to mind while exploring Bismuth’s plugin system, and the developers EggdraSyl and Iyomisc were kind enough to answer them.

![](/images/2018-07-16/plugin-system-002.png)

### Bridging Blockchain and Plugin Architecture
------

###### Question: *How did Bismuth achieve the connection between cutting-edge blockchain technology and traditional plugin applications?*

**EggdraSyl:**  
Well, it actually came from a personal need. For my pools and notification/monitoring systems, I needed more data—and faster—than what the node could provide.

I tried various approaches:
* JSON-RPC server (another layer, verbose, added latency)
* Modding the node (risky, painful when upgrading core code)
* Adding native API commands to the core (which were merged)

Still, I needed more.

I’m familiar with WordPress and its plugin/filter system. That inspired the solution: extensions to the core, not affected by updates.

As far as I know, no other crypto offers this. Bismuth plugins allow you to extend node functionality with just a few lines of Python — **no new language to learn**.

### Decentralization and Cross-Node Use
------

###### Question: *Can Bismuth plugins run in a decentralized manner? Can different nodes run the same plugin?*

**EggdraSyl:**  
Let me rephrase: A Bismuth plugin is extra code run by a node, triggered by events—like a new block or change in network difficulty.

Plugins can:
* Be **autonomous** (e.g., play a sound on incoming transactions)  
* Use external APIs (e.g., send notifications, emails)  
* Interact with other blockchains  
* Even **call other plugins**

You could build abstract protocols and token-based cooperation between plugins, but that’s beyond today’s scope. :)

### Learning Curve and Language
------

###### Question: *If I can write plugins for WordPress or phpBB, how hard is it to write one for Bismuth?*

**EggdraSyl:**  
Bismuth plugins are written in Python, just like the node itself. Python is a great high-level language, widely used in machine learning and other fields.

Start with:
* The [plugin docs](https://github.com/bismuthfoundation/BismuthPlugins/tree/master/doc) and hook references  
* The demo plugins—they’re short and well-commented

### Plugin Architecture and Activation
------

###### Question: *How does the plugin system work structurally? How are plugins activated?*

**EggdraSyl:**

* All plugins live in the `plugins/` directory
* Each plugin is its own folder, with at least an `__init__.py` file
* Directory names follow a 000_plugin-name format, where the number sets priority

**Priority conventions:**

* 000–099: Low-level (e.g., IFTTT APIs)
* 100–199: Demos and examples
* 900–999: Tests
* Others: For your own use

To deactivate a plugin: move its folder to `plugins_available/`.  

Note: Plugins load at node startup. Restart the node to activate/deactivate.

### Supported Hooks
------

###### Question:  *What action hooks does the plugin system support?*

**EggdraSyl:**  
See the [documentation](https://github.com/bismuthfoundation/BismuthPlugins/tree/master/doc). The main hooks are:

* `"block"` – Triggered on new blocks  
* `"fullblock"` – Triggered with all block transactions  

The "fullblock" hook is especially powerful—great for reacting to specific transactions.

### Real-World Use Cases
------

###### Question:  *What can Bismuth plugins do?*

**EggdraSyl:**  
With the "fullblock" hook and a few lines of code, you can:

* Get mobile notifications for pool payouts
* Track transactions in Google Sheets
* Deliver digital goods after payment (like in the Dragginator use case)
* Decode data and execute functions (like serverless computing on-chain!)

### Scalability and Comparison
------

###### Question:  *Can Bismuth plugin applications scale?*

**EggdraSyl:**  
Absolutely. Think of them as a layer above Bismuth—you can use:

* Master/slave models
* Sharding
* Round-robin distribution
* Load balancing
* Service tiers

###### Question:  *Is this system comparable to Ethereum smart contracts?*

**EggdraSyl:**  
Nope.  

Ethereum smart contracts:

* Use a specific language
* Run on every node
* Act as a slow, redundant virtual PC

Bismuth plugins:

* Run only on the node you choose
* Add features you need, not others
* Do not need global consensus
* It’s a different design and purpose.

### Plugin and Blockchain Interaction
------

###### Question:  *Does every plugin interaction need to be recorded on the blockchain?*

**EggdraSyl:**  
No. By default, they are not.

However, certified plugins may be introduced—audited by the team and verifiable via their signature or hash stored on-chain.

### Learning Resources and Best Practices
------

###### Question: *Are demo plugins available to help developers learn?*

**EggdraSyl:**  
Yes! Check the [BismuthPlugins repo](https://github.com/bismuthfoundation/BismuthPlugins). If you need a new hook, open an issue or ping me on Discord (#dev channel).

###### Question:  *Is there a best practices guide or cheat sheet?*

**EggdraSyl:**  
Stick to the style of the demo plugins—but hey, they’re your plugins, build them your way. :)

### Why It Matters
------

###### Question:  *What are the benefits of Bismuth having an integrated plugin system?*

**EggdraSyl:**  
If I needed to react to a transaction in most cryptos, I’d have to:

1. Build an app  
2. Integrate JSON-RPC libs  
3. Manage credentials  
4. Poll the node constantly  
5. Write logic, logs, and webhook handlers  
6. Run everything 24/7  

With Bismuth plugins, all of this—except the custom logic—is **already handled**.

You can **focus on what matters**.

### The Dragginator Plugin: A Real-World Use Case
------

###### Question:  *Iyomisc, how did you learn the plugin system?*

**Iyomisc:**  
It was the first **real-world use** of the plugin system. I read the docs, checked the examples—it was easy to adapt. EggdraSyl also helped when needed.

###### Question:  *What inspired the Dragginator plugin?*

**Iyomisc:**  
I wanted to automate dragon deliveries. I needed to detect matching incoming transactions: correct amount, recipient, and not already processed.

The demo code was perfect. I added:

* A hash store for tracking processed transactions
* The `send_no_gui.py` script to deliver tokens and data

Now, it’s **self-contained**. No external app needed—and reusable for other projects.

###### Question:  *How long did it take?*

**Iyomisc:**  
Just a few weeks for the plugin. The real time sink is the website, writing guides, and user text.

###### Question: *Will you open-source any plugins in the future?*

**Iyomisc:**  
My current plugin is basic—very close to the demo. Maybe I’ll release others later. Not sure yet.

###### Question: *What’s your vision for Bismuth plugins going forward?*

**Iyomisc:**  
They’ll keep evolving. Expect:

* More hooks
* More ready-to-use plugins
* More apps built directly on the plugin layer

It’s the best way to interact with the Bismuth blockchain—easier than using the native or JSON-RPC APIs.

### Final Thoughts
------

A big thank-you to **EggdraSyl** and **Iyomisc** for sharing their insights into the powerful Bismuth plugin system and its real-world use in the Dragginator project.

This system clearly shows that **Bismuth isn’t just a blockchain—it’s a flexible development platform**, built for creators.

## References
- Github Rep: [Bismuth Plugins](https://github.com/bismuthfoundation/BismuthPlugins)
- Github Docs: [Plugin Docs](https://github.com/bismuthfoundation/BismuthPlugins/tree/master/doc)
- Github Link: [EggdraSyl](https://github.com/EggPool)
- Github Link: [Iyomisc](https://github.com/iyomisc)



