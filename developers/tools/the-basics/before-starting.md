# Before starting

Before starting to go into depth into the command-line-interface, creating Aragon apps, etc., first some important basics:

## What is Web3? <a href="#web3" id="web3"></a>

Unless you've been living under a rock for the last few years, you've probably come across the term **Web3** 😋.

But what does it mean exactly? And why do we care about it in the context of Aragon?

Web3 is the vision of a fully **decentralized web**. One of the craziest things to wrap your head around is that in web3, apps don't need a central server to fetch data from!

How is this possible?

In a nutshell: thanks to something called **peer-to-peer data architectures**. The key point is that in a P2P architecture, instead of requesting data from a central server, you request it from multiple computers (peers) around you.

While this is nothing new in itself -- P2P architectures have existed since the 1990’s (where they rose to fame with file sharing programs like BitTorrent and Napster) -- what's new is the addition of **cryptography and economic incentives** to these architectures.

The fusion of these seemingly disparate disciplines was the big innovation behind Bitcoin, and has since led to the emergence of a new field of research devoted to their intersection (what we now call cryptoeconomics).

While we won't get into the details here, the key takeaway:

{% hint style="success" %}
Cryptoeconomics is the big unlock that has allowed us to start moving from centralized data structures (web2) to more decentralized or fully distributed data architectures (web3).
{% endhint %}

<figure><img src="../../../.gitbook/assets/centralized-vs-decentralized-stack-2.png" alt=""><figcaption><p>Centralized vs Decentralized</p></figcaption></figure>

> Note that there’s a spectrum from fully centralized (left) to fully decentralized (right).

## IPFS (InternetPlanetary File System)

While blockchains -- like Bitcoin and Ethereum -- are key to this Web3 vision, it's important to note that there are **other essential parts** of the Web3 stack that are not covered by them.

For example, since blockchains are relatively expensive to **store data** on, it turns out that they don't make great file systems. That's why there's also a need for decentralized file systems like the \*\*\*\* [**IPFS (InterPlanetary File System)**](https://ipfs.io/) which Aragon also makes use of.

IPFS is a distributed system for storing and accessing files, websites, applications, and data.

## What is a Web3 provider? <a href="#web3" id="web3"></a>

Definition: a Web3 provider an abstraction of a connection to the Ethereum Network, providing a concise, consistent interface to standard Ethereum node functionality.

In poor words, a Web3 provider is "something" that can actually sign and send transactions to the Ethereum blockchain.

If you're new to the decentralized web you might be wondering why we have to use a separate provider to interact with the blockchain.

Why don't decentralized apps (like Aragon's) just do it themselves?

In short, while it's possible for dapps (decentralized apps) to interact directly with the blockchain, using a Web3 provider allows users to interact with dapps without trusting every one of them with their private keys (the keys to their funds).

Without a Web3 provider, users have to have total trust in every dapp they use. With a Web3 provider, they just need to trust that provider.

Examples of web3 providers are [Metamask](https://metamask.io/) and [Frame](https://frame.sh/).

## **Metamask**

Metamask is a browser plugin that allows users to make Ethereum transactions through regular websites. It does this by injecting a javascript library called Web3.js into the namespace of each page your browser loads.

Web3.js is written by the Ethereum core team and has functions that regular web pages can use to make read and write requests to the blockchain. Eventually, we'll have browsers with this sort of functionality built-in (Brave and Opera are working on this). But for now, we need plugins like Metamask to help us bridge the gap between Web2 and Web3.

For instructions on how to use Metamask as your Web3 provider, please follow our [Metamask guide.](https://documentation.aragon.org/products/set-up-metamask)

## Further resources <a href="#further-resources" id="further-resources"></a>

* [DAOs and the Web3 vision](https://www.youtube.com/watch?v=YG3a5ihbkAQ)
* [Why The Internet Needs IPFS Before It’s Too Late](https://techcrunch.com/2015/10/04/why-the-internet-needs-ipfs-before-its-too-late/)
* [A hands-on introduction to IPFS](https://medium.com/coinmonks/a-hands-on-introduction-to-ipfs-ee65b594937)
* [Blockchain infrastructure landscape: a first principles framing](https://medium.com/@trentmc0/blockchain-infrastructure-landscape-a-first-principles-framing-92cc5549bafe)
* [The case for decentralization](https://a16z.com/2019/04/17/why-work-in-crypto-startup-grind-2019/)
* [What comes after open source?](https://a16z.com/2019/01/22/what-comes-after-open-source/)
* [Fat protocols](http://www.usv.com/blog/fat-protocols)
