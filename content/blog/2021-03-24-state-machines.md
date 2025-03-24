---
title: Python and State Machines
date: 2021-02-24
authors:
  - name: Bismuth Foundation
    link: https://github.com/bismuthfoundation
    image: https://raw.githubusercontent.com/bismuthfoundation/MEDIA-KIT/refs/heads/master/Logo_v2/bis300px.png
tags:
  - statemachines
  - python
---
![](/images/2021-03-24/state-machines.webp)
Are you familiar with Finite state machines? They are everywhere, yet, we don’t see them as such.
<!--more-->

### State machines

A state machine – in mathematical terms – is a model of computation.
It is defined by a – finite – list of states, including an initial state as well as transitions: conditions that have it move from one state to another one.
This seems very simple, and it can be. Here is a sample machine from Wikipedia.

![](/images/2021-03-24/finite_state_machine.png)

A simple state machine: a door that can only be closed or open.
Don’t be fooled by the apparent simplicity of this sample: state machine can be very, very complex… but also very useful.

#### Here’s why:
The most known computation model is the Turing machine. Most computer hardware and programming languages rely on this model.
This is a very open model, that allows to do many things. This is also a weakness, because you can’t always predict what states such a model will end up in.

This has several implications. With classical programming, you can end up with an edge case where your program will run forever – be it because of the algorithm, or an implementation bug – or end up in an unplanned state, where it will be stuck and never recover.

This is one of the flaws of the ETH VM for instance, which is Turing complete. Its capacity to run loops means it can be stuck inside a large or infinite loop and consume a huge amount of gas.
Other smart contract languages willingly chose to have a non Turing complete language to avoid unexpected side effects.

The same happens with complex virtual objects like a client or server for a given protocol. Say, a custom protocol over a raw socket, or at a higher level, a blockchain node.

When designing such an object, interacting with others, you often – consciously or not – think of it as a state machine. The node is “starting”, it’s “syncing” or “digesting a transaction” or “waiting for next block” aso…
When you implement this with “regular” code, events, functions, methods, private or global variables… you are not bound by a state machine computation model. You are Turing complete.
The compiler lets you write dangerous things you are not aware of, that can backfire: your system can end up in a totally unstable and unplanned state, with no way back to a functioning mode.

The limits of the state machine model then become a strength: If you model your object as a state machine and take care of all the needed states and transitions, you are sure (to the extend of your trust in the state machine framework you use) your system is only in one of the planned states.

It could end up stuck in a given state with no way out, because you forgot a transition, but it will never magically jump from one state to another with no reason.

Working with state machine is then more stringent: you have to define all possible states and conditions, instead of just the obvious paths. But these added constraints also force you to fully define your model, and allow to reason on a global scale, with an overview you can rely on.

### State machines and Python

Any Turing complete language can implement state machines, since state machines are a subset of the Turing model.

You can code state machine behavior with vanilla code. Have a class, with a private member representing state, and methods as transitions for instance. This is enough for simple things.

If you want to go further, nice libraries and tools have been coded.

As for Python, I picked two of them:

### Pytransition

Pytransition is an actively maintained and very complete state machine framework, with several extensions.

The github comes with a full documentation, the quickstart being a funny “narcoleptic super hero” example

![](/images/2021-03-24/state-machine-02.png)

Quickstart from Pytransitions
Note the diagram is generated from a “diagram” extension, by the module itself.

There is even more since a GUI, running with a Tornado web server and JS client code, allows to draw and manipulate the models. It’s not only fun but pretty useful!

![](/images/2021-03-24/state-machine-03.png)

State machine GUI editor

Many examples come with the library. Best thing you can do is bookmark the Github and use it for your next project or rewrite, then come and tell us! [Github](https://github.com/pytransitions/transitions)

### Pysm

This library is older and simpler, and it’s also why it was selected.

Another big up is its MicroPython support. With embedded python coming everywhere, it would be a shame not begin able to use that state pattern there as well.

Still, Pysm is a complete library, with all you’ll need including transition callbacks, and state hooks, conditional transitions… while remaining lightweight and fast.
It comes with documentation, test and examples. [Github](https://github.com/pgularski/pysm)

![](/images/2021-03-24/state-machine-04.png)

Here is a sample of a complex hierarchical state machine designed with Pysm
(taken from pysm github)

### When to use state machines?

Some use cases are obvious: when the logic is that of an “automaton”, like a vending machine, a “stubborn” and predictable machine that does only a handful of things in the right order, it’s quite easy.
In that case, state machine should be a no brainer.

Some cases are more difficult to grasp at first sight, but they may be where you have the most to gain. Take a socket reading for example, with some custom protocol, or a parser for a specific syntax.
Here, consider the logic as a state machine can alleviate the code a lot, make it clearer, and easier to explain. Added bonus: you’re more confident you did not forgot edge cases (unit test still are required, don’t get me wrong)

Last case is for more complex systems, like a whole blockchain node for instance. As simple as it looks, it’s not at all, and converting legacy code to a state machine can be a huge work. This could even force you to rethink your protocol…
One thing is sure: the sooner you consider your system as a state machine, the better you’ll have a practical overview you can spec, discuss, and work with.

### Some external pointers

* Finite state machine article on [Wikipedia](https://en.wikipedia.org/wiki/Finite-state_machine)
* PyTransitions [Github](https://github.com/pytransitions/transitions) and its GUI [Github](https://github.com/pytransitions/transitions-gui)
* Pysm – with Micropython support [Github](https://github.com/pgularski/pysm)

### Your turn!

It’s up to you!  
Did you already work with state machines?  
Did this post motivate you to give it a try?  
Do you have a good example in mind that could benefit from this model?  

Please tell us, we’re eager to know!  
You can join us on Twitter [@bismuthPlatform](https://twitter.com/BismuthPlatform) or on our [Bismuth Discord](https://discord.gg/8KvA3JU).  

## References

- [Github - Pyrtransitions](https://github.com/pytransitions/transitions)
- [Github - Prysm](https://github.com/pgularski/pysm)
- [Wikipedia - Finite State Machine](https://en.wikipedia.org/wiki/Finite-state_machine)
- [Github - Transitions GUI](https://github.com/pytransitions/transitions-gui)

